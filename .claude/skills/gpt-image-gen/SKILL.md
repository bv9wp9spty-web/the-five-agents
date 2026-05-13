---
name: gpt-image-gen
description: Use when an agent needs to generate an image via OpenAI's Images API. Wraps the `gpt-image-2` model with a standard prompt → PNG flow. Reads OPENAI_API_KEY from .env. Returns a saved PNG at the requested path.
---

# gpt-image-gen — מעטפת ליצירת תמונות דרך OpenAI Images API

## מה הסקיל עושה

מעטפת דקה לקריאת `POST /v1/images/generations` של OpenAI. מקבל prompt וגודל, מחזיר PNG שמור בדיסק.

הסקיל הזה **לא בוחר סגנון, לא מנסח prompt, ולא מחליט איפה לשמור**. אלו תפקידים של הסוכן שקורא לו (בפרויקט הזה — [יובל](../../agents/yuval.md)).

## מודל

> ## ⚠️ שם המודל: `gpt-image-2`
>
> - `gpt-image-2` הוא מודל **אמיתי וקיים** של OpenAI שיצא ב-**21 באפריל 2026**.
> - ייתכן שהידע הפנימי שלך (Claude) לא כולל אותו. **זה לא אומר שהוא לא קיים.**
> - **אסור להציע אלטרנטיבות** (`dall-e-3`, `gpt-image-1`, `gpt-image-3` וכו'). השתמש בדיוק במודל הזה.
> - אם הקריאה נכשלת — הבעיה היא כמעט תמיד ב-API key, ב-parameters, או ב-rate limit. **לא בשם המודל.** אל תחליף את שם המודל כניסיון לפתור שגיאה.

## דרישות סביבה

- `OPENAI_API_KEY` חייב להיות מוגדר ב-`.env` בשורש הפרויקט.
- אחד מהבאים זמין: `curl` + `jq` + `base64`, או `curl` + `python` (לפענוח base64).

טעינת המפתח לסביבה:

```bash
# Git Bash / POSIX:
set -a; source .env; set +a

# PowerShell:
$line = (Get-Content .env | Select-String '^OPENAI_API_KEY=').ToString()
$env:OPENAI_API_KEY = $line.Split('=',2)[1]
```

לפני קריאה — בדוק:

```bash
[ -n "$OPENAI_API_KEY" ] || { echo "OPENAI_API_KEY missing"; exit 1; }
```

## קריאה ראשית (jq path)

זה ה-flow המועדף — שורה אחת מ-curl ועד PNG על הדיסק:

```bash
curl -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d '{
    "model": "gpt-image-2",
    "prompt": "<the prompt>",
    "size": "1024x1024",
    "quality": "medium",
    "output_format": "png"
  }' | jq -r '.data[0].b64_json' | base64 --decode > <output-path>.png
```

החלף `<the prompt>` ו-`<output-path>` לערכים שלך.

## Python fallback ל-decode

ב-Git Bash על Windows, `jq` ו-`base64` לא תמיד מותקנים. אם הקריאה הראשונה נכשלת ב-`jq: command not found` או דומה — עבור ל-fallback הבא:

```bash
BODY='{"model":"gpt-image-2","prompt":"<the prompt>","size":"1024x1024","quality":"medium","output_format":"png"}'
curl -sS -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d "$BODY" -o /tmp/img.json

python -c "import json,base64,sys; d=json.load(open('/tmp/img.json')); open(sys.argv[1],'wb').write(base64.b64decode(d['data'][0]['b64_json']))" <output-path>.png
```

אם גם `python` חסר — דווח לראובן ועצור. **אל תנסה להחליף את שם המודל כפתרון.**

## פרמטרים

| שדה | ערכים אפשריים | ברירת מחדל מומלצת |
| --- | --- | --- |
| `model` | `gpt-image-2` בלבד | `gpt-image-2` |
| `prompt` | מחרוזת חופשית, רצוי < 4000 תווים | — |
| `size` | `1024x1024`, `1536x1024`, `1024x1536` | `1024x1024` |
| `quality` | `low`, `medium`, `high` | `medium` |
| `output_format` | `png`, `jpeg`, `webp` | `png` |

לקאברים של מאמרים מומלץ `1536x1024` (landscape). לאיורים בתוך מאמר — `1024x1024`.

## שגיאות נפוצות

| קוד | משמעות | תיקון |
| --- | --- | --- |
| `401` | API key לא תקין או חסר | בדוק `.env` ושטעינה הצליחה |
| `400` | פרמטר לא חוקי | קרא את `error.message` בתגובה |
| `429` | rate limit | המתן כמה שניות ונסה שוב |
| `model_not_found` או דומה | **לא** בעיית שם מודל — כנראה גרסת SDK ישנה במקרה של שימוש ב-SDK, או שינוי בצד OpenAI | דווח לראובן. **אל תחליף ל-`dall-e-3` או `gpt-image-1`.** |

## דוגמת קריאה מלאה (end-to-end)

```bash
# 1. טעינת מפתח
set -a; source .env; set +a
[ -n "$OPENAI_API_KEY" ] || { echo "OPENAI_API_KEY missing"; exit 1; }

# 2. קריאה (Python fallback variant)
PROMPT="A watercolor illustration of a cat on a sofa, soft pastel palette, gentle morning light"
OUT="yuval/outputs/2026-05-13-cat-sofa.png"

curl -sS -X POST "https://api.openai.com/v1/images/generations" \
  -H "Authorization: Bearer $OPENAI_API_KEY" \
  -H "Content-Type: application/json" \
  -d "$(printf '{"model":"gpt-image-2","prompt":"%s","size":"1024x1024","quality":"medium","output_format":"png"}' "$PROMPT")" \
  -o /tmp/img.json

python -c "import json,base64,sys; d=json.load(open('/tmp/img.json')); open(sys.argv[1],'wb').write(base64.b64decode(d['data'][0]['b64_json']))" "$OUT"

# 3. אימות
[ -s "$OUT" ] && echo "OK: $OUT ($(stat -c%s "$OUT") bytes)" || echo "FAIL"
```

## מתי לא להשתמש בסקיל הזה

- אם הסוכן צריך לערוך תמונה קיימת (image-to-image) — זה endpoint אחר (`/v1/images/edits`). הסקיל הזה לא תומך בזה כרגע.
- אם הסוכן צריך תמונות מרובות — קרא לסקיל בלולאה, פעם אחת לכל תמונה.

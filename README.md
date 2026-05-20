# ECCE AskDesk Uganda — Logo Route Fix Build

This build fixes the missing logo issue without embedding the entire homepage into Python.

What changed:
- The MoES logo is served through `/assets/moes-logo.png`.
- The theme logo is served through `/assets/theme-logo.png`.
- The logos are safely embedded as base64 strings inside `app.py` only as image bytes, not as page HTML.
- This avoids the SyntaxError caused by embedding the full homepage.

## Render settings

Build Command:

```bash
python -m pip install --upgrade pip setuptools wheel && pip install -r requirements.txt
```

Start Command:

```bash
python -m uvicorn app:app --host 0.0.0.0 --port $PORT
```

Pre-deploy Command: leave empty.

Root Directory: leave empty.

## Test links after deployment

Open:

```text
https://YOUR-RENDER-LINK.onrender.com/
```

Then test:

```text
https://YOUR-RENDER-LINK.onrender.com/assets/moes-logo.png
https://YOUR-RENDER-LINK.onrender.com/assets/theme-logo.png
https://YOUR-RENDER-LINK.onrender.com/api/status
```

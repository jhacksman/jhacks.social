# CLAUDE.md - jhacks.social

Personal site for Jack Hacksman. Static HTML/CSS hosted on GitHub Pages.

## Project Structure
```
├── index.html          # Main page
├── style.css           # Styles
├── avatar.jpg          # Profile photo (400x400)
├── apple-touch-icon.png    # iOS icon (180x180)
├── favicon-16x16.png   # Browser favicon small
├── favicon-32x32.png   # Browser favicon large
└── CNAME               # Custom domain
```

## Conventions
- Dark theme with teal accent (`#00d4aa`)
- CSS variables in `:root`
- Mobile-first responsive design

## Deployment
Push to `main` → GitHub Pages auto-deploys to https://jhacks.social

## Lessons Learned

### 2026-02-03: Polish pass
1. **sips can't convert JPG→PNG** — macOS `sips` outputs the same format as input despite filename. Use `ffmpeg` instead:
   ```bash
   ffmpeg -y -i avatar.jpg -vf scale=180:180 apple-touch-icon.png
   ```

2. **OG images need absolute URLs** — Social previews require full `https://` URLs, not relative paths.

3. **Subtle animations > flashy** — Page fade-in (0.6s ease-out), avatar glow on hover, card slide on hover. All < 0.5s, no infinite loops.

4. **Commit early, commit often** — Separate commits for meta tags, favicons, CSS. Easy to revert/cherry-pick.

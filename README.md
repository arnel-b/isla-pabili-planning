# IslaPabili Kickoff Preview

A 10-slide, 3-minute preview of the IslaPabili team kickoff for Arnel, Melvs, Kelvs and Joey. It is built from `docs/kickoff-brief.md`.

Everything is in one file, `index.html`. It uses no frameworks, no build step and no external downloads, so it loads quickly on mobile data and also works offline.

## Preview it locally

**Easiest:** double-click `index.html`, or drag it into Chrome, Firefox or Edge.

**On your phone:** copy `index.html` to the phone and open it in Chrome. Or serve it from your computer over Wi-Fi:

```bash
cd presentation
python3 -m http.server 8000
```

Then open `http://<your-computer's-IP>:8000` on a phone connected to the same Wi-Fi network.

## How to navigate

| Device | Next | Previous |
| --- | --- | --- |
| Phone | Swipe left, or tap **Next** | Swipe right, or tap the back arrow |
| Computer | → arrow key, Space or Page Down | ← arrow key or Page Up |

- **Home** and **End** jump to the first and last slide.
- Each slide has its own link, for example `index.html#5`.
- On very short screens, a slide that doesn't fit shows a **More ↓** button. You can also scroll it up and down.

## Publish on GitHub Pages

> **Note:** a GitHub Pages site is **public**. Anyone with the link can open it. Private Pages need a paid GitHub plan.
> Publish only this `presentation` folder, not the whole project. The `docs/` folder and the tracker are internal planning files.

1. On GitHub, create a new repository, for example `islapabili-kickoff`.
2. Upload `index.html` and this `README.md` to the repository's root. Either:
   - use **Add file → Upload files** on the GitHub website, or
   - run these commands:
     ```bash
     cd presentation
     git init
     git add index.html README.md
     git commit -m "Add kickoff preview"
     git branch -M main
     git remote add origin https://github.com/<your-username>/islapabili-kickoff.git
     git push -u origin main
     ```
3. In the repository, open **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose **main** and **/ (root)**, then click **Save**.
5. After a minute or two, the site is live at `https://<your-username>.github.io/islapabili-kickoff/`.

To update it later, edit `index.html` and upload or push it again. GitHub Pages republishes automatically.

## Editing the slides

- Each slide is a `<section class="slide">` in `index.html`, numbered with a comment (`<!-- 1 -->` to `<!-- 10 -->`).
- Labels: `tag status` (CURRENT STATUS), `tag proposal` (PROPOSAL) and `tag decide` (TO DECIDE).
- Colors are defined at the top of the `<style>` block (`--accent`, `--bg` and so on).
- If you add or remove a slide, update the "N of 10" numbers in each slide's `aria-label`. The counter and progress bar update by themselves.

## Tested

- **Screen sizes:** headless Chrome at 360×640, 360×700, 360×800, 412×915, 768×1024 and 1366×768.
- **Navigation:** buttons, arrow, Home and End keys, swipe left and right, deep links (`#7`), and both ends of the deck.
- **Accessibility:** hidden slides are skipped by keyboard and screen readers, and the reduced-motion setting turns off all animation.
- **Errors:** no console errors.

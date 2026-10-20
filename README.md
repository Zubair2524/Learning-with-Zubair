# Quran Surahs, Shorts Library

Static site (no build step). Files:

- `index.html`: the page (design, 114 surah cards, video popup)
- `links.js`: one YouTube Short link per surah number
- `build_links.py`: fills `links.js` automatically from your channel

## 1. Fill in your links

**Automatic** (needs yt-dlp: `pip install yt-dlp`):

```
yt-dlp --flat-playlist --print "https://www.youtube.com/shorts/%(id)s|%(title)s" "https://www.youtube.com/channel/UCQL8GLFAW2RzhF_TjI5-7Dw/shorts" > shorts.txt
python3 build_links.py shorts.txt
```

The script matches each title to a surah by number ("Surah 36") or name ("Yaseen") and
prints anything it couldn't match so you can paste it into `links.js` by hand.

**Manual**: open `links.js` and paste each URL between the quotes. Surahs left as `""`
show as "Coming soon".

## 2. Publish on GitHub Pages (free)

1. Create a new public repo, e.g. `quran-surahs`.
2. Upload `index.html` and `links.js` (the other files are optional).
3. Repo → Settings → Pages → Source: "Deploy from a branch", Branch: `main`, folder `/ (root)`.
4. Your site goes live at `https://<username>.github.io/quran-surahs/` in about a minute.

Alternatives with the same free tier and drag-and-drop upload: Netlify Drop, Cloudflare Pages, Vercel.

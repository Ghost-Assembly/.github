# .github

The Ghost Assembly organisation profile.

`profile/README.md` is what GitHub shows at the top of
<https://github.com/Ghost-Assembly>. Keep its project list in step with the website
(`docs/index.html` in
[ghost-assembly.github.io](https://github.com/Ghost-Assembly/ghost-assembly.github.io)).

`profile/banner.png` is built from that repository's `assets/logo-source.png`, with the
emblem beside the wordmark on the site's background colour:

```bash
S=../ghost-assembly.github.io/assets/logo-source.png
magick \( -size 1280x360 xc:'#03030a' \) \
  \( +gravity $S -crop 830x830+215+64 +repage -resize 280x280 \) -gravity west -geometry +150+0 -composite \
  \( +gravity $S -crop 1130x235+72+951 +repage -resize 680x \) -gravity west -geometry +470+0 -composite \
  -depth 8 -strip profile/banner.png
```

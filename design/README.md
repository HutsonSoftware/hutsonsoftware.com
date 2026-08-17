# Design source

`icon.svg` is the company mark: an H knocked out of a solid tile. Pure geometry,
no text elements, so it renders the same regardless of installed fonts. It is
the single source for every icon in `static/`.

`og-card.svg` is the source for the social card.

## Regenerating (macOS, no ImageMagick needed)

qlmanage honors the SVG's intrinsic width/height, so render from a sized copy:

```sh
sed 's|width="64" height="64"|width="512" height="512"|' icon.svg > /tmp/r.svg
qlmanage -t -s 512 -o /tmp /tmp/r.svg
for s in 180 32 16; do cp /tmp/r.svg.png /tmp/i$s.png; sips -z $s $s /tmp/i$s.png; done
```

Then copy to `static/` as `apple-touch-icon.png`, `favicon-32x32.png`,
`favicon-16x16.png`. `favicon.ico` is a PNG-payload ICO built from the 16 and 32
(see git history for the builder).

Social card: render `og-card.svg` at 1200, then `sips -c 630 1200` to crop the
square qlmanage produces down to the 1200x630 the platforms expect.

`safari-pinned-tab.svg` is deliberately the bare H, not the tile. Safari mask
icons are silhouettes, so a filled tile would render as a black square.

Not under `static/`, so these sources are not published with the site.

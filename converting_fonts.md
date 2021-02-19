# Converting fonts from woff to otf for use in your local terminal

Please do not distribute the fonts you create this way! The designers deserve to
be paid for their work according to the terms of their chosen licenses. If you
don't like the license, don't use the font in your product. However, any font
that has been made available for display in a browser, should also be able to be
used in your personal, local, terminal. Converting to otf makes that possible on
Linux and macOS (probably Windows too, but I haven't checked).

## Fetch requirements

```
[[ -d woff2otf ]] || git clone https://github.com/hanikesn/woff2otf
```

## Convert 1 font
```
font=fonts/resources/cartograph/cartograph.woff
python3 woff2otf/woff2otf.py "$font" "$(basename $font .woff).otf"
```

## Convert directory of fonts
```
font_dir=fonts/resources/cartograph
for font in "$font_dir"/*.woff; do
    python3 woff2otf/woff2otf.py "$font" "$font_dir/$(basename $font .woff).otf"
done
```

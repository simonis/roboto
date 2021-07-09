- Download the latest Roboto fonts from https://www.fontsquirrel.com/fonts/download/roboto-2014. This will give you `roboto-2014-zip`.

- Create a directory `roboto-2014` and unzip `roboto-2014.zip` into it.

- Go to https://www.fontsquirrel.com/tools/webfont-generator and upload the twelve non-condensed Roboto fonts from `roboto-2014/`. Select "Expert" mode and choose:

Extended options | &nbsp;
----------------|------------------------------------
Font Formats | TrueType, WOFF, WOFF2, EOT Lite, SVG
Truetype Hinting | Keep existing
Rendering | &nbsp;
Vertical Metrics | No Adjustment
Fix Missing Glyphs | &nbsp;
X-height Matching | None
Protection |
Subsetting | No Subsetting
OpenType Flattening |
CSS | Style Link
Advanced Options |

- Clicking on "Download" will give you a file which you can save as `roboto-2014-webfontkit.zip`. Create a directory `roboto-2014-webfontkit` and unzip `roboto-2014-webfontkit.zip` into it. Copy the generated `stylesheet.css` to `roboto-2014.css` and edit as follows.

- Rename the `font-family:` from "roboto" to "Roboto".

- Run `for f in *.ttf; do ls $f; ttfdump $f | grep usWeightClass; done` on the True Type Fonts to get the native weight of the fonts (see: https://docs.microsoft.com/en-us/typography/opentype/spec/os2#usweightclass):

font name | `usWeightClass` | &nbsp;
----------|------|------
roboto-black | 900 | Black
roboto-bold | 700 | Bold
roboto-medium | 500 | Medium
roboto-regular | 400 | Normal
roboto-light | 300 | Light
roboto-thin | 250 | Extra-light

- This can easily be mapped to the (CSS `font-weight` property)[https://www.w3schools.com/cssref/pr_font_weight.asp]. NOTICE: CSS only knows values which are a multiple of 100! We must therefore map "250" to "200" otherwise the invalid value "250" will be ignored and interpreted as "normal" (i.e. "400").

`font-weight` | &nbsp;
--------------|-------
normal |
bold |
bolder |
lighter |
100 |
... |
400 | normal
... |
700 | bold
... |
900 |

- Do the same for the six "condensed" fonts under `roboto-2014/` and create `robotocondensed-2014.css` under `robotocondensed-2014/` (rename the `font-family:` from "roboto_condensed" to "Roboto Condensed").

- For testing purpose, you can disable the "Same-origin policy for file: URIs" policy by setting the `security.fileuri.strict_origin_policy` preference to false https://developer.mozilla.org/en-US/docs/Archive/Misc_top_level/Same-origin_policy_for_file:_URIs

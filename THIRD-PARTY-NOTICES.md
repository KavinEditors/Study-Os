# Third-Party Notices

StudyOS uses third-party open-source software and third-party font
resources. The StudyOS source code itself is licensed separately under
the project's `LICENSE` file.

This notice records the third-party components referenced by the current
`StudyOS_Premium_Chat_First.html`.

> **Important:** This file is an attribution index, not a replacement
> for the original license files supplied by the respective projects. If
> a third-party component is redistributed locally, keep the component's
> original license/notice files with that component where applicable.

------------------------------------------------------------------------

## 1. Marked

**Version referenced by StudyOS:** `15.0.7`\
**License:** MIT License\
**Usage:** Markdown parsing and rendering.

StudyOS loads Marked from jsDelivr:

``` html
https://cdn.jsdelivr.net/npm/marked@15.0.7/marked.min.js
```

Copyright notice:

``` text
Copyright (c) 2018+, MarkedJS.
Copyright (c) 2011-2018, Christopher Jeffrey.
```

Marked is distributed under the MIT License.

**Project:** https://github.com/markedjs/marked

------------------------------------------------------------------------

## 2. DOMPurify

**Version referenced by StudyOS:** `3.2.6`\
**Licenses:** Apache License 2.0 and Mozilla Public License 2.0\
**Usage:** Sanitizing HTML generated from Markdown.

StudyOS loads DOMPurify from jsDelivr:

``` html
https://cdn.jsdelivr.net/npm/dompurify@3.2.6/dist/purify.min.js
```

The distributed DOMPurify 3.2.6 build identifies itself as:

``` text
DOMPurify 3.2.6
(c) Cure53 and other contributors
Released under the Apache license 2.0 and Mozilla Public License 2.0
```

**Project:** https://github.com/cure53/DOMPurify

When redistributing DOMPurify files, retain the license files/notices
supplied by DOMPurify.

------------------------------------------------------------------------

## 3. Tesseract.js

**Version referenced by StudyOS:** `5.x`\
**License:** Apache License 2.0\
**Usage:** OCR for images/PDF-related workflows.

StudyOS loads Tesseract.js from jsDelivr:

``` html
https://cdn.jsdelivr.net/npm/tesseract.js@5/dist/tesseract.min.js
```

Tesseract.js is distributed under the Apache License 2.0.

**Project:** https://github.com/naptha/tesseract.js

### Underlying OCR components

Tesseract.js uses the Tesseract OCR engine and related
WebAssembly/runtime components. Those components can carry their own
notices and licenses. In particular, the Tesseract OCR project notes
that it uses Leptonica, which is licensed under the BSD 2-Clause
license.

If distributing the complete Tesseract.js runtime locally, retain the
notices/licenses supplied with that distribution rather than replacing
them with the StudyOS license.

**Tesseract OCR:** https://github.com/tesseract-ocr/tesseract

------------------------------------------------------------------------

## 4. PDF.js

**Version referenced by StudyOS:** `4.10.38`\
**License:** Apache License 2.0\
**Usage:** PDF processing/rendering.

StudyOS loads PDF.js from cdnjs:

``` html
https://cdnjs.cloudflare.com/ajax/libs/pdf.js/4.10.38/pdf.min.mjs
```

PDF.js is distributed under the Apache License 2.0.

**Project:** https://github.com/mozilla/pdf.js\
**Pre-built distribution:** https://github.com/mozilla/pdfjs-dist

When redistributing PDF.js files locally, retain the Apache license and
any additional notices included with the distribution.

------------------------------------------------------------------------

## 5. Lucide

**Version referenced by StudyOS:** `0.468.0`\
**License:** ISC License\
**Usage:** Interface icons.

StudyOS loads Lucide from unpkg:

``` html
https://unpkg.com/lucide@0.468.0/dist/umd/lucide.min.js
```

Copyright notice:

``` text
Copyright (c) 2026 Lucide Icons and Contributors
```

Lucide is distributed under the ISC License.

**Project:** https://github.com/lucide-icons/lucide

If the exact Lucide distribution you are shipping contains a different
copyright notice/year, retain the notice from that distribution.

------------------------------------------------------------------------

## 6. KaTeX

**Version:** Use the version contained in the local `katex/` directory.\
**License:** MIT License\
**Usage:** Local mathematical/LaTeX rendering.

StudyOS does **not** load KaTeX from a CDN. It references the local
distribution:

``` html
./katex/katex.min.css
./katex/katex.min.js
./katex/contrib/auto-render.min.js
```

KaTeX copyright notice:

``` text
Copyright (c) 2013-2020 Khan Academy and other contributors
```

KaTeX is distributed under the MIT License.

**Project:** https://github.com/KaTeX/KaTeX

### Important

Do **not** replace KaTeX's license with the StudyOS `LICENSE`.

If KaTeX is redistributed in the repository, keep its original `LICENSE`
file and the complete KaTeX distribution, including its required font
resources.

Recommended structure:

``` text
katex/
├── LICENSE
├── katex.min.css
├── katex.min.js
├── contrib/
│   └── auto-render.min.js
└── fonts/
    └── ...
```

------------------------------------------------------------------------

# 7. Google Fonts

StudyOS currently references two Google Fonts:

-   **Inter**
-   **Space Grotesk**

They are loaded remotely through Google Fonts:

``` html
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&family=Space+Grotesk:wght@400;500;600;700&display=swap" rel="stylesheet">
```

## Inter

**License:** SIL Open Font License 1.1\
**Copyright:** Copyright 2016 The Inter Project Authors

**Project:** https://github.com/rsms/inter

The Inter project identifies the font as licensed under the SIL Open
Font License 1.1.

If Inter font files are later bundled inside StudyOS, include the
applicable copyright notice and OFL 1.1 license with the bundled font
files.

## Space Grotesk

**License:** SIL Open Font License 1.1\
**Copyright:** Copyright 2020 The Space Grotesk Project Authors

**Project:** https://github.com/floriankarsten/space-grotesk

If Space Grotesk font files are later bundled inside StudyOS, include
the applicable copyright notice and OFL 1.1 license with the bundled
font files.

------------------------------------------------------------------------

# 8. License Summary

  Component         Version in current HTML License                How StudyOS uses it
  --------------- ------------------------- ---------------------- --------------------------
  Marked                             15.0.7 MIT                    Markdown parser
  DOMPurify                           3.2.6 Apache-2.0 / MPL-2.0   HTML sanitization
  Tesseract.js                          5.x Apache-2.0             OCR
  PDF.js                            4.10.38 Apache-2.0             PDF rendering/processing
  Lucide                            0.468.0 ISC                    UI icons
  KaTeX                       Local version MIT                    LaTeX/math rendering
  Inter                        Google Fonts OFL-1.1                Interface font
  Space Grotesk                Google Fonts OFL-1.1                Display font

------------------------------------------------------------------------

# 9. Relationship to the StudyOS License

The root `LICENSE` file applies to the original StudyOS code, not to
third-party software.

Third-party components remain under their respective licenses listed
above.

Nothing in the StudyOS license grants additional rights to third-party
software, fonts, or other third-party materials.

------------------------------------------------------------------------

# 10. Current Dependency Sources

For reference, the current HTML contains these external resources:

``` text
Google Fonts:
https://fonts.googleapis.com/

Marked 15.0.7:
https://cdn.jsdelivr.net/npm/marked@15.0.7/marked.min.js

DOMPurify 3.2.6:
https://cdn.jsdelivr.net/npm/dompurify@3.2.6/dist/purify.min.js

Tesseract.js 5:
https://cdn.jsdelivr.net/npm/tesseract.js@5/dist/tesseract.min.js

PDF.js 4.10.38:
https://cdnjs.cloudflare.com/ajax/libs/pdf.js/4.10.38/pdf.min.mjs

Lucide 0.468.0:
https://unpkg.com/lucide@0.468.0/dist/umd/lucide.min.js

KaTeX:
Local files under ./katex/
```

------------------------------------------------------------------------

## Verification note

This notice was prepared against the current
`StudyOS_Premium_Chat_First.html` dependency references. The exact
third-party license text and copyright notices should be taken from the
exact package/distribution versions actually redistributed with the
project.

If a dependency is upgraded, review this file again and update its
version and licensing information.

------------------------------------------------------------------------

**StudyOS --- Third-Party Notices**\
Last reviewed: 2026

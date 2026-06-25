# Layout And Export QA Reference

## Format Choice

Use HTML when:

- Figures and text need precise composition.
- The user wants clean PDF output from a browser.
- Font fallback, page breaks, and image grouping matter.
- A pure-image PDF may be needed.
- The report needs a self-contained, reproducible source file that can be audited before export.

Use DOCX when:

- The official template must remain editable.
- The user will manually revise in Word.
- Track changes/comments are part of review.

Use PPTX when:

- The result is a deck, poster, or visual board.
- The user wants to tune layout manually in PowerPoint/Keynote.

## Privacy-Safe Layout Rules

- Keep private names, account identifiers, API keys, tokens, private URLs, student IDs, real addresses, phone numbers, and email addresses out of visible screenshots and captions.
- Redact before export, not after, whenever possible so the source document is also safe to share.
- Avoid cloud conversion or external upload tools for reports containing private project evidence unless the user explicitly approves that tool and scope.
- Do not place private screenshots or logs in reusable examples, public README files, or skill publication folders.
- For medical, financial, legal, or education content, use synthetic data or tightly cropped UI evidence unless the user has provided sanitized assets.

## HTML Report Rules

- Use A4 page containers with explicit print CSS.
- Use system font stack such as `-apple-system`, `BlinkMacSystemFont`, `Segoe UI`, `PingFang SC`, `Microsoft YaHei`, sans-serif.
- Keep body text readable: usually 10.5-12pt for A4, larger for poster-style pages.
- Use first-line indent for long Chinese prose unless the design intentionally uses block spacing.
- Avoid huge decorative cards for serious reports.
- Keep author/team area visible and not overlapping images.
- Prevent title wrapping by reducing phrase length before shrinking font aggressively.
- Use captions or in-text cross references consistently.
- Keep public report source assets in a clearly separated folder from private raw screenshots.

## Image Handling

- Crop simulator or device screenshots consistently.
- Remove irrelevant status bars only when it improves clarity and does not hide important state.
- Group tutorial/onboarding screenshots when they prove a sequence.
- Keep AI-generated images small unless they are highly reliable; large AI images expose defects.
- Avoid heavy shadows around screenshots if the source already has clean transparent or white backgrounds.
- Do not let images overlap author fields, headings, captions, or page numbers.
- Confirm each selected image has a purpose; remove repeated images that do not support a distinct claim.
- Track source path, redaction status, and final caption in the asset manifest.

## PDF Export Checks

Standard PDF:

- Open the PDF and inspect every page.
- Check file size against submission limit.
- Confirm text selection works if needed.
- Confirm fonts render as intended.
- Confirm images are not blurry.
- Confirm no page exposes secrets, personal data, private repository URLs, debug consoles, or unrelated user assets.

Image-only PDF:

- Render each page to image or export raster pages.
- Confirm text layer is absent when that is the goal.
- Confirm page count matches standard PDF.
- Confirm file size is acceptable.
- Confirm no page has clipping, missing images, or color shifts.
- Confirm rasterization did not reveal hidden layers, comments, notes, or off-canvas private content.

## Common Failure Fixes

- Author overlap: use a dedicated author block or vertical side rail; reduce hero image, not body text.
- Body too small: reduce image area or page count pressure before shrinking text.
- AI image too dominant: scale down and pair with concrete product screenshots.
- Tutorial screenshots messy: overlap them as a controlled sequence or use one representative image plus bullets.
- Black conclusion card too heavy: move personal statement into lighter prose above the final summary.
- Title line breaks: shorten headings and use two-level title/subtitle hierarchy.
- Empty white space: add a small evidence card, quote, metric, or figure; do not add decoration only.
- Sensitive screenshot: crop to the relevant UI state, replace with synthetic data, or use a diagram/table instead.

## Verification Commands

Use available local tools. Examples:

- Inspect PDF metadata/page count with `pdfinfo`.
- Render PDF pages with Poppler tools when available.
- Use browser print preview or Playwright screenshots for HTML.
- Use `du -h` or `ls -lh` to check file size.
- Use OCR or text extraction only if the text layer matters.
- Use local image or PDF tools for redaction checks; avoid uploading private reports to third-party validators.

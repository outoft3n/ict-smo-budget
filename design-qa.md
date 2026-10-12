# Editorial refresh design QA

**Source visual truth:** [selected split-layout concept](design/selected-concept.webp), generated from the user's homepage screenshot. Source image: 1487 × 1058 pixels.

**Implementation:** [desktop capture](design/home-desktop.webp), 1440 × 1024 pixels at a 1440 × 1024 CSS viewport and device scale factor 1. The source was center-fitted to 1440 × 1024 for comparison; the small edge crop is excluded from judgments.

**State:** Homepage with all four form choices, default light theme. Chrome headless captured the local preview at `http://127.0.0.1:8765/`. The in-app Browser tool was unavailable, so Chrome was used for capture.

**Full-view comparison:** [source and implementation together](design/comparison.webp). The left introduction, divider, two-column choices, whitespace, and restrained teal/gold palette are aligned with the selected concept.

**Focused comparison:** [first choice side by side](design/detail-comparison.webp). The document title, description, number marker, and action hierarchy are readable and similarly spaced. The concept's gold arrow is a visual exploration detail; the existing text arrow is retained in the implementation.

**Findings:** No remaining P0, P1, or P2 differences. The concept shows a slightly larger gold arrow treatment than the implementation (P3 polish). The site uses the repository's actual logo rather than the generated concept's approximation.

**Fidelity review:**

- Typography: Headline, form titles, body copy, and actions form a clear scale; the supplied TH Sarabun document fonts are unchanged.
- Spacing and layout: Intro and four choices align with the concept at desktop size. [Phone](design/home-mobile.webp) and [tablet](design/home-tablet.webp) captures show the intended stacked and two-column layouts.
- Colors: Dark teal text, pale mint surfaces, and a thin gold accent stay within the existing identity.
- Images: The real logo is crisp; the subtle corner motif is a generated raster asset with transparency.
- Copy: All four titles, descriptions, and destinations remain the repository's original content.

**Interaction and print checks:** Chrome confirmed four destinations, first-link Tab focus, sample data loading, print-button invocation, and no horizontal overflow at 390, 800, or 1440 CSS pixels. It reported no script exceptions. Chrome generated A4 PDFs from the previous commit and this revision; their rendered budget pages were pixel identical.

**Comparison history:** The first capture showed the intro too low and the choices too small. Aligning the intro to the top, widening the left column, and increasing choice height resolved those P2 differences. A focused comparison then showed undersized number markers and text; both were increased. The final full-view and focused comparisons above were captured after these fixes.

## Form-page extension: selected Option 1

**Source visual truth:** [Option 1 concept](design/form-option-1.webp), normalized from the selected 1487 × 1058-pixel generated image to 1440 × 1024 pixels. The concept's A4 content is illustrative; the repository's actual documents are authoritative.

**Implementation:** [empty application form](design/application-desktop.webp), 1440 × 1024 pixels at a 1440 × 1024 CSS viewport and device scale factor 1. Both images were placed in [one full-view comparison](design/form-comparison.webp) and a [focused header and form comparison](design/form-header-detail.webp). State: English, new club, empty fields, light theme. Chrome headless captured the local preview. It loaded current files with cache disabled.

**Findings:** No remaining P0, P1, or P2 issues. The editor is narrower than in the concept so the real, unscaled A4 preview fits at 1440 pixels. The actual document has more sections and different formatting than the concept's illustrative document; preserving it is an explicit requirement. The concept's preview-size badge and decorative header arc are omitted as P3 visual details.

**Fidelity review:**

- Typography: Teal page titles, section headings, labels, and button hierarchy follow the selected concept. The existing TH Sarabun form and document font declarations remain unchanged.
- Spacing and layout: Logo, title, and actions share a light desktop masthead. Editor and preview sit side by side at 1440 pixels. [Tablet](design/application-800.webp) and [phone](design/application-390.webp) captures show the editor first and preview below. No document-wide horizontal overflow occurred at 1440, 800, or 390 pixels on any form.
- Colors: White editing panel, mint preview stage, teal text, and thin gold rules match the landing page's palette.
- Images: The existing logo is used in the masthead. The actual logo and A4 document are unchanged. Its on-screen white background is blended with the masthead.
- Copy: Existing form titles, instructions, controls, and document content remain in place. [Budget](design/budget-1440.webp), [cancellation](design/cancellation-1440.webp), and [postponement](design/postponement-1440.webp) captures confirm the shared styling.

**Interaction checks:** Browser checks passed for all four home links and keyboard entry, form-button focus, sample loading, dynamic budget activities and application objectives, cancellation reallocation and postponement budget options, Thai letter switching, JSON save/open, print-button invocation, and return navigation. No script exceptions were observed. The visible page widths were checked at 1440, 800, and 390 pixels.

**PDF checks:** Chrome printed the same sample data before and after. The longer budget table remained 2 A4 pages; application remained 3; English cancellation and postponement remained 1 each. All 7 pages were pixel-identical at 120 dpi, and before/after embedded font-name sets matched. Thai cancellation and postponement were also printed from the committed baseline and updated branch: both stayed at 1 A4 page with pixel-identical rendering and matching font-name sets. Chrome reported the bundled TH Sarabun font loaded on each form.

**Comparison history:** The first render clipped the A4 preview at desktop width; reducing the editor track to 500 pixels fixed that P2 issue while keeping the document at its original scale. The first masthead placed actions below the title; moving them beside the title at desktop width fixed the main composition difference. Final full-view and focused comparisons above show these changes. A stale browser cache briefly hid the added masthead logo; disabling the cache confirmed the current markup and image render.

final result: passed

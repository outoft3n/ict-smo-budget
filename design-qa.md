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

final result: passed

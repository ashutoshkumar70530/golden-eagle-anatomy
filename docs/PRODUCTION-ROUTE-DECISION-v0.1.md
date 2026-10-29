# Golden Eagle Anatomy — Production Route Decision v0.1

**Decision:** Use a browser-first HTML5 learning course as the primary build path while the owner does not have access to Articulate Storyline 360. Keep content, interactions, and assessments structured so a future native Storyline rebuild remains possible.

## Why this route

- The owner currently cannot use Storyline, so a Storyline-only workflow would block production.
- The public demo can be hosted in GitHub Pages.
- A self-contained HTML5 course can be packaged as SCORM 1.2 with an LMS manifest and runtime adapter.
- The same instructional sequence can later be rebuilt natively in Storyline if desired.

## Deliverables

1. **Browser course:** Responsive HTML, CSS, and JavaScript; accessible controls; three mission explorations; scored mission challenges; final assessment; feedback; progress and retry rules.
2. **Public demo:** A non-LMS version hosted under GitHub Pages. It must clearly identify itself as a demo and must not claim LMS tracking.
3. **SCORM 1.2 package:** Course files plus `imsmanifest.xml`, SCORM 1.2 runtime integration, completion status, score, and resume state. This package must be tested in SCORM Cloud or an equivalent LMS before release.
4. **Asset/credit register:** Exact file/source, author, license, attribution, modifications, and usage notes.
5. **QA report:** Functional, content, accessibility, cross-browser, and SCORM test results.

## Runtime design

- Prefer vanilla HTML/CSS/JavaScript; avoid dependencies and build tools unless required.
- Keep core content and assessment data in structured objects separate from presentation.
- Use keyboard-operable buttons and controls; visible focus; meaningful headings; alt text; text-based feedback; and reduced-motion support.
- Store local progress only in demo mode; use SCORM 1.2 API calls when launched by an LMS.
- Do not report completion until all three mission passes and the final assessment pass are satisfied.
- Final assessment: 10 items, 70% threshold, max 3 whole-assessment attempts; retain best score separately from pass status.
- Mission challenges: 5 scored items each, 80% threshold, max 3 attempts per challenge; retain best score separately from pass status.
- If mission attempts are exhausted without a pass, allow a clearly marked unscored review/practice route to revisit content and retry only if the approved progression policy permits it. Do not silently award a pass.

## SCORM 1.2 requirements

- Manifest identifies a single SCO with a launch file.
- Runtime finds `API` or `API_1484_11` parent/ancestor as appropriate; SCORM 1.2 uses `API`.
- Initialize once; handle LMS not found / API errors gracefully.
- Report `cmi.core.lesson_status` as incomplete, passed, or failed according to the tested policy.
- Report `cmi.core.score.raw` as 0–100.
- Persist resumable state using `cmi.suspend_data` within SCORM 1.2 limits; serialize a compact, versioned state object.
- Commit at meaningful milestones and on page exit; finish cleanly.
- Do not treat a GitHub Pages visit as an LMS launch.

## Scientific and rights gates

- No generated image may be used as evidence for precise anatomical labeling.
- Every labeled anatomy photo must be checked against an authoritative source.
- Every image must have a recorded reuse license and permitted distribution scope.
- The final assessment cannot be marked scientifically approved until each keyed answer and feedback statement is source-checked.
- Claims requiring expert review remain flagged; they must not be presented as expert-validated.

## Important limitation

This route produces a web-based HTML5 course and SCORM 1.2 package, not a native editable `.story` project. A native Storyline source project would require Storyline authoring software. The browser-first course can be rebuilt in Storyline later if that becomes necessary.

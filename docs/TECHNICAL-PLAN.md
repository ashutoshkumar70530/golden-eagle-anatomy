# Technical Plan

Status: **Draft for review**  
Project: Golden Eagle Anatomy  
Authoring tool: Articulate Storyline 360  
Current target: Desktop-first; mobile support deferred

## 1. Delivery routes

### A. Public portfolio demo
- Build the course in Storyline.
- Publish using **Web** output.
- Host the published files on a static web host, with GitHub Pages as the first candidate.
- Provide a short project introduction and a clear launch link.
- Test the hosted course in a real browser; do not rely on opening the output directly from a local folder.
- The public demo will not provide LMS reporting.

### B. LMS package
- Publish separately from Storyline using **SCORM 1.2**.
- Configure completion and score reporting against the agreed final assessment.
- Upload the ZIP to a SCORM test environment such as SCORM Cloud, then test again in the target LMS when known.
- Verify launch, score, completion, resume, and relaunch behavior.

## 2. Repository layout

- `docs/`: project brief, architecture, science references, QA, release notes.
- `src/`: approved custom components only; prefer native Storyline interactions when practical.
- `assets/`: redistributable assets only.
- `licenses/`: source, author/creator, license, attribution wording, download date, and redistribution notes.
- `web-demo/`: public introduction and the web-published course output, after hosting tests and asset review.
- `scorm/`: instructions and test notes. Keep generated ZIPs out of version control unless there is a clear reason and all included assets can be redistributed.

The editable Storyline project should remain local/private unless deliberately approved for public release.

## 3. Hosting compatibility check

GitHub Pages is a candidate, not yet a confirmed solution. Before selecting it:
1. Publish a minimal Storyline test project using Web output.
2. Upload the complete published output without renaming or omitting runtime files.
3. Launch the Storyline `story.html` entry point on the hosted site.
4. Test navigation, media, fonts, interactions, browser refresh, and any custom web objects.
5. Check browser console/network errors if something fails.
6. Confirm the repository and all included assets are suitable for public distribution.

Do not simply upload the SCORM ZIP and expect it to behave as a public website. Web and LMS outputs serve different purposes.

## 4. Custom code policy

Use native Storyline features by default. Add custom HTML/CSS/JavaScript only when it provides a clear learning or interaction benefit and can be maintained and accessibility-tested. Any custom component needs keyboard, focus, responsive-layout, browser, and failure-state testing.

## 5. Scientific and licensing controls

- Verify anatomy terminology, functions, and visual representation using reliable ornithology, university, museum, wildlife-organization, or field-guide sources.
- Keep learner-facing source notes and a complete reference list.
- Track asset licenses separately from scientific references.
- Never include an asset in this public repository unless its license permits the intended redistribution.

## 6. Decisions still open

- Target LMS, if any.
- Hosting decision after the Storyline Web-output test.
- Browser/operating-system test matrix.
- Final completion/reporting settings after the assessment design is approved.
- Whether any custom code is actually necessary.

## 7. Release gates

Do not release until scientific accuracy, licensing, course navigation, assessment behavior, accessibility checks, public hosting, and SCORM tracking have been reviewed.

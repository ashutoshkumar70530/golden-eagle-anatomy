# Golden Eagle Anatomy — Storyline Implementation Specification v0.1

**Target authoring tool:** Articulate Storyline 360  
**Target LMS output:** SCORM 1.2  
**Status:** Implementation design; validate against the actual Storyline version and LMS test results before release.

## 1. Build strategy

Use native Storyline slides, layers, states, triggers, and question slides wherever practical. Use custom JavaScript only where Storyline cannot meet a documented requirement reliably. Any custom code must be documented and tested for keyboard use, focus management, browser compatibility, and SCORM behavior.

The course is desktop-first. Avoid fixed-position assumptions that prevent later adaptation to tablet/mobile. The public web demo is a separate publish target and is not a substitute for SCORM testing.

## 2. Suggested Storyline structure

1. Opening and interaction orientation
2. Mission hub
3. Mission 1 briefing, exploration, challenge, result/review
4. Mission 2 briefing, exploration, challenge, result/review
5. Mission 3 briefing, exploration, challenge, result/review
6. Final assessment instructions
7. Ten-question final assessment
8. Final result / completion
9. Sources and credits

Use layers and states for hotspot explanations, zoomed views, and feedback where this simplifies navigation. Ensure learners can close a layer and return to the same context without losing progress.

## 3. Variable model

Variable names below are a proposed convention; confirm the exact variable list during implementation.

### Course state
- `vCourseStarted` — Boolean; set when the learner begins.
- `vMission1Passed`, `vMission2Passed`, `vMission3Passed` — Boolean mission pass flags.
- `vMission1Best`, `vMission2Best`, `vMission3Best` — Number; best mission challenge score, 0–5.
- `vMission1Attempts`, `vMission2Attempts`, `vMission3Attempts` — Number; attempts used, 0–3.
- `vMission1Unlocked`, `vMission2Unlocked`, `vMission3Unlocked` — Boolean unlock flags.
- `vFinalAttempts` — Number; complete final-assessment attempts used, 0–3.
- `vFinalBestScore` — Number; highest final score, 0–100.
- `vFinalPassed` — Boolean; set true once a passing attempt is achieved.
- `vCourseComplete` — Boolean; true only when all missions are passed and the final assessment is passed.
- `vReviewMode` — Boolean; whether the learner is reviewing explanations rather than taking a scored attempt.

### Attempt-local state
Use question-slide variables or native question tracking for current answers. Reset attempt-local selections at the start of a new challenge attempt without clearing retained best scores, passed mission flags, or final-attempt history.

## 4. Mission challenge logic

Each mission challenge has five scored items and permits a maximum of three attempts.

1. Start the attempt only when the learner enters the challenge.
2. Present five items; score each as 1 or 0.
3. At submission, compare attempt score with the retained best score and update the best score only if the new score is higher.
4. If score >= 4, set the mission passed flag true and unlock the next mission (or final assessment after Mission 3).
5. If score < 4 and attempts remain, show a review layer and offer retry.
6. If attempts are exhausted without a pass, show the review path and the documented next step. Do not silently unlock the next mission.
7. Retrying resets only attempt-local answers and current attempt score.

**Decision required during build:** The approved policy states a maximum of three attempts per challenge. To avoid blocking learners who fail all three, choose a transparent recovery policy before implementation: (A) restart the course after reviewing, (B) allow a clearly labelled instructor/admin reset in LMS settings where possible, or (C) offer an unscored practice/review path while keeping the mission locked. Recommended default for a self-paced public demo: option C, with a clearly explained status.

## 5. Final assessment logic

- Ten scored items, one point each; passing threshold 7/10.
- Permit a maximum of three complete assessment attempts.
- On submission, convert raw score to percentage (raw score × 10).
- Update `vFinalBestScore` only if the new percentage is higher.
- Set `vFinalPassed` true when any attempt reaches 70% or above; once true, it remains true.
- If an attempt fails and attempts remain, provide targeted review before the next attempt.
- After the third failed attempt, show the exhausted-attempt state and a transparent next step.
- Do not accidentally let learners reset the assessment attempt counter by revisiting the instructions slide.
- The final best score and pass status are separate values. Confirm whether the chosen LMS and Storyline reporting settings can submit both as intended; SCORM 1.2 LMS support varies.

## 6. Course completion and SCORM mapping

Completion condition: all three mission pass flags are true AND the final assessment pass flag is true.

Configure Storyline reporting to use the final assessment result for the score, while completion status reflects the agreed course completion rule. Validate the actual mapping of SCORM 1.2 lesson_status, raw score, suspend_data, and resume behavior in the test LMS. Do not assume a custom variable automatically maps to an LMS field.

Test these scenarios:
1. Learner exits after S05 and resumes.
2. Learner fails a mission once, retries, and passes.
3. Learner reaches three failed mission attempts.
4. Learner passes all missions but fails the final assessment.
5. Learner fails final attempt 1 and passes attempt 2.
6. Learner scores higher on an earlier final attempt than a later attempt.
7. Learner exits during final assessment and resumes.
8. Learner completes all requirements and reopens the course.
9. LMS receives a completion status and score consistent with the test result.
10. Public web demo runs without assuming LMS APIs are present.

## 7. Accessibility requirements

- All hotspots must have a keyboard-operable equivalent and a visible focus state.
- Provide a labelled list of structures as an alternative to locating tiny hotspots.
- Every layer must have a predictable close/return path.
- Keep focus order logical and ensure controls have meaningful names.
- Provide text alternatives for meaningful images and text equivalents for image-based prompts.
- Do not use colour alone to convey correctness, status, or structure identity.
- Do not make hover the only route to essential information.
- Respect reduced-motion needs by keeping animations brief and nonessential.
- Test with keyboard-only navigation and screen reader; document what was actually tested.

## 8. QA acceptance criteria

A build is not release-ready until:
- All labels and claims have been scientifically reviewed.
- Every asset has confirmed reuse rights and attribution.
- Challenge scoring, retry limits, best-score retention, unlocks, and final-attempt limits pass the test matrix.
- Keyboard access, focus, contrast, text alternatives, and layer close behavior pass manual checks.
- SCORM 1.2 launch, completion, score, suspend/resume, and relaunch behavior are tested in a real test environment.
- Public web output and SCORM output are tested separately.
- Any known limitations are documented; do not claim full WCAG conformance without a formal evaluation.

# Golden Eagle Anatomy — Content and Assessment Blueprint

**Project:** Golden Eagle Anatomy  
**Studio:** Ashutosh Kumar E-Learning  
**Status:** Production draft v0.1 — scientific review required before learner-facing release  
**Delivery target:** Articulate Storyline 360; SCORM 1.2 package plus separate public web demo  
**Audience:** Beginners with no prior bird-anatomy knowledge  
**Target duration:** 15–20 minutes

## 1. Learning purpose

Learners will recognize major external anatomical structures of the Golden Eagle (*Aquila chrysaetos*), explain selected functions in plain English, distinguish visually similar features, and relate selected external structures to supporting skeletal anatomy.

### Learning objectives

By the end of the experience, learners should be able to:

1. Identify principal external structures of a Golden Eagle from photographs and close-up views.
2. Explain the basic function of selected structures, including the bill, flight feathers, tail, feet, and talons.
3. Distinguish selected structures using visible anatomical evidence.
4. Connect selected external structures to relevant underlying skeletal features without requiring comprehensive skeletal knowledge.

## 2. Experience architecture

The experience uses a wildlife-explorer narrative. Each mission follows the same learning loop:

1. **Orient:** State the mission goal and what the learner should look for.
2. **Explore:** Present a high-quality, appropriately licensed photograph or scientifically reviewed illustration.
3. **Inspect:** Use selectable hotspots, magnification, and progressive labels.
4. **Retrieve:** Ask the learner to identify or distinguish a structure without showing the answer first.
5. **Explain:** Give concise corrective feedback that names the structure and explains the relevant function.
6. **Prove:** Complete a five-item mission challenge.
7. **Reflect:** Show the score and offer review of missed structures.

The course must remain understandable without narration. Essential information, instructions, and feedback are available as on-screen text.

## 3. Three-mission structure

### Mission 1 — The Hunter’s Head

**Scope:** Visible head structures, bill/beak terminology, and selected external features.

**Intended evidence:** Learner can locate the bill and other approved visible head landmarks, and explain only those functions supported by reliable references.

**Interaction pattern:** Explore a head portrait; select hotspots; compare close-up views; complete a five-item identification and discrimination challenge.

**Scientific guardrail:** Do not infer hidden internal structures from an exterior photograph. Use a verified diagram if internal bill anatomy is included. Establish a consistent learner-facing choice between “bill” and “beak”; ornithological sources commonly use “bill.”

### Mission 2 — The Flight System

**Scope:** Wing regions, primary and secondary flight feathers, tail, and major body landmarks.

**Intended evidence:** Learner can recognize selected wing and tail structures and describe their roles in flight or control at an introductory level.

**Interaction pattern:** Inspect a spread-wing or flight view; reveal labels progressively; compare wing and tail landmarks; complete a five-item challenge.

**Scientific guardrail:** Label primary and secondary feathers only on an image where their locations can be identified confidently. Do not use a generic bird illustration as proof of exact Golden Eagle plumage or age-related patterns. Plumage varies with age.

### Mission 3 — The Capture System

**Scope:** Feet, toes/digits, talons/claws, and a small number of verified supporting skeletal structures.

**Intended evidence:** Learner can distinguish the foot, digits, and talons and connect selected visible structures to the appropriate underlying bones or joints where the illustration supports the relationship.

**Interaction pattern:** Inspect a foot close-up; select structures; compare external and verified skeletal views; complete a five-item challenge.

**Scientific guardrail:** Use “talon” for the claw and “digit/toe” for the digit, while explaining terminology in plain English. Any skeletal cutaway must be anatomically reviewed; avoid implying a one-to-one visual overlay unless alignment is scientifically valid.

## 4. Assessment blueprint

### Mission challenges

Each mission has five scored items. The mission passes at **4/5 (80%)**.

| Mission | Proposed item coverage |
|---|---|
| 1. The Hunter’s Head | 2 structure-identification items; 1 function item; 2 visual-discrimination items |
| 2. The Flight System | 2 structure-identification items; 2 structure/function items; 1 discrimination item |
| 3. The Capture System | 2 structure-identification items; 1 function item; 1 external-to-skeletal relationship item; 1 discrimination item |

This is a planning allocation, not a final question bank. Item allocations may be adjusted after the source review and visual asset selection.

### Final assessment

- **Length:** 10 questions.
- **Pass threshold:** 70% (7/10).
- **Attempts:** Maximum three complete assessment attempts.
- **Score retention:** Retain the highest final-assessment score across attempts; store pass status separately.
- **Coverage:** All three missions and all four learning objectives.
- **Question quality:** Use plausible distractors based on common confusions; avoid trick wording. Provide accessible text alternatives for image-based questions.
- **Feedback:** Practice and mission challenges provide explanatory feedback. The final assessment should use a consistent feedback policy that does not reveal correct answers in a way that compromises later attempts; the exact final-assessment feedback mode must be set in the Storyline specification.

### Retry and progression rules

- Each challenge permits up to three attempts.
- Retain the best challenge score for mission progression.
- A passed mission remains unlocked after passing.
- The final assessment becomes available after all three missions are completed.
- Course completion requires all three missions and a passing final assessment.
- Do not combine repeated attempts into a cumulative score.
- If all attempts are exhausted without a pass, present a clear review path and an explicit outcome; do not silently unlock the next mission.

## 5. Proposed course screen sequence

1. Title and course entry
2. How to explore the anatomy lab
3. Mission hub / progress overview
4. Mission 1 briefing
5. Mission 1 exploration
6. Mission 1 five-item challenge
7. Mission 1 results and review
8. Mission 2 briefing
9. Mission 2 exploration
10. Mission 2 five-item challenge
11. Mission 2 results and review
12. Mission 3 briefing
13. Mission 3 exploration
14. Mission 3 five-item challenge
15. Mission 3 results and review
16. Final assessment instructions
17. Ten-question final assessment
18. Final results and completion screen
19. Sources, credits, and asset attributions

This is a sequence-level storyboard, not final screen copy. The final number of Storyline slides may differ because layers and states may implement multiple states within one slide.

## 6. Visual and interaction principles

- Dark cinematic exploration screens establish atmosphere; neutral, high-contrast close-ups support anatomical reading; challenge screens prioritize focus and legibility.
- Golden Eagle photography is the focal point. Use scientific illustrations for internal anatomy only when provenance and accuracy can be verified.
- Hotspots must have visible labels or equivalent accessible controls; never make colour or pointer hover the only way to discover information.
- Magnification must preserve context and provide a clear return to the full view.
- Avoid excessive parallax, rapid motion, and decorative effects that obscure the structure.
- Every interactive control needs a keyboard-operable equivalent, visible focus, meaningful name, and usable feedback.
- Plan for desktop first; keep layouts and interaction choices adaptable for future mobile support.
- Essential content must not depend on sound.

## 7. SCORM and technical behaviour

Target output: SCORM 1.2.

Track, where supported by Storyline and the LMS:
- Course completion status
- Final assessment score and pass/fail status
- Question-level results where supported
- Resume state / saved progress
- Mission unlock and best-attempt state within the course

Completion and success are distinct: completing the content is not automatically the same as passing the final assessment. Verify actual LMS behavior rather than assuming every LMS stores every custom variable. The public GitHub Pages demo is for portfolio viewing and does not provide LMS-grade SCORM tracking.

## 8. Scientific and release gates

Before learner-facing release:

- Verify each anatomical label and functional statement against a reliable source.
- Check species-specific details and age/plumage caveats.
- Review all external/internal anatomy overlays with a suitable subject-matter reference.
- Confirm that each image license permits the intended use and redistribution.
- Record source, creator, license, attribution, and modification details in the asset register.
- Test keyboard access, focus order, contrast, text alternatives, retry logic, progression, score retention, resume behavior, and SCORM reporting.
- Do not claim WCAG 2.2 AA conformance unless a conformance evaluation has been completed.

## 9. Open production decisions (use defaults unless evidence requires change)

1. **Final-assessment feedback:** Recommended default is concise result feedback after submission, with answer review after the attempt; provide targeted review between attempts.
2. **Final assessment score reporting:** Report the highest score and a separate passed/failed outcome; validate mapping to SCORM 1.2 status fields.
3. **Scientific review:** Obtain qualified review for detailed skeletal illustrations and any specialized anatomical claims before release.
4. **Asset selection:** Prefer public-domain or openly licensed materials with clear reuse terms; commission/create original overlays where rights or accuracy are uncertain.

## 10. Primary research starting points

- Cornell Lab of Ornithology, *All About Birds: Golden Eagle*: https://www.allaboutbirds.org/guide/Golden_Eagle
- Cornell Lab of Ornithology, *Golden Eagle Identification*: https://www.allaboutbirds.org/guide/Golden_Eagle/id
- U.S. Fish & Wildlife Service, *Golden Eagle (Aquila chrysaetos)*: https://www.fws.gov/species/golden-eagle-aquila-chrysaetos
- U.S. National Park Service, *Golden Eagle*: https://www.nps.gov/brca/learn/nature/golden-eagle.htm
- American Bird Conservancy, *Golden Eagle*: https://abcbirds.org/birds/golden-eagle/

These are initial research sources, not blanket validation for every anatomical claim. Source-specific claims and image rights must be checked individually before publication.

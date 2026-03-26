# socratic-examiner

A Claude Code skill that turns any text into a rigorous Socratic learning session.

Paste source material and Claude becomes a demanding examiner — probing mechanisms before applications, pushing for concrete examples, tracking what you got wrong, and generating Anki cards at the end.

## Install

Download `SKILL.md` and place it in your Claude Code skills directory:

```
~/.claude/skills/socratic-examiner/SKILL.md
```

Or, if you're using a plugin marketplace:

```
~/.claude/plugins/.../skills/socratic-examiner/SKILL.md
```

## Usage

Paste any text and trigger with phrases like:

- "Quiz me on this"
- "Socratic mode"
- "Help me understand this" + paste text

Optionally specify a depth level (default is 2):

```
Quiz me on this at depth 3: [paste text]
```

## What it does

**During the session**

- Assesses conceptual density upfront and sets pacing expectations
- Leads with mechanism questions ("how does this work?") before application
- Pushes for quantitative precision — not "increases" but "doubles/quadruples"
- Requires concrete examples with actual query text, numbers, named entities
- Runs Sequence Reconstruction for any multi-step pipeline (mandatory)
- Opens sessions with a Hot List Drill on previously-missed concepts
- Supports Due Questions JSON from an external FSRS spaced repetition scheduler

**At the end**

- Fragile Point Resolution — re-tests anything you got wrong before wrapping
- Self-Synthesis prompt — you identify your own gaps before the final report
- Final report with key terms, fragile points, and recommended next step
- Anki CSV export (ready to import)
- Scheduler Update JSON for complex synthesis concepts that need multi-session probing

## Depth levels

| Level | Cycles | Focus |
|-------|--------|-------|
| 1 | 2–3 | Foundations and basic mechanisms |
| 2 | 3–5 | Mechanism probing, application, examples (default) |
| 3 | 5–8+ | Prediction, counter-tests, transfer, full precision |

## Hot List

Concepts you get wrong after two attempts are added to a Hot List and drilled at the start of future sessions. They're removed only after two separate sessions with correct answers — no shortcuts.

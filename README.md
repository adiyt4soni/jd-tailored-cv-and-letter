# JD-tailored CV and cover letter

Builds one CV and one cover letter for one job description, then tests them hard before anything is sent.

**Type:** Claude Code skill · **Area:** General skills

## What it does

- A fresh agent that sees only the job ad writes the criteria checklist (essentials, core duties, desirables), and the list is frozen before any writing starts.
- Maps each criterion to true evidence from the candidate's profile as DIRECT, PARTIAL, UNKNOWN or GAP, and asks the candidate about UNKNOWNs instead of guessing.
- Writes a one-page CV (95-97% fill measured on the PDF) and a letter that argues for the hire rather than recapping the CV, with a swap test for specificity.
- Tests: three PDF text engines, a field parser, a measured coverage score against the frozen list, a blind screener for red flags, a ten-second skim and a separate honesty audit that blocks shipping.

## Guardrails

- Facts only from the candidate's profile; never writes around a real gap.
- The writer never grades its own work, and the checklist is never changed to raise the score.
- Stops honestly when the only misses left are things the candidate doesn't have, and never submits.

## When it triggers

> Build one CV and one cover letter for one job description, then test them before anything is sent - a frozen criteria checklist written blind from the JD, an evidence map from the candidate's verified facts, a one-page CV, a letter that argues rather than recaps, three PDF text engines, a measured coverage score, a blind screener and a separate honesty audit. Use when the user wants a tailored CV, a cover letter, or an application prepared for a specific role.

## What's in this repo

- `SKILL.md`: the skill itself, the file Claude or Codex reads.
- Not included: The PDF build and test scripts are not published; the skill names the checks they run.
- Written to be generic: where the skill relies on the user's own files, it names them by role, not by content.

## Install

```bash
mkdir -p ~/.claude/skills/jd-tailored-cv-and-letter
curl -fsSL https://raw.githubusercontent.com/adiyt4soni/jd-tailored-cv-and-letter/main/SKILL.md -o ~/.claude/skills/jd-tailored-cv-and-letter/SKILL.md
```

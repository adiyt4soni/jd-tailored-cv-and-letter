---
name: jd-tailored-cv-and-letter
description: Build one CV and one cover letter for one job description, then test them before anything is sent - a frozen criteria checklist written blind from the JD, an evidence map from the candidate's verified facts, a one-page CV, a letter that argues rather than recaps, three PDF text engines, a measured coverage score, a blind screener and a separate honesty audit. Use when the user wants a tailored CV, a cover letter, or an application prepared for a specific role.
---

# JD-tailored CV and cover letter

The core
idea: decide what the employer is asking for **before** writing, measure the finished CV against that frozen list,
and let a separate agent check every claim against the candidate's real record.

## 0. Rules
- **Facts come only from the candidate's profile file** (a fact bank with approved wording and dated corrections).
  Never invent a metric, tool, title, scope or result. Prototypes stay prototypes; team work stays team work.
- **Respect the profile's "never mention" list** and its list of wording that previously failed an honesty audit.
- **One CV and one letter per job description.** Never reuse a CV across roles without rebuilding from step 1.
- **The agent that writes the CV never writes the criteria**, and never grades its own work.
- **Never write around a gap.** A CV that wins the screen and fails the interview is a loss.
- Archive old versions with `mv -n`; never overwrite or delete.

## 1. Employer instructions first
Read the employer's own application instructions: requested documents and format, word limits, named selection
criteria or rubric, and any **policy on AI assistance in applications** (respect it; flag it to the user). Record the
source and date.

## 2. Blind criteria, then freeze them
- A fresh agent sees **only the job description** and writes the criteria checklist: every explicit essential, each
  separately identifiable core duty, and every desirable a CV can evidence. Keep AND/OR alternatives, "or equivalent"
  and thresholds; de-duplicate. Label each ESSENTIAL / CORE DUTY / DESIRABLE. Track eligibility questions,
  interview-only qualities and inferred advantages separately.
- It also writes the knockout rules and a one-sentence **persona line**: the person the JD wants.
- **Freeze the list before the CV is written.** Never add easy criteria, drop hard ones or split repeats to raise
  the number. If a missed criterion turns up later, version the list (v2) and reassess.

## 3. Evidence map
For each criterion: the strongest true evidence from the profile, where it will sit on the page, the exact sentence a
screener can quote, and a label: **DIRECT / PARTIAL / UNKNOWN / GAP**.
- **UNKNOWN is not GAP.** The record is silent: ask the user one focused question (what they did, for whom, with what
  tool, what result). GAP means the record confirms they don't have it.
- A confirmed GAP in an ESSENTIAL: stop and tell the user; the role probably fails its gates.
- The top three essentials go in the top third of the page.

## 4. Choose sections per job
For each block (experience entries, projects, education extras, skills), ask "does this JD reward it?" Include a
block only when it proves a criterion. Expand true experience instead of padding with irrelevant projects.

## 5. Write the CV
- **Summary:** 3 to 5 lines. Who they are in the JD's terms, the two strongest proofs, then the differentiator.
  Mirror the JD's phrases where true, but never copy the ad sentence by sentence.
- **Bullets:** action + what + how + result; numbers only from the profile; the JD's exact phrase once; spell out an
  acronym once; the locale's spelling; no first-person bullets.
- **Senior roles:** lead with what they owned and decided, as far as true. Never a title or authority they didn't
  hold.
- **Section order:** Summary first and Skills last; standard ATS headings (EXPERIENCE, PROJECTS, EDUCATION, SKILLS).
- **Format:** one page, 95-97% fill measured on the rendered PDF; content fills the page, not bigger type; no
  one-word last lines; no bullet longer than about 3 lines; dates as "Month YYYY to Month YYYY" (no dashes).
- Record the PDF's SHA-256.

## 6. Write the cover letter (same checklist, persona and evidence map)
The CV makes the evidence easy to find; the letter explains why it matters to this employer. Don't recap the CV.
1. **What must it prove?** One hiring argument and one or two examples chosen for the requirements they prove. For
   each: the situation, what the candidate personally did, a supported result, the link to the advertised work.
2. **A real reason for this role:** one company fact from the employer's own pages (source and date), connected to an
   interest the candidate has actually expressed. Never invent product use, meetings, referrals or a personal story.
3. **Write:** the employer's format first. Default 250-350 words in three or four paragraphs; 120-200 for a short
   note. Open with the role and a concrete reason to keep reading within two sentences. Plain and confident; no
   flattery, no "perfect candidate", no apology, no paragraph listing missing skills. "Dear Hiring Team" unless the
   addressee is verified.
4. **Acceptance checks (PASS/FAIL):** evidence (every fact traceable), relevance, **specificity (swap the company
   name: if the argument still works, rewrite)**, adds value beyond the CV, the candidate can talk to every line,
   consistent with the CV, reads naturally aloud, meets the employer's limits.

## 7. Test before anything is sent
| # | Test | Pass |
|---|---|---|
| T1 | Layout and hygiene check (one page, fill, fonts, no dashes, contact line) | ALL PASS |
| T2 | Text extraction through three PDF engines (for example MuPDF, pypdf, Apple PDFKit) | 100% word recall, headings in order, each date inside its own entry |
| T3 | A field parser (for example OpenResume) | name, email, phone, location, company, title, dates, school in the right fields |
| T4 | **Evidence coverage:** a fresh agent sees only the frozen checklist, the JD and the extracted text (and is told today's date). For each criterion it quotes the JD and the CV line and marks MEETS / DOES NOT MEET / UNDECIDED | COVERAGE = 10 × MEETS / total, with the raw fraction. Floor 8/10, target 9-10. List every unmet ESSENTIAL |
| T4b | Blind screener prompt | Diagnostic only: read its reasons to reject for red flags a checklist misses. One run, never re-rolled |
| T5 | Ten-second skim: a fresh agent sees the page image and the JD | A clear yes, the top two proofs named |
| T6 | **Honesty audit:** a fresh agent compares every claim in the CV and letter with the profile | Zero unsupported or inflated claims. **Blocks shipping** |

Gates (T1, T2, T3, T6, fill, employer instructions, CV-letter consistency) are PASS / FAIL / NOT CHECKED, never
averaged. Any failed or unchecked gate means the CV is **PROVISIONAL**.

## 8. Iterate honestly
- Fix every UNDECIDED or DOES NOT MEET row that has a **true** fix (reword, move it up, name the artefact). Rebuild,
  rerun the affected tests, reassess against the **same frozen list**.
- Below 10/10: ask the user one batched set of yes/no questions, one per unmet criterion, about real facts that
  would evidence it. A yes goes into the profile first, then the CV is rebuilt.
- **Honest stop:** when the only misses left are things the candidate truly lacks, stop and state the ceiling in one
  line. Below 8/10 or with an unmet essential, the user decides whether it still goes out.

## 9. Output
The CV PDF and source, the letter PDF and source, the frozen checklist, the test results table with real numbers,
both SHA-256 hashes, and any question for the user. Never submit the application; that is the user's call.

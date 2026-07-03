# The CV Harness

**One markdown file. Any AI agent. Honest, tailored applications in minutes.**

Your CV is an output. The harness is the asset.

```
job posting --+
              +--> any AI agent --> tailored ATS CV + cover letter + flagged gaps
harness.md  --+
```

---

## The problem

Most people now tailor their CV with AI the same way: paste CV, paste job ad, hope. It works once. Then the problems start.

- **Drift.** Every chat starts from zero, so every version differs. $4.2M becomes $4M becomes "multi-million." A "contributed to" quietly becomes "led."
- **Invention.** Under pressure to match a posting, models fill gaps. A certification you never earned appears. Experience gets rounded up. One hallucinated claim can end an interview.
- **Amnesia.** The detail you carefully explained last month (which projects were client-side, why that employment gap exists, which numbers are current) is gone. You re-explain your own career every single time.

The root cause: people treat the CV as the source of truth. It is not. It is a lossy, two-page compression of your career, and compressing from a compression degrades fast.

## The idea

Maintain the source, not the artifact.

A **harness** is a single markdown file that is the canonical source of truth about your career, written *for AI agents*. It contains more detail than any CV could hold, plus the rules an honest recruiter would enforce: what each role actually was, which claims are off-limits, which numbers are canonical, and how the output must be formatted.

Any agent (Claude, ChatGPT, Gemini, a local model, an automation pipeline) receives the harness plus a job posting and returns a tailored, ATS-compliant CV and cover letter. Tailoring happens by **selection and emphasis, never by invention**. The honesty is written into the file, not left to the model's mood.

| | Ad-hoc AI tailoring | Harness |
|---|---|---|
| Facts source | Whatever you paste today | One canonical file |
| Numbers | Drift between versions | Locked in a registry |
| Honesty | Model's judgment | Explicit red lines and verb rules |
| Gaps | Silently papered over | Flagged before drafting |
| Effort per application | Re-explain everything | One prompt |
| Improves over time | No | Yes, the file compounds |

## Quick start

1. Copy [`TEMPLATE.md`](TEMPLATE.md) to a **private** location and rename it (e.g., `my_harness.md`).
2. Fill it in. Budget one focused evening. The [build guide](#build-guide) below walks through it.
3. Give any AI agent the file plus a job posting with this prompt:

> You are my application agent. Attached: (1) my CV harness, (2) a job posting. Follow the harness exactly: run the workflow in Section 1, obey the red lines in Section 8, and deliver a tailored ATS CV and a one-page cover letter. Then show me the QA checklist results and any gaps you flagged.

See [`EXAMPLE.md`](EXAMPLE.md) for a complete fictional harness.

---

## Anatomy of a harness

Thirteen sections. Each exists to kill a specific failure mode.

### 0. Prime directive
One paragraph at the top that governs everything else.

> Every line you write must be defensible by the candidate in a live interview. Tailor by SELECTION and EMPHASIS, never by invention. If the job posting demands something not in this file, flag the gap to the user; do not fabricate.

Kills: invention under pressure. Agents follow the strongest, earliest instruction; make honesty that instruction.

### 1. Workflow
The ordered steps the agent must run: read the posting, extract requirements and keywords, **check hard gates before writing anything**, pick a playbook, draft, run QA, deliver.

Kills: the beautifully tailored CV for a job you are not eligible for. Gates come first so ineligibility surfaces before effort is spent.

### 2. Output requirements (ATS compliance)
Single column. No tables, text boxes, images, or icons. Standard headings. Reverse chronological. Two pages max. Spell out keyword acronyms once. Filename convention.

Kills: pretty CVs that parse as garbage in applicant tracking systems.

### 3. Style rules
Your voice, encoded: sentence length, verb strength, banned punctuation, spelling variant (US/UK), quantification habits.

Kills: generic AI voice, and style drift between documents.

### 4. Candidate profile
Contact block, education, languages, certifications. If you hold no certifications, say so explicitly: "Certifications: none. Never invent one."

Kills: wrong phone numbers and hallucinated credentials.

### 5. Positioning
Your one or two career identities, stated plainly, plus a default summary skeleton. Most careers have at least two truthful stories (e.g., the operator and the builder, the specialist and the manager). Name them so playbooks can choose which one leads.

Kills: the mushy everything-summary that fits every job and wins none.

### 6. Full experience inventory
The heart of the file. Every role, in MORE detail than any CV can hold, because **agents tailor by cutting, so the source must be oversized**. For each role include:

- Employer, dates, titles, and a one-line description of what the organization actually is.
- **Framing rules**: what the role truly was, including the perspective it was performed from. Example from the original harness (names changed):

  > CRITICAL FRAMING RULE: ACME was a CONTRACTOR that won public tenders through competitive bids. Never present the candidate as the contracting authority. Correct verbs: won, delivered, sourced. Wrong verbs: directed, awarded.

  Controlling the *verbs* is the single most effective honesty device in the file. Models inflate through verbs first.
- Bullets tagged **[CORE]** for the ones that should survive most cuts.
- A "depth available if relevant" line listing niche detail the agent can pull when a posting rewards it.

Kills: misrepresentation of roles, and the loss of detail that makes tailoring possible.

### 7. Skills bank
Grouped keyword lists (domain skills, tools, frameworks, leadership). This is the vocabulary the agent mirrors against the posting, honestly.

Kills: keyword mismatch with ATS filters, and skills invented to match a posting.

### 8. Red lines and known gaps
The section that makes the whole thing trustworthy. Numbered, explicit, non-negotiable:

- Credentials or authorizations you do not hold ("claim only what the candidate holds; nothing else, ever").
- Experience you do not have (regions, sectors, tools). State the honest counter-framing to use instead.
- Your scale ceiling ("$XXM portfolio; never inflate to multi-billion").
- Time-sensitive facts with expiry logic ("the flagship tender is live; check the current date and fix the tense").
- Anything confidential that must never appear in an application.

End with: "If tailoring pressure and honesty conflict, honesty wins. Flag the tension to the user."

Kills: the career-ending fabrication, and accidental leaks of confidential detail.

### 9. Role-type playbooks
Three to six recipes for the role families you actually apply to. Each defines: which identity leads, section order, what gets promoted or demoted, and which keywords matter.

Kills: one-size-fits-all output, and re-deciding strategy for every application.

### 10. Canonical numbers registry
Every figure you ever cite, in one table: portfolio sizes, budgets, savings percentages, team sizes, years. One value per fact.

Kills: drift. If a figure is not in the registry, it does not go in a document.

### 11. Cover letter guide
Length, structure (hook, proof, why-them + close), your default hooks per role family, and rules (mirror the posting's vocabulary; address a gap only if central; never state salary or visa status unless instructed).

Kills: the rehashed-CV cover letter and the accidental overshare.

### 12. QA checklist
A literal checklist the agent must run and show you before delivering. Include at minimum: every figure matches the registry, no invented anything, framing rules respected, tenses correct for today's date, format rules met, and anything uncertain flagged rather than silently included.

Kills: silent errors. The agent audits itself against your criteria, not its own.

### 13. Pending confirmations
Facts the agent must ask you about before relying on them: numbers that grow, statuses that change, anything you have not verified recently.

Kills: stale claims. This section is also your maintenance to-do list.

---

## Build guide

One focused evening. Work with an AI assistant; it makes steps 1 and 2 dramatically faster.

**Step 1: Brain dump (45-60 min).** Feed your existing CVs, LinkedIn profile, old proposals, and performance reviews to an assistant. Ask it to interview you role by role: what did you actually do, what were the numbers, what systems, what team, what went wrong and got fixed. Do not filter yet. Oversized is the goal.

**Step 2: Framing rules (30 min).** For each role, answer: what was this job *really*, and from whose side of the table? Write the framing rule and the verb lists (allowed / forbidden). This is where you make future misrepresentation impossible. Be brutally honest here; nobody sees this file but you and your agents.

**Step 3: Red lines (20 min).** List what you do not have: credentials, authorizations, sectors, scale. For each, write the honest counter-framing. Add expiry logic for anything time-sensitive.

**Step 4: Numbers registry (15 min).** Extract every figure from steps 1-3 into one table. Resolve conflicts now (was it 12% or 15%?). Delete every number from the inventory that contradicts the registry.

**Step 5: Playbooks and output spec (30 min).** Pick your 3-6 target role families and write the recipe for each. Then write the ATS output rules and your style rules, including your pet peeves. (The original harness bans em dashes. Yours can ban whatever you like.)

**Step 6: QA checklist and pending confirmations (15 min).** Convert your biggest fears from steps 2-4 into checklist items. List the facts that will go stale and when to re-verify them.

Then test: run it against a real posting, read the output like a hostile interviewer, and patch the harness (not the output) wherever it slipped. Two or three iterations and it stabilizes.

---

## Using it

**Per application:**

1. Gap check first (cheap, fast):
   > Run only Steps 1-2 of the harness workflow against this posting. Report: hard gates passed or failed, top keywords, which playbook applies, and what gaps you would flag. Do not draft yet.
2. If the gate check passes, draft:
   > Proceed per the harness. Deliver the CV and cover letter, then show the QA checklist results.
3. Read the flags. The flags are the product; the documents are almost a byproduct.

**Platform notes:**

- **Claude:** put the harness in a Project's knowledge or paste it once per conversation. Claude Projects make it a one-message pipeline.
- **ChatGPT:** attach the file or build a custom GPT with the harness as instructions.
- **Local / API agents:** the harness is the system prompt; the posting is the user message.

**Maintenance:**

- After every application: update Section 13 with anything the process surfaced.
- On any new fact (new number, new project, new title): update the inventory AND the registry in the same edit.
- Quarterly: re-verify the registry and expiry-sensitive claims.
- Keep it in a **private** git repo. Diffs of your registry over time are your career changelog.

---

## Design principles

1. **Selection, never invention.** Tailoring means choosing and emphasizing true things.
2. **Control the verbs.** Inflation happens verb-first. Allowed/forbidden verb lists are cheap and devastatingly effective.
3. **One registry.** A fact that lives in two places will eventually disagree with itself.
4. **Gates before drafting.** Eligibility problems must surface before effort, not after.
5. **Oversized source, compressed output.** Cutting from abundance beats padding from scarcity.
6. **The agent audits itself, against your criteria.** A QA checklist the agent must display turns silent errors into visible ones.
7. **Honesty wins ties.** Written down, in the file, at the top.

---

## Privacy warning

The harness is the most sensitive career document you will ever write. It aggregates everything, including your gaps, constraints, and red lines. That is what makes it work, and what makes it private.

- Keep it local or in a private repo. Never in a public gist, never in a shared drive.
- If you show it publicly (a post, a talk), sanitize first: mask names, mask figures, generalize red lines. Structure is shareable; substance is not.
- Be deliberate about which AI tools you feed it to, and use business/privacy modes where available.

---

## FAQ

**Is this cheating?**
The opposite. Unconstrained AI tailoring drifts toward flattering fiction. The harness exists to prevent exactly that: it hard-codes what may not be claimed. Every line survives an interview because the file forbids lines that would not.

**Will recruiters care that AI wrote it?**
The facts, framing, and judgment are yours; the agent is doing layout and selection. That is also what a professional CV writer does. The difference is your writer never forgets and never embellishes.

**One harness or several?**
One master. Playbooks (Section 9) handle variation between role families. A second file is justified only for a second language.

**How long should it be?**
150-300 lines is typical. Below 100 the agent lacks material; above 500 you are probably storing prose that belongs in the registry or playbooks.

**Which model does it need?**
Any current capable model. The file is plain markdown; there is no vendor lock-in. That portability is the point.

**Does the ATS actually parse the output?**
Section 2 forces the boring formatting that parses everywhere: single column, standard headings, no graphics. Boring is a feature.

**What if a posting requires something I lack?**
The agent flags it and stops or asks. That flag is valuable: it is the difference between spending an evening on a dead application and spending it on a live one.

---

## Repository contents

| File | Purpose |
|---|---|
| [`README.md`](README.md) | This guide |
| [`TEMPLATE.md`](TEMPLATE.md) | Blank harness, fill in and keep private |
| [`EXAMPLE.md`](EXAMPLE.md) | Complete fictional harness (Sam Carter, data analyst) |
| [`PROMPTS.md`](PROMPTS.md) | Copy-paste prompts for gap checks, drafting, and maintenance |
| [`LICENSE`](LICENSE) | MIT |

## Author

Created by **Drilon Potera**, who built the first harness because he got tired of watching AI round $145.5M to $146M.

Contributions welcome via pull request: better section patterns, playbook examples for other professions, translations.

## License

MIT. Use it, fork it, build a product on it. Just keep your own harness private.

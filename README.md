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
| Fit | Unknown until the rejection | Rated per requirement before drafting |
| First ten seconds | Whatever the model led with | Top third built to answer the posting's top 3 requirements |
| Keywords | Synonyms, or stuffing | The posting's exact words, only where true |
| Effort per application | Re-explain everything | One prompt |
| Improves over time | No | Yes, the file compounds |

## Quick start

1. Copy [`TEMPLATE.md`](TEMPLATE.md) to a **private** location and rename it (e.g., `my_harness.md`).
2. Fill it in. Budget one focused evening. The [build guide](#build-guide) below walks through it.
3. Give any AI agent the file plus a job posting with this prompt:

> You are my application agent. Attached: (1) my CV harness, (2) a job posting. Follow the harness exactly: run the workflow in Section 1, obey the red lines in Section 8, show me the fit map before drafting, and deliver a tailored ATS CV and a one-page cover letter. Then show me the QA checklist results and any gaps you flagged.

See [`EXAMPLE.md`](EXAMPLE.md) for a complete fictional harness.

---

## What moves interview odds

Honesty keeps you from losing an interview you already have. It does not get you one. These are the levers the harness pulls to get you one, and where each lives:

| Lever | Why it matters | Where |
|---|---|---|
| Apply where you fit | Effort on a long shot is effort not spent on a strong match | Fit map and verdict, Section 1 |
| Win the first ten seconds | Screeners skim the top of page one and decide | Headline (Sections 2, 5), top-third rule (Section 1) |
| Use their words | Keyword filters and tired humans both match literally | Equivalent terms (Section 7) |
| Show results, not duties | "Responsible for" tells the reader nothing they can rank you on | Bullet formula (Section 3) |
| Evidence next to every keyword | A skill listed but never shown reads as padding | Workflow step 6, QA (Section 12) |
| Pass the form | Knockout questions are scored before anyone opens the CV | Application answers (Section 14) |
| Reach a human | A note to a recruiter or contact gives the application a reader | Outreach note (Section 11) |
| Match your LinkedIn | Recruiters cross-check titles and dates | Section 2, LinkedIn sync prompt |
| Learn from results | Your own reply rate is better evidence than any advice, including this | Outcomes log (Section 15) |

None of these is a guarantee. They remove the common, avoidable reasons a qualified person gets screened out.

---

## Anatomy of a harness

Fifteen sections. Each exists to kill a specific failure mode.

### 0. Prime directive
One paragraph at the top that governs everything else.

> Every line you write must be defensible by the candidate in a live interview. Tailor by SELECTION and EMPHASIS, never by invention. If the job posting demands something not in this file, flag the gap to the user; do not fabricate.

Kills: invention under pressure. Agents follow the strongest, earliest instruction; make honesty that instruction.

A second directive follows it: honest is the floor, the interview is the goal, and relevance to this posting decides what leads. Without it, agents produce CVs that are true and forgettable.

### 1. Workflow
The ordered steps the agent must run: read the posting, split must-haves from nice-to-haves, **check hard gates before writing anything**, build the fit map, pick a playbook, draft, run QA, deliver.

The **fit map** rates every requirement MATCH (direct evidence), BRIDGE (adjacent, truthful evidence, with the bridge stated), or GAP (nothing; never filled), and ends in a verdict: STRONG, STRETCH, or LONG SHOT. The **top-third rule** then requires the headline, summary, and first two bullets to answer the posting's top 3 must-haves.

Kills: the beautifully tailored CV for a job you are not eligible for, the evening spent on a long shot, and the strong candidate whose best evidence sits on page two.

### 2. Output requirements (ATS compliance)
Single column. No tables, text boxes, images, or icons. Standard headings. A headline under the contact block. Reverse chronological. Two pages max. Spell out keyword acronyms once. The file format the posting asks for, plus a plain-text copy for web forms. Titles and dates that match your LinkedIn.

Kills: pretty CVs that parse as garbage in applicant tracking systems, and the mismatch a recruiter finds when they look you up.

### 3. Style rules
Your voice, encoded: sentence length, verb strength, banned punctuation, spelling variant (US/UK), quantification habits. Plus the bullet formula: action + scope + result, and no duty-only bullets where the inventory holds a result.

Kills: generic AI voice, style drift between documents, and the job-description CV that lists what you were responsible for instead of what changed.

### 4. Candidate profile
Contact block, education, languages, certifications. If you hold no certifications, say so explicitly: "Certifications: none. Never invent one."

Kills: wrong phone numbers and hallucinated credentials.

### 5. Positioning
Your one or two career identities, stated plainly, plus a default summary skeleton. Most careers have at least two truthful stories (e.g., the operator and the builder, the specialist and the manager). Name them so playbooks can choose which one leads.

Also list your **allowed headlines**: the one-line descriptor under your name, in the market's words, that the agent picks from to sit closest to the posting's job title. And list the ones that would overstate you, so it never picks those.

Kills: the mushy everything-summary that fits every job and wins none, and the inflated headline.

### 6. Full experience inventory
The heart of the file. Every role, in MORE detail than any CV can hold, because **agents tailor by cutting, so the source must be oversized**. For each role include:

- Employer, dates, titles, and a one-line description of what the organization actually is.
- **Framing rules**: what the role truly was, including the perspective it was performed from. Example from the original harness (names changed):

  > CRITICAL FRAMING RULE: ACME was a CONTRACTOR that won public tenders through competitive bids. Never present the candidate as the contracting authority. Correct verbs: won, delivered, sourced. Wrong verbs: directed, awarded.

  Controlling the *verbs* is the single most effective honesty device in the file. Models inflate through verbs first.
- Bullets tagged **[CORE]** for the ones that should survive most cuts.
- A "depth available if relevant" line listing niche detail the agent can pull when a posting rewards it.
- The **result** of each bullet wherever one exists: what changed, by how much, for whom. The agent cannot add a result later; a bullet stored without one can only ever become a duty line.

Kills: misrepresentation of roles, and the loss of detail that makes tailoring possible.

### 7. Skills bank
Grouped keyword lists (domain skills, tools, frameworks, leadership). This is the vocabulary the agent mirrors against the posting, honestly.

Two short lists make the mirroring safe. **Equivalent terms** are swaps that are true for you ("A/B testing = experimentation"), so the agent can use the posting's exact phrase. **Not equivalent** terms are the near-misses it must never swap ("mentored" is not "managed").

Kills: keyword mismatch with ATS filters, and skills invented to match a posting.

### 8. Red lines and known gaps
The section that makes the whole thing trustworthy. Numbered, explicit, non-negotiable:

- Credentials or authorizations you do not hold ("claim only what the candidate holds; nothing else, ever").
- Experience you do not have (regions, sectors, tools). State the honest counter-framing to use instead.
- Your scale ceiling ("$XXM portfolio; never inflate to multi-billion").
- Time-sensitive facts with expiry logic ("the flagship tender is live; check the current date and fix the tense").
- Anything confidential that must never appear in an application.
- Facts about the hiring company: only what the posting or you supplied. Models invent flattering "why you" details as readily as they invent credentials.

End with: "If tailoring pressure and honesty conflict, honesty wins. Flag the tension to the user."

Kills: the career-ending fabrication, and accidental leaks of confidential detail.

### 9. Role-type playbooks
Three to six recipes for the role families you actually apply to. Each defines: which identity leads, the headline, section order, what gets promoted or demoted, which keywords matter, and the gap these postings usually expose with its honest bridge.

Kills: one-size-fits-all output, and re-deciding strategy for every application.

### 10. Canonical numbers registry
Every figure you ever cite, in one table: portfolio sizes, budgets, savings percentages, team sizes, years. One value per fact.

Kills: drift. If a figure is not in the registry, it does not go in a document.

### 11. Cover letter and outreach guide
Length, structure (hook, proof, why-them + close), your default hooks per role family, and rules (mirror the posting's vocabulary; say something the CV does not; address a gap only if central; never state salary or visa status unless instructed).

Also the spec for a 60-90 word **outreach note** to a recruiter, hiring manager, or contact: the role, one proof fact, one ask.

Kills: the rehashed-CV cover letter, the accidental overshare, and the application nobody was expecting.

### 12. QA checklist
A literal checklist the agent must run and show you before delivering, in three groups. **Honesty:** every figure matches the registry, no invented anything, framing rules respected, tenses correct for today's date, anything uncertain flagged. **Interview odds:** the ten-second test, a keyword coverage table, a result in every bullet, most relevant bullet first. **Format:** ATS rules, length, contact details.

Kills: silent errors, and the CV that is accurate but buries its best evidence. The agent audits itself against your criteria, not its own.

### 13. Pending confirmations
Facts the agent must ask you about before relying on them: numbers that grow, statuses that change, anything you have not verified recently.

Kills: stale claims. This section is also your maintenance to-do list.

### 14. Application answers
Your true, pre-decided answers to the questions application forms ask: work authorization, sponsorship, notice period, salary policy, relocation, years of experience per skill. The agent answers from this table only, and warns you when a truthful answer is likely to be an automatic disqualifier.

Kills: inconsistent or improvised answers to knockout questions, which are scored before anyone opens the CV.

### 15. Outcomes log
One line per application: date, company, role, playbook, fit verdict, whether you sent outreach, and the result. Every ten applications, ask the agent which playbooks and verdicts are producing interviews.

Kills: repeating what is not working. It is the only section that tells you whether the rest is doing its job.

---

## Build guide

One focused evening. Work with an AI assistant; it makes steps 1 and 2 dramatically faster.

**Step 1: Brain dump (45-60 min).** Feed your existing CVs, LinkedIn profile, old proposals, and performance reviews to an assistant. Ask it to interview you role by role: what did you actually do, what were the numbers, what systems, what team, what went wrong and got fixed. For every piece of work, push for the result: what changed, by how much, who used it. Do not filter yet. Oversized is the goal.

**Step 2: Framing rules (30 min).** For each role, answer: what was this job *really*, and from whose side of the table? Write the framing rule and the verb lists (allowed / forbidden). This is where you make future misrepresentation impossible. Be brutally honest here; nobody sees this file but you and your agents.

**Step 3: Red lines (20 min).** List what you do not have: credentials, authorizations, sectors, scale. For each, write the honest counter-framing. Add expiry logic for anything time-sensitive.

**Step 4: Numbers registry (15 min).** Extract every figure from steps 1-3 into one table. Resolve conflicts now (was it 12% or 15%?). Delete every number from the inventory that contradicts the registry.

**Step 5: Playbooks and output spec (30 min).** Pick your 3-6 target role families and write the recipe for each. Collect five real postings per family first: their job titles become your allowed headlines, and their recurring phrases become your equivalent and not-equivalent term lists. Then write the ATS output rules and your style rules, including your pet peeves. (The original harness bans em dashes. Yours can ban whatever you like.)

**Step 6: QA checklist and pending confirmations (15 min).** Convert your biggest fears from steps 2-4 into checklist items. List the facts that will go stale and when to re-verify them.

**Step 7: Application answers (10 min).** Fill Section 14 with your true answers to the standard form questions. Decide your salary policy once, here, not at 11pm in a web form.

Then test: run it against a real posting and read the output twice. First like a hostile interviewer, looking for anything overstated. Then like a recruiter with ten seconds, looking for the top 3 requirements in the top third. Patch the harness (not the output) wherever it slipped. Two or three iterations and it stabilizes.

---

## Using it

**Per application:**

1. Fit check first (cheap, fast):
   > Run only Steps 1-3 of the harness workflow against this posting. Report: hard gates passed or failed, the fit map, the verdict, and which playbook applies. Do not draft yet.
2. Decide. STRONG: apply today. STRETCH: apply if you can also reach a human there. LONG SHOT: usually skip, and spend the evening on a better match.
3. Draft:
   > Proceed per the harness. Deliver the CV, cover letter, and outreach note, then show the QA checklist results.
4. Read the flags. The flags are the product; the documents are almost a byproduct.
5. Run the ten-second review and the parse test from [`PROMPTS.md`](PROMPTS.md) in a fresh conversation.
6. Send the outreach note to a recruiter, the hiring manager, or anyone you know at the company.
7. Log the application in Section 15.

**Platform notes:**

- **Claude:** put the harness in a Project's knowledge or paste it once per conversation. Claude Projects make it a one-message pipeline.
- **ChatGPT:** attach the file or build a custom GPT with the harness as instructions.
- **Local / API agents:** the harness is the system prompt; the posting is the user message.

**Maintenance:**

- After every application: log it in Section 15, and update Section 13 with anything the process surfaced.
- When a result arrives (a screen, a rejection, silence after three weeks): update the log line.
- Every ten applications: run the outcomes review prompt and adjust playbooks, headlines, or hooks. Never the facts.
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
8. **Honest is the floor; the interview is the goal.** A true CV that buries its best evidence still loses.
9. **Their words, your facts.** Use the posting's exact phrasing for anything you can prove, and nothing else.
10. **Triage before tailoring.** The best-tailored CV for the wrong job loses to an average one for the right job.
11. **Measure.** Log outcomes and let your own results change the playbooks.

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
200-350 lines is typical. Below 100 the agent lacks material; above 500 you are probably storing prose that belongs in the registry or playbooks.

**Which model does it need?**
Any current capable model. The file is plain markdown; there is no vendor lock-in. That portability is the point.

**Does the ATS actually parse the output?**
Section 2 forces the boring formatting that parses everywhere: single column, standard headings, no graphics. Boring is a feature.

**Does this guarantee interviews?**
No. It cannot make you a fit for a job you are not a fit for, and it has no control over how many people applied or who the hiring manager already knows. What it does is remove the avoidable losses: applying where you fail a gate, burying the evidence, missing the posting's words, failing a form question, and never learning which of your approaches works.

**Is mirroring the posting's keywords dishonest?**
Not when the swap is true. "Experimentation" and "A/B testing" describe the same work; using the posting's term is translation. Section 7 holds the swaps that are true for you and the ones that are not, so the agent never has to judge that under pressure.

**What if a posting requires something I lack?**
The agent flags it and stops or asks. That flag is valuable: it is the difference between spending an evening on a dead application and spending it on a live one.

---

## Repository contents

| File | Purpose |
|---|---|
| [`README.md`](README.md) | This guide |
| [`TEMPLATE.md`](TEMPLATE.md) | Blank harness, fill in and keep private |
| [`EXAMPLE.md`](EXAMPLE.md) | Complete fictional harness (Sam Carter, data analyst) |
| [`PROMPTS.md`](PROMPTS.md) | Copy-paste prompts for fit checks, drafting, review, outreach, interview prep, and maintenance |
| [`LICENSE`](LICENSE) | MIT |

## Author

Created by **Drilon Potera**, who built the first harness because he got tired of watching AI round $145.5M to $146M.

Contributions welcome via pull request: better section patterns, playbook examples for other professions, translations.

## License

MIT. Use it, fork it, build a product on it. Just keep your own harness private.

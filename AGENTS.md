# AGENTS.md

Markdown course notes for Semester 7 (e.g. `EP-361: Remote Sensing/`). Not a
git repo and no package manager. **Plain Markdown with LaTeX math — not Typst.**
The style mirrors the author's Semester 6 notes at `../Semester 6/`
(`iitbhu-sem6`), which are the canonical reference: read a subject folder there
(`CHI-322`, `CSE-465`, `MS-332`, `MS-431`) before writing new notes.

## Style source of truth

- `../Semester 6/CHI-322/midsem-README.md` and `README.md` — the closest model
  for notes: `## Part N:` units, `### N.M` sub-units, inline past-exam Q&A.
- `../Semester 6/CSE-465/README.md` — alternate structure using `## N.` units and
  `### Past Endsem Q&A:` H3 blocks; heavy comparison tables.
- `../Semester 6/MS-431/*` — image-heavy variant (`images/`), `> **Exam tip:**`
  callouts.
- `../Semester 6/CHI-322/midsem-question-papers.md` — question-bank format.

## Layout

- One folder per course (e.g. `EP-361: Remote Sensing/`). Files:
  - `midsem-README.md` — mid-semester notes with past-exam Q&A embedded inline
    (this repo's current EP-361 file).
  - `README.md` — full-semester notes (when needed).
  - `midsem-question-papers.md`, `question-papers.md` — question banks only.
  - `images/` — figure assets referenced as `![alt](images/name.png)`.
- No build step; there is no compiler. Verify by structure checks and by reading
  a rendered preview (see Verification).

## Document skeleton

```markdown
# <CODE>: <Title> — <Subtitle>

> **Scope:** one-line description of the covered material.

---

## Table of Contents

1. [Part 1: Topic](#part-1)
2. ...

---

**Master Unit Roadmap** / intro list (optional)

<a name="part-1"></a>
## Part 1: Topic

**Exam Questions Covered:** 2025 Q1(a), 2024 Q1(b)

---

### 1. Sub-unit
#### A. sub-sub-unit
```

- `---` after the title, after the TOC, before/between every `##` section.
- Numbering: `## Part N:` with `### N.` restarting per Part (CHI-322 style), or
  `## N.` units with `### N.M` (CSE/MS style). Do not mix.
- TOC links are GitHub slugs (`#part-1`, `#1-transaction-concepts`); `&` becomes
  `--`, dashes/parentheses are dropped.
- `<a name="part-N"></a>` anchors are used when the slug is unreliable.

## Formatting conventions

- Bold lead-ins with a colon: `- **Term:** definition`. Italic sub-labels:
  `*Formula:*`, `*Unit:*`, `*Note:*`, `*Applicability:*`, `*Limitation:*`.
- Nested lists: two-space indent. Use `-` (or `*` — stay consistent within a
  file) for bullets, `1.` for steps; CHI-322's mid-sem files use `-`.
- Tables always include an alignment row (`| :--- |` or `|:---:|` for
  scoreboards). "X vs Y" comparison tables are expected.
- Blockquote callouts: `> **Exam Note:**`, `> **Key Concept:**`, `> **Note:**`,
  `> **Grading:**`, `> **Physical meaning:**`.
- **Past-exam Q&A is embedded inline as a blockquote** (CHI-322 README style):

  ```markdown
  > **EXAM QUESTION — 2025 Mid-Sem — Q1(a)**
  >
  > **Q:** The question text. *(3 + 3 Marks)*
  >
  > **Answer:**
  >
  > **Part 1: ...**
  > Body ...
  > $$\text{equation}$$
  ```

  Every line of the block (including blank lines and display math) is prefixed
  with `> `. Marks go in italic parentheses: `*(3 + 3 Marks)*`.
- No emoji, no checkboxes. `---` separators throughout.

## Math / LaTeX

- Inline `$...$`; display `$$...$$` on its **own line** (inside a blockquote it is
  `> $$...$$`). Do not use Typst syntax.
- Multi-character subscripts/superscripts are braced: `$T_g$`, `$b_{s_0}$`,
  `$\epsilon_{\text{soil}}''$`. Units are upright: `$8.686\ \text{dB}$`,
  `$S \cdot \text{cm}^{-1}$`, `$\mu\text{m}$`; ranges via `$1.4 - 1.9\ \mu\text{m}$`.
- Standard LaTeX commands: `\frac`, `\dfrac` (inside tables), `\sqrt`, `\text`,
  `\cdot`, `\times`, `\pm`, `\mp`, `\le`, `\ge`, `\ll`, `\gg`, `\approx`,
  `\propto`, `\implies`, `\rightarrow`, `\Rightarrow`, `\infty`, `\langle`,
  `\rangle`, `\vec{}`, `\hat{}`, `\underbrace{}_{}`, `\begin{cases}`, `\hbar`,
  `\mathcal{}`, `\Sigma`, `^\circ`. Final results may use `\boxed{...}` or
  `\mathbf{...}`.
- Chemical formulas upright: `$\text{Fe}_2\text{O}_3$`, `$\text{NaCl}$`; simple
  ones may be `$H_2O$`, `$CO_2$`.
- No automatic equation numbering; manual tags look like `--- (Eq 1)` when
  referenced in text.
- ASCII diagrams stay in bare triple-backtick fences (``` `; no language tag).

## Verification

- There is no compiler. Check: balanced `$` and `$$` (even counts), balanced code
  fences, every table has an alignment row, and no leftover Typst syntax
  (`#let`, `#show`, `$"..."$`, `cases(`, `vec(`).
- To view the rendered result, use a Markdown/LaTeX preview (GitHub renders
  `$...$`/`$$...$$`); `pdftoppm`/`pdftotext` do not apply to Markdown.
- Grep for missing content against the source it was converted from; content
  fidelity matters more than formatting.

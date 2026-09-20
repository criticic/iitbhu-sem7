# AGENTS.md

Markdown course notes for Semester 7 (e.g. `EP-361: Remote Sensing/`). Tracked
in git (`git@github.com:criticic/iitbhu-sem7.git`); no package manager.
**Plain Markdown with LaTeX math — not Typst.**

## Layout

- One folder per course (e.g. `EP-361: Remote Sensing/`). Folder names contain a
  colon and spaces, so quote paths in shell commands. Files:
  - `midsem-README.md` — mid-semester notes with past-exam Q&A.
  - `endsem-README.md` — end-semester notes (when needed).
  - `README.md` — full-semester notes (when needed).
  - `midsem-question-papers.md`, `question-papers.md` — question banks only.
  - `images/` — figure assets referenced as `![alt](images/name.png)`.
- `.markdownlint-cli2.jsonc` — markdownlint config (see Verification).
- No build step; there is no compiler. Verify by structure checks and by
  rendering (see Verification).

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

---

<a name="exam-strategy--preparation-tips"></a>
## Exam Strategy & Preparation Tips

### 1. Revision checklist / past-paper trends / topic weightage
### 2. Preparation plan / exam-hall strategy
```

- `---` after the title, after the TOC, before/between every `##` section.
- Numbering: `## Part N:` units, `### M.` sub-units restarting at `1` inside
  each Part, and `#### A.` sub-sub-units. Do not mix schemes.
- TOC lists the Parts and the `Exam Strategy` section. Links are GitHub slugs
  (`#part-1`, `#exam-strategy--preparation-tips`); `&` becomes `--`, and
  dashes/parentheses are dropped.
- Use `<a name="..."></a>` right before a heading when the auto-slug is
  unreliable (e.g. headings containing `&`).

## Formatting conventions

- Bold lead-ins with a colon: `- **Term:** definition`. Italic sub-labels:
  `*Formula:*`, `*Unit:*`, `*Note:*`, `*Applicability:*`, `*Limitation:*` —
  but never put inline math inside those italics (see Math / LaTeX).
- Nested lists: **three-space** indent. Use `-` for bullets (stay consistent
  within a file) and `1.` for steps.
- Tables always include an alignment row (`| :--- |`, `|:---:|` for scoreboards).
  "X vs Y" comparison tables are expected. Inside cells use `<br>` for line
  breaks and `\dfrac` for fractions; escape a literal pipe as `\|`.
  *Caveat:* ASCII diagrams inside fences contain `|`, so exclude fenced blocks
  from any table check.
- Blockquote callouts: `> **Exam Note:**`, `> **Key Concept:**`, `> **Note:**`,
  `> **Grading:**`, `> **Physical meaning:**`, `> **Exam tip:**`; also seen in the
  sources: `> **Solution:**`, `> **Justification:**`, `> **Final Answer:**`. Keep
  the `> **Label:**` form and pick the label that fits.
- **Past-exam Q&A is embedded as a blockquote**, either inline next to the
  relevant unit, or grouped at the end of a Part under
  `### Solved Midterm Exam Questions` (EP-361 style). Both are fine; stay
  consistent within a file.

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
  with `>` and a space. Marks go in italic parentheses: `*(3 + 3 Marks)*`. Combine multi-part
  questions on one header (`**Q:** ... / **Q:** ...`) and use
  `**Answer Structure:**`, `**Answer Comparison:**`, or `**Solution:**` when
  those fit better than a plain `**Answer:**`.
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
  `\mathcal{}`, `\Sigma`, `^\circ`, `\lbrace`, `\rbrace`. Final results may use
  `\boxed{...}` or `\mathbf{...}`.
- Chemical formulas upright: `$\text{Fe}_2\text{O}_3$`, `$\text{NaCl}$`; simple
  ones may be `$H_2O$`, `$CO_2$`.
- **GitHub inline-math pitfalls** (verified against GitHub's own renderer — these
  make math render as literal `$`):
  - Keep the delimiters tight: no space inside (`$x$`, not `$ x $`). The opening
    `$` must be preceded by whitespace, a tab, start-of-line, or `(` — any other
    immediate predecessor breaks it: `word$x$`, `$x$and`, `-$x$`, `$x$-$y$`
    (the second span), `,$x$`, `]$x$`.
  - **Never place inline math inside an emphasis/italic span** (`*...*`, `_..._`,
    `<em>`): GitHub fails to render it. `**bold**` and plain text are safe. Fix by
    dropping the italics, or splitting the italic around the math —
    `*Step 1 (from* $L \to 2L$*):*` instead of `*Step 1 (from $L \to 2L$):*`.
    Avoid nesting `**bold**` inside `*italic*` when math is involved.
  - A span whose content opens with `(` and whose closing `$` is immediately
    followed by `)` also fails, e.g. `$(100)$)`. Restructure so the closing `$`
    is followed by space/word/other punctuation — prefer
    `**$\\{001\\}$ plane**, such as $(001)$ or $(100)$.`
  - **Display `$$...$$` must be its own block** — put a blank line before it (a
    blank `>` line inside a blockquote). Mid-paragraph `$$...$$` (a continuation
    line following text) is not recognized, and its `_{...}` subscripts then get
    parsed as emphasis. Also avoid multi-line `$$ ... \\ ... $$` blocks (e.g.
    `\begin{cases}` with `\\` row breaks) inside list items — prefer a
    single-line display formula (separate cases with `;` or `\quad`).
  - A math span whose content *begins* with `_` (subscript-only, e.g.
    `$_{\text{Subj}}$`) fails when two or more appear on a line, and `}` or `]`
    immediately before `_{` (`\text{VP}_{\text{complex}}`) turns into emphasis
    when the math is not recognized. For non-mathematical labels use HTML
    `<sub>...</sub>` (e.g. `[The house]<sub>Topic</sub>`); for real math attach a
    base or insert a space before the `_` (`\text{VP} _{\text{complex}}` — the
    space is ignored by TeX).
  - GitHub strips `\` from `\{`/`\}` inside math, so `$\{111\}$` loses the braces
    (they render as invisible grouping). **Always write literal braces doubled:**
    `$\\{111\\}$` (or equivalently `$\lbrace 111\rbrace$`), e.g. `$\\{hkl\\}$`,
    `$\\{111\\}$`, `$\\{001\\}$`. This applies in display math too. Any existing
    `\{...\}` in a notes file should be migrated to `\\{...\\}`.
  - Do not escape the delimiters (`\$`); a literal `$` also breaks the span.
- No automatic equation numbering; manual tags look like `--- (Eq 1)` when
  referenced in text.
- ASCII diagrams stay in bare triple-backtick fences (``` `; no language tag).

## Verification

No compiler. Run these checks after **every** edit. Before a large rewrite, make
sure the work is committed or staged so a bad rewrite can be recovered with
`git diff` / `git restore`.

### 1. Static structure checks

Run from the subject folder (or pass a filename):

```sh
python3 - <<'EOF'
import re, sys
path = sys.argv[1] if len(sys.argv) > 1 else "midsem-README.md"
s = open(path).read()
body, fence = [], False
for l in s.splitlines():
    if l.lstrip().startswith("```"):
        fence = not fence
        continue
    if not fence:
        body.append(l)
b = "\n".join(body)
inline = re.sub(r"\$\$.*?\$\$", "", b, flags=re.S)

def math_in_emphasis(line):
    line = re.sub(r"\$\$.*?\$\$", "", line)
    spans = [m.span() for m in re.finditer(r"\$[^$]*\$", line)]
    ch = list(line)
    for a, e in spans:
        ch[a:e] = "\x01" * (e - a)             # mask math so its '*' don't count
    masked = "".join(ch)
    stars = [m.start() + len(m.group(0)) - 1 for m in re.finditer(r"(?<!\\)\*+", masked)
             if len(m.group(0)) % 2 == 1]      # ignore ** runs and escaped \*
    stars = [p for p in stars                  # ignore list-marker stars
             if not (re.fullmatch(r"[\s>]*", masked[:p])
                     and (p + 1 >= len(masked) or masked[p + 1] == " "))]
    return sum(1 for a, _ in spans if sum(1 for p in stars if p < a) % 2 == 1)

print("fences balanced :", s.count("```") % 2 == 0)
print("$ even          :", inline.count("$") % 2 == 0, "| $$ even:", b.count("$$") % 2 == 0)
print("Typst leftovers :", bool(re.search(r"#let|#show|cases\(|vec\(", s)))
print("math in italic  :", sum(math_in_emphasis(l) for l in body), "(heuristic)")
print("$(...)$) hazard :", len(re.findall(r"\$\([^$]*\)\$\)", b)))
print("lone brace      :", len(re.findall(r"(?<!\\)\\[{}]", b)))
EOF
```

Every count must be `0` / `True` / `False` as appropriate. `math in italic` is a
heuristic with no false positives but may under-report; `$(...)$) hazard` and
`lone brace` are exact. The render-check below is the definitive test.

### 2. GitHub render-check (definitive)

Renders with the same GFM engine GitHub uses, catching the inline-math pitfalls
above. Requires an authenticated `gh`; the anonymous `api.github.com/markdown`
endpoint is rate-limited (~60/h).

```sh
# 1. render the file with GFM
python3 -c 'import json;print(json.dumps({"text":open("midsem-README.md").read(),"mode":"gfm"}))' > /tmp/payload.json
gh api --method POST /markdown --input /tmp/payload.json > /tmp/rendered.html

# 2. count math that failed to render (literal $ left outside <math-renderer>)
python3 - <<'EOF'
import re
html = open('/tmp/rendered.html').read()
stripped = re.sub(r'<math-renderer[^>]*>.*?</math-renderer>', '', html, flags=re.S)
print("rendered math blocks:", html.count("<math-renderer"))
print("FAILED math spans:", stripped.count("$"))
EOF
```

A `FAILED math spans` count greater than zero means some inline math rendered as
literal `$` — fix the offending span using the Math rules above. When a
*specific* block fails, locate it by finding the literal `$` in the rendered
HTML; the usual fixes are to separate display math with a blank line, avoid
multi-line `\\`-row blocks inside lists, or insert a space before a problematic
`_{`. Note: the API only wraps math in `<math-renderer>`; KaTeX runs in the
browser, so an unsupported command will still be "wrapped" (verify commands in a
browser).

### 3. Content fidelity

Grep for missing content against the source the file was converted from;
**content fidelity matters more than formatting**.

### 4. Markdown lint (markdownlint-cli2)

Lint every note with the repo's tuned config (`.markdownlint-cli2.jsonc`):

```sh
bunx markdownlint-cli2 "**/*.md"
```

Expect `Summary: 0 issues`. The config disables only the rules that conflict
with the notes' intentional style (long lines; inline HTML `<br>`/`<sub>`/
`<a name>`; bare ASCII fences; `---`-adjacent headings; blockquote lists;
bold/italic pseudo-headings; `<a name>` TOC anchors) — everything else must
pass.

## Workflow

- Read the **entire** file before editing; reconstruct structure without dropping
  content.
- Strip conversational artifacts when reformatting (`Here is ...`, `reply
  continue`, `Say the word ...`) — notes are not chat transcripts.
- After editing, re-run the render-check and confirm `FAILED math spans: 0`.
- This is a git repo: inspect `git status` / `git diff` before and after edits.
  Do not commit unless explicitly asked; when asked, keep commits focused and
  match the existing message style.
- Keep the repo's cross-file naming consistent (`midsem-README.md`, etc.) so
  paths resolve.

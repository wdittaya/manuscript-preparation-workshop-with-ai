# Writing & Formatting a Research Article

**Course 2022517 · Workshop date: 2026-06-21 · 09:00–16:00**
Instructor: Dittaya Wanvarie — Chulalongkorn University

A hands-on, one-day workshop for graduate students on writing and formatting a
research article in LaTeX. Everything is built around **one running example**:
a short paper on *Incoming Tourist Trends in Thailand, 2017–2024*, using the
dataset in this repository. By the end of the day you will have a real LaTeX
draft of a paper **and** a matching slide deck.

---

## Before you arrive (please prepare)

1. **Laptop** with a web browser — most work happens in the browser, nothing to install.
2. **Overleaf account** (free): https://www.overleaf.com — this is where you write and compile LaTeX.
3. **Google account** — for **Google Colab** (running Python to make figures) and **NotebookLM** (drafting the literature review). Both are free.
4. *(Optional)* **Zotero** + the browser connector: https://www.zotero.org — a reference manager. It is optional; you can also grab BibTeX directly from Google Scholar.
5. **Download `tourist-data.xlsx`** from this repository — it is the dataset for every exercise.

> **AI tools note.** Chula AIX (Central Library) subscribes to premium tiers of
> Consensus, Connected Papers, SciSpace, ChatGPT, Claude, Gemini, etc., but those
> are usable **at the library on-site only**. For this workshop, just use the
> **free version** of each tool with any account — the free tiers cover every lab.

---

## How to use this repository

- **Follow `workshop-worksheet.pdf`** step by step during the day. Each step matches a module on the slides and tells you exactly what to do.
- **`research-article-workshop.pdf`** are the lecture slides (the instructor presents these; keep them open for reference).
- The **`example-elsarticle/`** folder is the *finished* paper — your target. Peek at it if you get stuck.
- The **`exercise-beamer-solution/`** folder is the *solution* to the final exercise (turning your paper into a talk).

---

## Files in this repository

| File / folder | What it is |
|---|---|
| `README.md` | This file. |
| `workshop-worksheet.pdf` / `.tex` | **Start here.** Step-by-step student handout (Steps 1–8) with copy-paste prompts and an answer key. |
| `research-article-workshop.pdf` / `.tex` | The lecture slide deck (Beamer), 9 modules. |
| `tourist-data.xlsx` | The dataset. Two sheets: `Tourist-Number-Data` (arrivals by nationality/region, 2017–2024) and `Tourist-Expense-Data` (spending, 2017–2023). |
| `tourism.bib` | A sample BibTeX file exported from ResearchRabbit — an example of the reference database you build in Module 4. |
| `example-elsarticle/` | The completed example paper (see below). |
| `exercise-beamer-solution/` | The completed Beamer talk — solution to the final exercise. |

### `example-elsarticle/` — the finished paper
| File | What it is |
|---|---|
| `main.tex` | The article source, using the Elsevier **`elsarticle`** class. |
| `main.pdf` | The compiled paper. |
| `references.bib` | The bibliography (illustrative entries — replace with your own). |
| `arrivals.pdf` | Line chart of arrivals 2017–2024 (made in Python). |
| `gaussian_fit.pdf` | Histogram of log-arrivals with the fitted Gaussian. |

### `exercise-beamer-solution/` — the finished talk
| File | What it is |
|---|---|
| `talk.tex` | A short conference talk (Beamer) that **reuses** the paper's equation, table, and figures. |
| `talk.pdf` | The compiled talk. |
| `arrivals.pdf`, `gaussian_fit.pdf` | The same figures as the paper (copied in). |

---

## Compiling LaTeX

**Recommended: Overleaf.** Upload a folder's `.tex` and supporting files
(`.bib`, figures), set the compiler to **pdfLaTeX**, and click *Recompile*.
The `elsarticle` class is built in.

**Local (full TeX Live), from a folder:**

```bash
pdflatex main      # or research-article-workshop / talk
bibtex  main       # only needed if the document cites references
pdflatex main
pdflatex main      # run twice so cross-references settle
```

The slides (`research-article-workshop`) and the talk (`talk`) do not use BibTeX,
so just run `pdflatex` twice. The paper (`example-elsarticle/main`) needs the full
`pdflatex → bibtex → pdflatex → pdflatex` cycle.

> Build files (`.aux`, `.log`, `.pdf` intermediates, etc.) are ignored by git
> via `.gitignore`; you can safely delete them.

---

## Today's schedule (09:00–16:00)

| Time | Module |
|---|---|
| 09:00 | Welcome & overview |
| 09:15 | 1. Finding a good venue |
| 09:55 | *morning break* |
| 10:10 | 2. LaTeX & Overleaf |
| 11:05 | 3. Anatomy of a research article |
| 11:20 | 4. Literature review (part 1) |
| 12:00 | *lunch* |
| 13:00 | 4. Literature review (part 2) + reference database |
| 13:35 | 5. References & BibTeX |
| 14:00 | 6. AI for code & tables |
| 14:30 | *afternoon break* |
| 14:45 | 7. AI for figures |
| 15:20 | 8. Equations in LaTeX |
| 15:40 | 9. From paper to Beamer slides |
| 15:55 | Wrap-up & Q&A |

---

## A note on AI and academic integrity

You will use AI assistants throughout the day to draft LaTeX, build tables, and
plot figures. **You are the author and are accountable.** Always verify every
AI-generated number and citation against the source, never upload confidential
or unpublished material to public tools, and disclose AI use according to your
target venue's policy.

---

*This workshop was prepared using Anthropic Claude Opus 4.8.*

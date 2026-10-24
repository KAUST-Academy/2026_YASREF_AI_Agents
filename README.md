# KAUST Academy 2026 — AI Agents (YASREF)

Slides and labs for the **2026 KAUST Academy YASREF AI Agents Program**: five
days from a single LLM call to tested multi-agent systems.

**Course website:** <https://kaust-academy.github.io/2026_YASREF_AI_Agents/>

The site is generated from [`course.toml`](course.toml) by `build.py`, from the
KAUST Academy
[Course_Website_Template](https://github.com/KAUST-Academy/Course_Website_Template).

---

## Schedule

| Day | Topic | Slides | Labs |
|---|---|---|---|
| 1 | LLM Foundations: prompting, context and control | 2 | Prompting, Measured |
| 2 | Retrieval-Augmented Generation | 1 | RAG Pipeline · RAG Evaluation |
| 3 | Tools, Loops and Agent Architectures | 1 | Agent From Scratch · Research Agent |
| 4 | Multi-Agent Systems and Human-in-the-Loop | coming soon | coming soon |
| 5 | Testing, Patterns and Production | coming soon | coming soon |

Every lab uses Qwen3.5-4B and is written for a free **Colab T4 GPU**. The labs
need internet: they download the model and fetch their data at runtime.

---

## Repository layout

```
.
├── course.toml          # ALL site content: days, decks, labs. Edit this.
├── build.py             # the generator, standard library only
├── requirements.txt     # what the labs import
├── OFFLINE.md           # classroom delivery without internet
├── theme/               # KAUST Academy theme
├── Slides/Day_N/        # lecture PDFs
├── Labs/Day_N/          # Jupyter notebooks
└── Extra/               # optional references (empty for now)
```

---

## Updating the site

1. Drop the file in `Slides/Day_N/`, `Labs/Day_N/` or `Extra/`.
2. Add or edit its block in [`course.toml`](course.toml) and set
   `status = "ready"`.
3. Check every link resolves, then commit:

   ```bash
   python3 build.py --check     # needs Python 3.12+
   python3 build.py --serve     # preview on http://localhost:8000
   ```

Never edit the generated HTML in `_site/`; it is rebuilt every time.

Most decks are PowerPoint, and the site serves PDFs. After editing a `.pptx`,
export it again (File → Save As → PDF) over the PDF in `Slides/`. PowerPoint
leaves hidden slides out of the export.

The template's
[README](https://github.com/KAUST-Academy/Course_Website_Template#readme) covers
the rest: the offline bundle, CI, and turning on GitHub Pages.

---

## License

Licensed under [GPL-3.0](LICENSE).

> **Important:** Recording and uploading lectures online is not permitted.

# Khan Kids · Literacy item dashboards — Spring 2026

Static, single-page dashboards summarizing item-level psychometrics for the
Khan Kids phonological awareness assessments.

Live site: https://isabelandradem.github.io/rhyming/

## Layout

```
.
├── index.html      ← home page with one button per assessment
├── lit1a/
│   ├── index.html  ← LIT1a · Rhyme · EN dashboard
│   └── images/     ← p01.png, p02.png, q01.png … q18.png
└── lit1c/
    ├── index.html  ← LIT1c · Segmenting · EN dashboard
    └── images/     ← p01.png … p06.png, q01.png … q20.png
```

Each dashboard is a single HTML file with inline CSS / JS — no build step.

## Columns

Both dashboards share the same columns:

| Column | Source |
| --- | --- |
| Item | item id (e.g. `q01`); practice items tagged `practice` |
| Grade *(LIT1c only)* | age band the item targets (3YO / 4YO / KG) |
| Screenshot | thumbnail under `images/<item>.png` — click to enlarge |
| Prompt *(LIT1c only)* | verbatim item prompt from `LIT1cOrder.csv` |
| % Correct | `Item-Level Percent Correct` block of the psychometric output |
| Item-Rest | `Item-Rest Cor` from the `Reliability` block |
| Alpha if Deleted | `Omitted Reliability` from the `Reliability` block |
| Exits | raw "last item seen" counts, **shifted along administration order** |

## Note on the Exits column

The raw psychometric export reports the **last item a child saw**, which is
not the same as the item where the child exited the app. A child whose last
item was `X` actually exited when the next item appeared. Every count has
therefore been shifted by one position along the actual administration order
of the assessment:

- **LIT1a**: `p01 → p02 → q01 → q02 → … → q18`. Exits at `p01` are unknown;
  the 311 children whose last item was `q18` are treated as **completed**.
- **LIT1c**: `q01 → … → q10 → p01 → q11 → p02 → q12 → p03 → q13 → p04 →
  q14 → p05 → q15 → p06 → q16 → q17 → … → q20`. Exits at `q01` are unknown;
  the 181 children whose last item was `q20` are treated as **completed**.

## Grade chip colors (LIT1c)

| Band | Color |
| --- | --- |
| 3YO | `#C5ABD3` |
| 4YO | `#8FD2E0` |
| KG  | `#7BDAC5` |

## Viewing locally

Open `index.html` directly, or serve the folder with any static server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

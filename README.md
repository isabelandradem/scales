# LIT1a · Rhyme · English — Spring 2026 item dashboard

Single-page dashboard summarizing item-level psychometrics for the LIT1a
(Rhyme) English assessment from the Spring 2026 administration.

## What's here

- `index.html` — the dashboard (HTML + inline CSS/JS, no build step)
- `images/` — item screenshots (`p01.png`, `p02.png`, `q01.png` … `q18.png`)

## Columns

| Column | Source |
| --- | --- |
| Item | item id (`p01`–`q18`) |
| Screenshot | `images/<item>.png` (click to enlarge) |
| % Correct | `Item-Level Percent Correct` block of the psychometric output |
| Item-Rest | `Item-Rest Cor` from the `Reliability` block |
| Alpha if Deleted | `Omitted Reliability` from the `Reliability` block |
| Exits | raw "last item seen" counts, **shifted down one row** (see below) |

## Note on the Exits column

The raw psychometric export reports the **last item a child saw**, which is
not the same as the item where the child exited the app. A child whose last
item was `X` actually exited when the next item appeared, so every value has
been shifted down by one row:

- `p01` exits — **unknown** (we have no record of exits before any item)
- `p02` = 13 (children whose last item was `p01`)
- `q01` = 7 (last item was `p02`)
- `q02` = 10 (last item was `q01`)
- …
- `q18` = 3 (last item was `q17`)

The 311 children whose last item was `q18` are treated as having **completed**
the assessment, and are reported in the "Completed Assessment" summary card
rather than as exits.

## Viewing locally

Open `index.html` directly, or serve the folder with any static server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

# Khan Kids · Assessment item dashboards

Static, single-page dashboards summarizing item-level psychometrics for
Khan Kids literacy and math assessments.

Live site: https://isabelandradem.github.io/scales/

## Dashboards

| Assessment | URL |
| --- | --- |
| LIT1a · Rhyme · EN | https://isabelandradem.github.io/scales/lit1a/ |
| LIT1c · Segmenting · EN | https://isabelandradem.github.io/scales/lit1c/ |
| MAT6a · Addition · EN | https://isabelandradem.github.io/scales/mat6a/ |
| MAT6b · Subtraction · EN | https://isabelandradem.github.io/scales/mat6b/ |

## Layout

```
.
├── index.html      ← home page with one card per assessment
├── lit1a/
│   ├── index.html  ← LIT1a · Rhyme · EN dashboard
│   └── images/
├── lit1c/
│   ├── index.html  ← LIT1c · Segmenting · EN dashboard
│   └── images/
├── mat6a/
│   ├── index.html  ← MAT6a · Addition · EN dashboard (Spring / Fall toggle)
│   └── images/
│       ├── spring/
│       └── fall/
└── mat6b/
    ├── index.html  ← MAT6b · Subtraction · EN dashboard (Spring / Fall toggle)
    └── images/
```

Each dashboard is a single HTML file with inline CSS / JS — no build step.

## Viewing locally

Open `index.html` directly, or serve the folder with any static server:

```bash
python3 -m http.server 8000
# then open http://localhost:8000/
```

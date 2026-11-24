# The Most Efficient NBA Duo

MIS 433 course project, Fall 2026, by Sam Nocera and Jackson Hardy.

**Question:** Which two-player duo on each NBA team is the most efficient when both players are on the floor, and how do the best duos compare across the league?

## Notebooks

| Notebook | What it does |
|---|---|
| [`01_analysis.ipynb`](01_analysis.ipynb) | Cleans the 2-man lineup data, explores it, builds a Duo Efficiency Score under four weighting models, finds the best duo on every team, and tests last season's scores against this season |
| [`02_application.ipynb`](02_application.ipynb) | Three features that combine our dataset, the BALLDONTLIE API, and the OpenAI API |

Open in Colab: [01_analysis](https://colab.research.google.com/github/samnocera05-ui/mis433/blob/main/final-project/01_analysis.ipynb) · [02_application](https://colab.research.google.com/github/samnocera05-ui/mis433/blob/main/final-project/02_application.ipynb)

## Data

Source: [NBA.com Advanced Stats](https://www.nba.com/stats/lineups/advanced), Lineups, Advanced, 2-man lineups, exported to CSV.

| File | Contents |
|---|---|
| `data/duos_train_2025_26.csv` | 2025-26 full season, top 2,000 duos by minutes (raw export) |
| `data/duos_test_2026_27.csv` | 2026-27 season through Nov 24, 2026 (raw export) |
| `data/duos_scored_2025_26.csv` | output of `01_analysis`: 1,259 duos with 300+ minutes, scored under four models |
| `data/duos_clean_2026_27.csv` | output of `01_analysis`: cleaned 2026-27 duos with 100+ minutes |

## Application features

1. **Team Duo Scouting Report:** pick a team; get its top duos, its live 2026-27 record, and an OpenAI scouting report with audio narration.
2. **Duo vs Duo:** pick two duos; compare them under all four models with live player profiles and an OpenAI verdict.
3. **Build Your Own Model:** set your own stat weights; every duo is re-ranked, OpenAI explains the result, and generates a "Duo of the Year" poster.

## How to run

1. Open a notebook in Colab with the links above.
2. For `02_application`, add two Colab secrets (key icon in the left sidebar) with notebook access on:
   - `OpenAIAPI` (your OpenAI API key)
   - `BalldontlieAPI` (free account at [app.balldontlie.io](https://app.balldontlie.io))
3. Runtime > Run all. The BALLDONTLIE free tier allows 5 requests per minute, so `02_application` pauses between calls and takes a few minutes.

Packages: see `requirements.txt` (all preinstalled on Colab).

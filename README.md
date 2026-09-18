# Athena — AI Data Analyst Agent

Ask a business question in plain English — *"which region makes the most money?"* — and Athena answers in clear language **and draws the chart**. Think ChatGPT, but focused on one company's sales data.

**Live demo:** https://nilanbeigibeigi.github.io/athena-agent/
**Author:** Nilan Beigi — [portfolio](https://nilanbeigibeigi.github.io/Nilan-Portfolio/) · [GitHub](https://github.com/nilanbeigibeigi)

---

## The problem

Non-technical business owners can't easily get answers from their own sales data. They either wait on an analyst or wrestle with spreadsheets. Athena closes that gap: natural-language questions in, plain answers + visuals out.

## What it does

- **Natural-language Q&A** over a sales dataset — regions, products, months, totals, comparisons.
- **Automatic charts** — the answer comes with the right visualization, not just a number.
- **Two modes:**
  - **Offline mode (default)** — a built-in rule/intent engine answers common questions instantly, with no setup and no API key.
  - **Real-AI mode (optional)** — paste a free [Groq](https://groq.com) API key and Athena uses a live LLM to handle open-ended questions it wasn't explicitly programmed for.

## How it works

1. The user's question is parsed for intent and entities (metric, dimension, filter, time range).
2. In offline mode, that maps to a query over the dataset; in real-AI mode, the question + a compact data summary are sent to the LLM with a focused prompt.
3. The result is rendered as a written answer plus a chart.

This graceful-degradation design (works with zero setup, upgrades with one key) means the demo is always usable and costs nothing to host.

## Tech

- Front-end app (runs entirely in the browser)
- Charting for the generated visuals
- Optional LLM via the Groq API

## Run locally

```bash
git clone https://github.com/nilanbeigibeigi/athena-agent
cd athena-agent
# open index.html in a browser, or serve it:
npx serve .
```

For real-AI mode, get a free key at groq.com and paste it into the in-app field (it stays in your browser).

## Roadmap

- Connect to a live database instead of a bundled dataset
- Query validation and guardrails on the LLM path
- Multi-turn follow-up questions with conversation memory
- Export answers + charts to PDF

## Note

Educational demo on sample data — not connected to any real company's systems.

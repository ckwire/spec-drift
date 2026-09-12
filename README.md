# spec-drift

AI agent that cross-checks specs against drawings and flags mismatches
with cited evidence, so nothing gets missed at review.

## What it does

Given a spec section and its corresponding drawing (or drawing notes),
spec-drift identifies where they disagree — material mismatches, rating
mismatches, dimension mismatches, or a requirement present in one but
silent in the other — and cites the exact source passage behind every
flag.

Built as a retrieval + verification agent, not a chatbot: every output
is traceable back to a specific line in a specific document.

## Status

Early and actively in development. Currently working through an initial
document pair end-to-end before expanding scope. Not yet handling
[e.g. multi-document retrieval / real project data / etc — whatever's
honestly true right now].

## How it works

1. Ingests a spec section and a drawing/drawing-notes file
2. Retrieves the relevant passages from each
3. Compares them for conflicts or gaps
4. Returns a structured flag with a citation to both sources
5. A human reviewer confirms or dismisses each flag

## Why this exists

Spec-vs-drawing conflicts that surface mid-construction cost real time
and money. Catching them at review, with a clear citation instead of a
vague "something looks off," is the goal.

## Tech

[Fill in as it becomes true — e.g. Python, LangGraph, pgvector, Claude/OpenAI API]

## Evaluation

Tested against a hand-written set of spec/drawing pairs with known
expected outcomes — see `/eval`. [Add your baseline score once you
have one after Day 7.]

## Status

Working against a real document pair — Fire Station in CA (public bid documents: electrical drawings and
Division 26 technical specifications). Test set of 18 cases built
against real spec clauses and drawing content. Baseline scoring not
yet run.

## License

MIT — see [LICENSE](./LICENSE)

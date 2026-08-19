# toll-bench-data

Public target data and results for [Toll Bench](https://tollbench.com/toll-bench) —
a live benchmark measuring whether AI systems can deliver real-world human
wants, verified by the person's approval.

[![verify](https://github.com/tollbench/verifier/actions/workflows/verify.yml/badge.svg)](https://github.com/tollbench/verifier/actions/workflows/verify.yml)

- **`data/deals.csv`** — one row per resolved deal, published automatically the
  moment a deal resolves. Full data dictionary in [data/README.md](data/README.md).
- **Every row has a permanent receipt**: `https://tollbench.com/receipts/<deal_id>` —
  the public row plus every public ledger event behind it, each event carrying
  its RFC 8785 canonical `event_hash`.
- **Live public data, no key needed**:
  [`/api/bench/board.json`](https://tollbench.com/api/bench/board.json) (the
  leaderboard recomputed from the ledger on request),
  [`/api/bench/receipts.jsonl`](https://tollbench.com/api/bench/receipts.jsonl),
  [`/api/bench/ledger.jsonl`](https://tollbench.com/api/bench/ledger.jsonl).
- **Check the math**: [`tollbench/verifier`](https://github.com/tollbench/verifier)
  is a stdlib-only script that rebuilds the whole leaderboard from this file
  and compares it against the live site. A scheduled GitHub run does this
  daily; the badge above is green when a stranger's recomputation matches.
- **Hugging Face mirror**: https://huggingface.co/datasets/tollbench/toll-bench-data
- **The paper**: https://bookofhouses.com/static/toll-bench.html

The ledger is the source of truth; this repository is a public mirror of it.
If the two ever disagree, the ledger wins and this repository is repaired to
match, in a new commit — history is never rewritten.

## Cite Toll Bench

```bibtex
@misc{ochs2026tollbench,
  author = {Ochs, Steven},
  title  = {Toll Bench: Can AI Systems Deliver Real-World Human Wants?},
  year   = {2026},
  url    = {https://tollbench.com/toll-bench},
  note   = {Live benchmark; public data at github.com/tollbench/toll-bench-data}
}
```

## License

The data in this repository is licensed under
[CC BY 4.0](https://creativecommons.org/licenses/by/4.0/) (Steven Ochs / Book
of Houses, ruled 2026-08-19). Use it freely, cite Toll Bench.

# Baseline query timings

**Status: measurements pending.** The local machine has `psql` but no running PostgreSQL server or installed `postgres` server binary; Docker access is unavailable. No execution times or plan types are estimated. The CSV seed checks in `docs/02_schema_design.md` are not a substitute for this database benchmark.

Run from the repository root after providing PostgreSQL 15+ and an empty database:

```bash
unzip -q seed_data.zip
psql -v ON_ERROR_STOP=1 -d YOUR_DB -f sql/01_schema.sql
psql -v ON_ERROR_STOP=1 -d YOUR_DB -f sql/02_load_data.sql
./benchmarks/run_benchmark.sh YOUR_DB baseline
```

The benchmark script writes three raw `EXPLAIN (ANALYZE, BUFFERS)` plans per query to `benchmarks/results/baseline/R*.txt` and `W*.txt`, and averages their `Execution Time` values in `summary.csv`. It wraps writes in `BEGIN`/`ROLLBACK`. Fill this table from the raw plan files after a successful run.

| SQL query | Type | Run 1 (ms) | Run 2 (ms) | Run 3 (ms) | Average (ms) |
|---|---|---:|---:|---:|---:|
| R01: Artist page: artist 33's 10 most-streamed tracks in the last 28 days | READ | — | — | — | — |
| R02: Album page: tracklist of album 1469 | READ | — | — | — | — |
| R03: Search: tracks whose title contains "love", most popular first | READ | — | — | — | — |
| R04: "Recently played": user 1038's last 50 streams | READ | — | — | — | — |
| R05: Playlist page: playlist 501 in order, with every artist on each track | READ | — | — | — | — |
| R06: "Liked Songs": user 1038's liked tracks, newest first | READ | — | — | — | — |
| R07: Royalties: streams of 30 seconds or more ("royalty-eligible") per artist in June 2026, top 20 | READ | — | — | — | — |
| R08: Spotify for Artists: skip rate of each of artist 33's tracks | READ | — | — | — | — |
| R09: Wrapped 2025: user 1038's top 5 artists by minutes listened | READ | — | — | — | — |
| R10: Platform analytics: daily streams per platform in June 2026 | READ | — | — | — | — |
| R11: "Release Radar": 2026 releases by artists user 1038 follows | READ | — | — | — | — |
| R12: Compliance: explicit tracks streamed by users who were under 18 at the time | READ | — | — | — | — |
| R13: Curation team: public playlists that have never been played | READ | — | — | — | — |
| R14: Collaborative playlists: number of different people who added tracks | READ | — | — | — | — |
| R15: "Fans also like": artists most followed by the followers of artist 33 | READ | — | — | — | — |
| R16: Artist profiles: distinct listeners of every artist in the last 28 days ("monthly listeners") | READ | — | — | — | — |
| R17: Growth: free users with 4+ streams in June 2026 (Premium upsell list) | READ | — | — | — | — |
| R18: Platform analytics: share of offline listening per platform | READ | — | — | — | — |
| R19: Verified artists report: total streams and the latest stream of every verified artist | READ | — | — | — | — |
| R20: Listening patterns: streams per hour of the day per country | READ | — | — | — | — |
| R21: Rights management: look up a recording by its ISRC code | READ | — | — | — | — |
| R22: Playlist hygiene: playlists that contain the same track more than once | READ | — | — | — | — |
| R23: Support console: all streams, newest first, page 8,001 (25 per page) | READ | — | — | — | — |
| R24: Label report: average track length and explicit share per album type | READ | — | — | — | — |
| R25: Discovery: tracks released in the last 30 days, ranked by streams | READ | — | — | — | — |
| W01: Player: log a stream of track 1389 by user 1038 | WRITE | — | — | — | — |
| W02: Heart button: user 1038 likes track 1389 | WRITE | — | — | — | — |
| W03: "Add to playlist": append track 1389 to the end of playlist 501 | WRITE | — | — | — | — |
| W04: Nightly job: recompute every artist's monthly listeners (last 28 days) | WRITE | — | — | — | — |
| W05: Takedown: the label withdrew the whole album of track 1389, so remove its tracks from every playlist | WRITE | — | — | — | — |
| **Total (sum of all 30)** | | — | — | — | — |

## Plan observations

Scan type and a one-line explanation for each query must come from its saved plan. They remain pending until the database benchmark runs.

- **R01:** Pending plan and execution time.
- **R02:** Pending plan and execution time.
- **R03:** Pending plan and execution time.
- **R04:** Pending plan and execution time.
- **R05:** Pending plan and execution time.
- **R06:** Pending plan and execution time.
- **R07:** Pending plan and execution time.
- **R08:** Pending plan and execution time.
- **R09:** Pending plan and execution time.
- **R10:** Pending plan and execution time.
- **R11:** Pending plan and execution time.
- **R12:** Pending plan and execution time.
- **R13:** Pending plan and execution time.
- **R14:** Pending plan and execution time.
- **R15:** Pending plan and execution time.
- **R16:** Pending plan and execution time.
- **R17:** Pending plan and execution time.
- **R18:** Pending plan and execution time.
- **R19:** Pending plan and execution time.
- **R20:** Pending plan and execution time.
- **R21:** Pending plan and execution time.
- **R22:** Pending plan and execution time.
- **R23:** Pending plan and execution time.
- **R24:** Pending plan and execution time.
- **R25:** Pending plan and execution time.
- **W01:** Pending plan and execution time.
- **W02:** Pending plan and execution time.
- **W03:** Pending plan and execution time.
- **W04:** Pending plan and execution time.
- **W05:** Pending plan and execution time.

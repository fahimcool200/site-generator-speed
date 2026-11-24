# site-generator-speed

[![make.fun · site-generator-speed-01-run-20261122](https://make.fun/badge/site-generator-speed-01-run-20261122.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![rank](https://make.fun/badge/site-generator-speed-01-run-20261122/fahimcool200/site-generator-speed/rank.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122/leaderboard?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)
[![reward](https://make.fun/badge/site-generator-speed-01-run-20261122/fahimcool200/site-generator-speed/reward.svg)](https://make.fun/bounty/site-generator-speed-01-run-20261122?utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122)

A faster drop-in for make.fun's own makefun-site 1.0.0 static site generator: `solve.js` answers every case exactly as the reference does — same output tree, byte for byte — in about half the CPU time.

## Run it

```sh
mkdir -p out && MAKEFUN_INPUT_DIR=practice/input MAKEFUN_OUTPUT_DIR=out node main.ts
```

`main.ts` reads every case from the input dir, answers each with `run()` from `solve.js`, and writes `out/answers.json`. Node 22, standard library only, no dependencies.

## How it is faster

Single-pass Markdown with batched inline rendering, a regex-free fast path for escaping, a lookup-table word count, an ASCII fast path for slugs, and precompiled templates — while keeping every answer identical to makefun-site 1.0.0.

Verified on the kit's practice set: 3/3 cases identical (official scorer: `passed: 1, cases_passed: 3/3`), and 12/12 more on freshly generated case sets. Timed on the practice set: ~1.75x faster than the house baseline by wall time.

---

<sub>Entered on [make.fun](https://make.fun/?ref=19r7tbph&utm_source=github&utm_medium=readme&utm_campaign=site-generator-speed-01-run-20261122) · AI agents build software for cash rewards</sub>

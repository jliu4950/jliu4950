<img src="./assets/banner.svg" alt="June Liu" width="1280" />

# Hi, I'm June Liu

M.S. Computer Science at Northeastern University, building reliable AI applications
and scalable backend systems.
**Seeking a Summer 2027 software engineering / AI internship.**

Five years of production experience before the degree: an LLM Text-to-SQL agent and a
CRM platform at an industrial-supply company, and lead-routing and streaming-analytics
services at a real-estate brokerage.

![Python](https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=python&logoColor=white)
![Java](https://img.shields.io/badge/Java-007396?style=flat-square&logo=openjdk&logoColor=white)
![FastAPI](https://img.shields.io/badge/FastAPI-009688?style=flat-square&logo=fastapi&logoColor=white)
![Spring%20Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=flat-square&logo=springboot&logoColor=white)
![PostgreSQL](https://img.shields.io/badge/PostgreSQL-4169E1?style=flat-square&logo=postgresql&logoColor=white)
![Kafka](https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=apachekafka&logoColor=white)
![AWS](https://img.shields.io/badge/AWS-232F3E?style=flat-square&logo=amazonwebservices&logoColor=white)
![LLM%20Applications](https://img.shields.io/badge/LLM%20Applications-334155?style=flat-square&logoColor=white)

## Selected Projects

| Project | What it does | Stack |
|---|---|---|
| **[QueryGuard](https://github.com/jliu4950/queryguard)** [![CI](https://github.com/jliu4950/queryguard/actions/workflows/ci.yml/badge.svg)](https://github.com/jliu4950/queryguard/actions) | Text-to-SQL service that treats model output as untrusted: schema retrieval, `sqlglot` AST validation, and row-level authorization injected server-side. Two suites run in CI on Python 3.9–3.13 — 25 correctness cases and 44 adversarial cases that assume the model is hostile. | FastAPI · sqlglot · SQLAlchemy · SQLite |
| **[StreamTally](https://github.com/jliu4950/streamtally)** [![CI](https://github.com/jliu4950/streamtally/actions/workflows/ci.yml/badge.svg)](https://github.com/jliu4950/streamtally/actions) | Real-time event analytics whose counts survive redelivery and mid-batch failure. An exactness harness tries to make them wrong; CI runs it against a real Kafka broker and Postgres on every push. | TypeScript · Kafka · Postgres · React |

### QueryGuard — the part worth looking at

A sales rep asks for "my customer orders". They never say *which* customers are theirs,
and the model is never asked to scope the query. The `customer_assignments` predicate in
the generated SQL is injected by the server after validation — authorization is a query
transformation, not a prompt instruction.

[![QueryGuard dashboard showing a sales-rep query whose generated SQL contains the server-injected authorization predicate](https://raw.githubusercontent.com/jliu4950/queryguard/main/docs/assets/demo-authorized-query.png)](https://github.com/jliu4950/queryguard#demo)

A second suite attacks that claim. For its 44 adversarial cases the model is replaced by one
returning attacker-chosen SQL — what a jailbroken model effectively gives you — and the pass
criterion is *disclosure*, not refusal, since refusing everything would score perfectly and be
useless. Writing it found six real bypasses in controls the README already claimed to have,
including `SELECT *` disclosing every customer email and a function blocklist that could never
match the functions it named. All six are fixed; CI now fails on any out-of-scope disclosure.

Metrics describe this demo harness on fictional data, not general Text-to-SQL model quality.
The repo is explicit about [scope](https://github.com/jliu4950/queryguard#evaluation),
[findings](https://github.com/jliu4950/queryguard/blob/main/docs/adversarial-evaluation.md),
and [what still doesn't hold](https://github.com/jliu4950/queryguard#limitations-and-future-work).

### StreamTally — the number has to stay right

Anyone can render a line chart from a counter. The hard part is the counter staying correct
when the broker redelivers a batch and the consumer dies halfway through it. StreamTally makes
that claim falsifiable and ships the harness that attacks it — including the case where a batch
is durably written and the process then dies *before* the offset commit, which is where an
aggregator that trusts its delivery semantics starts double-counting.

Ingest sustains **36,000 events/s** on a laptop at p99 49 ms, and the benchmark asserts every
accepted event was still counted exactly once, because a throughput number from a pipeline that
drops events is worse than no number.

## Currently

*Updated September 2026*

- Next on QueryGuard: replacing the blunt “reject every subquery for sales reps” rule with a
  scope-aware rewrite that constrains every table reference.
- Next on StreamTally: aging out the dedupe table on a retention window, and testing consumer
  rebalance with more than one aggregator.
- Daily algorithm practice in [neetcode-submissions](https://github.com/jliu4950/neetcode-submissions).

## What I Work On

- **AI systems:** LLM applications, retrieval, evaluation, and safety guardrails
- **Backend systems:** APIs, data modeling, event-driven services, caching, and observability

## Connect

[LinkedIn](https://www.linkedin.com/in/juneliu4950) · jliu4950@gmail.com

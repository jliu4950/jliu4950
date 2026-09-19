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
| **[QueryGuard](https://github.com/jliu4950/queryguard)** [![CI](https://github.com/jliu4950/queryguard/actions/workflows/ci.yml/badge.svg)](https://github.com/jliu4950/queryguard/actions) | Text-to-SQL service that treats model output as untrusted: schema retrieval, `sqlglot` AST validation, and row-level authorization injected server-side. 25-case eval suite runs in CI on Python 3.9–3.13. | FastAPI · sqlglot · SQLAlchemy · SQLite |

### QueryGuard — the part worth looking at

A sales rep asks for "my customer orders". They never say *which* customers are theirs,
and the model is never asked to scope the query. The `customer_assignments` predicate in
the generated SQL is injected by the server after validation — authorization is a query
transformation, not a prompt instruction.

[![QueryGuard dashboard showing a sales-rep query whose generated SQL contains the server-injected authorization predicate](https://raw.githubusercontent.com/jliu4950/queryguard/main/docs/assets/demo-authorized-query.png)](https://github.com/jliu4950/queryguard#demo)

On the repository's deterministic fictional dataset the 25-case suite reports execution
accuracy 1.0, zero authorization violations, and a 1.0 safety interception rate. Those
numbers describe this demo harness, not general Text-to-SQL model quality — the
[README](https://github.com/jliu4950/queryguard#evaluation) is explicit about the scope
and the [limitations](https://github.com/jliu4950/queryguard#limitations-and-future-work).

## Currently

*Updated September 2026*

- Extending QueryGuard's evaluation suite with an adversarial subset covering
  prompt-injection attempts against the authorization layer.
- Building an event-driven backend service with load-test and observability evidence.
- Daily algorithm practice in [neetcode-submissions](https://github.com/jliu4950/neetcode-submissions).

## What I Work On

- **AI systems:** LLM applications, retrieval, evaluation, and safety guardrails
- **Backend systems:** APIs, data modeling, event-driven services, caching, and observability

## Connect

[LinkedIn](https://www.linkedin.com/in/juneliu4950) · jliu4950@gmail.com

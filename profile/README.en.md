<div align="center">

🌐 **[한국어](./README.md)** | **English** | **[日本語](./README.ja.md)** | **[简体中文](./README.zh.md)**

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="./logo-dark.svg">
  <img alt="data2flow" src="./logo-light.svg" width="300">
</picture>

**Stop watching dashboards. Let your building fix itself.**

An AIoT platform that connects, cleans and analyzes in-building sensor data with configuration alone,<br>and then acts on equipment based on the results

</div>

---

## What is data2flow

> CO2 in a lab stays above 1,000 ppm for 5 minutes.<br>
> → data2flow detects it and turns on the ventilation.<br>
> → If it does not drop within 15 minutes, the person in charge gets a "control had no effect" alert.<br>
> → A month later, a report shows how much time above the limit was reduced.

The whole loop is built **in the UI, with settings and visual flows**, without deploying code. As the name says, **data** follows the **flow** from cleaning to analysis to action.

## Five stages

| Stage | What it does |
|---|---|
| **Connect** | Attach LoRaWAN (ChirpStack), MQTT, Webhook and edge-gateway sensors from the UI; discover new devices from incoming data and register them with admin approval |
| **Clean** | Turn vendor-specific payloads into one shape: sandboxed JavaScript scripts, quality codes, raw retention and reprocessing |
| **Understand** | Pick-and-run analysis templates (comfort, space utilization, anomaly detection, energy) with AI explanations in plain language |
| **Act** | Detect with the flow editor and rules, drive equipment through one vendor-neutral control gateway, notify via Telegram |
| **Rehearse** | Validate automations first in a virtual space with virtual sensors, devices and scenarios |

## What makes it different

- **Measure → standard → act → evidence** in one product, up to indoor-air-quality compliance reports.
- **Zero data loss, zero-downtime deploys.** Not a single incoming message is lost, even during redeploys.
- **Live editing.** Flow changes apply immediately without stopping the engine.
- **Vendor-neutral control.** Capability + Driver + Control Facade — the UI, flows and AI all use the same gateway.
- **Open-source license policy.** Only permissive licenses (Apache, MIT, BSD, …) ship in the product.

## Repositories

| Repository | Role | Tech |
|---|---|---|
| [data2flow-docs](https://github.com/data2flow/data2flow-docs) | Specs, design, decision records, storyboards | Markdown |
| data2flow-web | UI + BFF (server rendering, sessions) | React Router v7, TypeScript |
| data2flow-api-gateway | Routing, token check, identity propagation | Spring Cloud Gateway |
| data2flow-auth | Login, token issue and revocation | Spring Boot 4 |
| data2flow-core-api | Users, devices, spaces, sources, flow definitions, rules, dashboards | Spring Boot 4 |
| data2flow-ingress | MQTT subscription, Webhook and edge intake | Spring Boot 4 |
| data2flow-pipeline | Decoding, scripts, storage, aggregation | Spring Boot 4, GraalJS |
| data2flow-flow-engine | Flow and rule execution, live reload | Spring Boot 4, GraalJS |
| data2flow-action | Device control, notifications, external sinks | Spring Boot 4 |
| data2flow-simulator | Virtual spaces, sensors, devices and scenarios | Spring Boot 4 |
| data2flow-ai | Result explanations, reports, chatbot, MCP server | Spring AI |
| data2flow-analytics | Analysis templates, real-time inference | Python, FastAPI |
| data2flow-contracts | Message schemas, common response and error formats | Java, JSON Schema |
| data2flow-manifests | Kubernetes deployment (GitOps) | Kustomize, Argo CD |

## Tech stack

`React Router v7` `TypeScript` `Spring Boot 4` `Java 21` `Spring AI` `Python FastAPI` `PostgreSQL 18 + pgvector` `RabbitMQ Streams` `Redis` `GraalJS` `Kubernetes` `Argo CD`

## Releases

Each version ships release notes in four languages (한국어 · English · 日本語 · 简体中文), and every service repository gets the same git tag (`vX.Y`). No release yet.

## Where we are

We work docs-first. 763 specs, 1,096 acceptance tests, a 155-scene UI storyboard, the ERD and the OpenAPI/AsyncAPI specs are done, and the first implementation milestone (M0) is being prepared.

<div align="center"><sub>Made at NHN Academy · data → flow</sub></div>

---
title: devops-openobserve-dev
tags: [monitoring, openobserve]
created: 2026-08-28T17:50:14.550Z
modified: 2026-08-28T17:50:48.600Z
---

# devops-openobserve-dev

> Open source observability platform for logs, metrics, traces, frontend monitoring, pipelines and LLM observability. 

# guide
- pros
  - 140x lower storage cost: Parquet columnar storage + S3-native architecture 
  - Performance: written in Rust, utilizes the DataFusion query engine to directly query Parquet files
  - Scalability: Operate at petabyte scale. Internal query benchmarking of 1 petabyte of data returned in 2 seconds.
  - OpenTelemetry native
  - SQL + PromQL: Query logs and traces with SQL, metrics with SQL or PromQL — no proprietary query language
  - Highly Compatible: Works with existing Prometheus and Elasticsearch tooling and workflows
  - Unified platform: Logs, metrics, traces, RUM, dashboards, alerts, and incidents 
  - Easy to Deploy: Single binary deployment
  - Cloud Native: Built for modern cloud environments and containerized workloads
  - Enterprise Ready: Offers SSO, RBAC, and compliance features

- cons
  - license: AGPL

- features
  - cost-effective alternative to Datadog, Splunk, and Elasticsearch

- tips
  - ?
# draft

# dev-xp

# more

# docs-openobserve

## overview

- OpenObserve is an observability platform with a distributed architecture composed of five node types — Router, Ingester, Compactor, Querier, and Scheduler — that runs in either single-node mode (SQLite with local disk or object storage) or high-availability mode (NATS, PostgreSQL, and object storage).

- Single-node mode with SQLite and local disk is the default way to run OpenObserve. Use it for light usage and testing or if you don't require HA. You can still ingest and search over 2 TB on a single machine per day.
  - Based on our tests (using an Apple M2 chip), you can ingest data at approximately 31 MB per second with the default configuration. This is equivalent to 1.8 GB per minute or 2.6 TB per day.
- Single-node mode with SQLite and object storage runs OpenObserve on one node but stores parquet files in durable object storage (for example, Amazon S3, GCS, MinIO, or Azure Blob) instead of local disk.
  - Compared with the local-disk variant, it trades slightly higher read latency and a storage dependency for much higher durability and effectively unbounded capacity.

- Running OpenObserve in HA mode requires: Kubernetes (with Helm) to orchestrate the nodes

- 
- 
- 
- 
- 
- 
- 
- 
- 

## ingestion

- OpenObserve supports multiple log ingestion methods to collect, aggregate, and centralize logs from various sources.

- [Vector - High-Performance Log Aggregation & Routing ](https://openobserve.ai/docs/ingestion/logs/vector/)
- Vector is a high-performance observability data pipeline for log aggregation, transformation, and routing. 
  - Use Vector to collect logs from multiple sources, transform log data, and route logs to OpenObserve for centralized log management and analysis.
- Once Vector starts shipping data, open the OpenObserve UI, click Logs in the sidebar, and select your stream. New log entries should appear within a few seconds.

- OpenObserve supports OpenTelemetry-compatible distributed tracing for application performance monitoring (APM) and microservices observability.

- 
- 
- 

## processing

- Enrichment tables in OpenObserve allow you to add meaningful context to your log data by joining it with external reference data. 
  - These tables are uploaded as CSV files and can be used during ingestion or at query time to add or modify fields.

- functions are VRL (Vector Remap Language) scripts that transform your stream data. You create and manage functions via the OpenObserve UI or API. 
  - VRL can be used during ingestion or query to aid advanced capabilities like enrichment, redaction, log reduction, compliance, etc.
  - custom SQL functions extend the capabilities of standard SQL by enabling full-text search, array processing, and time-based aggregations.

- 
- 
- 
- 
- 

## search

- 
- 
- 
- 
- 

## Analytics

- Service Level Objectives
  - An SLO turns a reliability goal into a number you can measure, argue about, and alert on. It answers one question continuously: over the last N days, what fraction of the thing you care about was good, and how much of your allowance for badness is left?
  - OpenObserve measures SLOs on a background job that runs independently of alerting. That separation is the whole point of the feature: measurement happens once, several alerts read the result, and none of them re-scan your raw data.

- 
- 
- 
- 
- 
- 

## docs

- 
- 
- 
- 
- 
- 
- 

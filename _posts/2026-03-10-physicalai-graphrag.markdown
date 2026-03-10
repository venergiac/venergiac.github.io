---
layout: post
title:  "Building an Industrial Graph‑RAG Pipeline with ISO 14224, Neo4j, InfluxDB, and Local LLMs"
date:   2026-03-10 00:00:00 +0100
categories: article
---

# Building an Industrial Graph‑RAG Pipeline with ISO 14224, Neo4j, InfluxDB, and Local LLMs

Building Industrial‑Grade Graph‑RAG with ISO 14224, Graphs, Time‑Series, and Local LLMs
Physical AI is not just about large language models—it is about structure, context, and time. In industrial environments, answering questions such as “What happened to this pump?” or “What is the current operating condition of this turbine?” requires more than documents and embeddings. It requires combining asset hierarchies, failure semantics, and time‑series data.
This project demonstrates a practical Graph‑RAG (Retrieval‑Augmented Generation) architecture designed specifically for industrial datasets. It integrates ISO 14224 asset models, Neo4j knowledge graphs, InfluxDB time‑series data, and local LLMs (Mistral via Ollama) into a fully reproducible, Docker‑based environment.
Unlike traditional RAG pipelines that rely on unstructured text, industrial systems are inherently structured. Assets follow strict hierarchies, failures have defined modes and mechanisms, and measurements continuously evolve over time. Graph‑RAG addresses this by using a knowledge graph to encode relationships and a time‑series database to capture operational reality, allowing the LLM to reason over explicit, structured context rather than raw text alone.
ISO 14224 provides the backbone of the system, defining companies, installations, equipment, measurements, and failure events. This structure is imported into Neo4j, creating the system’s structural memory. Operational data is stored separately in InfluxDB, representing the temporal truth of what is happening now or most recently. A synchronization step updates the graph with the latest measurements, making it time‑aware.
On top of this foundation, Graph‑RAG enables natural‑language queries that are translated into Cypher, executed against the graph, and explained by a local LLM. The result is grounded, explainable answers—for example, identifying failure events on a pump or reporting the latest wind speed of a turbine—without hallucinations.
This approach moves beyond chatbots and embeddings toward engineering‑grade AI assistants for operations, maintenance, and reliability, built on standards, semantics, time awareness, and local, controllable AI.

Article on [https://venergiac.substack.com/p/building-an-industrial-graphrag-pipeline](https://venergiac.substack.com/p/building-an-industrial-graphrag-pipeline). 

Clone code from

     git clone https://github.com/venergiac/iiot-graph-rag.git
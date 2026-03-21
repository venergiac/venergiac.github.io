---
layout: post
title:  "Streaming RAG for IIoT: using LLM to perform live analytic for asset performance management"
date:   2026-03-21 00:00:00 +0100
categories: article
---

# Streaming RAG for IIoT: using LLM to perform live analytic for asset performance management

Classic RAG (Retrieval-Augmented Generation) assumes static documents. In IoT, knowledge changes every second. Streaming RAG means:

1. Ingest continuously (MQTT telemetry stream)
2. Index incrementally (append-only time-series + optionally semantic embeddings)
3. Retrieve just-in-time (latest values, last N minutes, anomalies)
4. Generate answers with streaming tokens (LLM starts answering immediately, keeps improving as retrieval completes)

This gives you a “living assistant” that can answer operational questions in real-time and trigger actions (alarms) deterministically.

Article on [https://venergiac.substack.com/p/streaming-rag-for-iiot-using-llm](https://venergiac.substack.com/p/streaming-rag-for-iiot-using-llm). 

Clone code from

     git clone https://github.com/venergiac/iiot-streaming-rag.git
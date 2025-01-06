---
layout: post
title:  "AI Agents Specialization"
date:   2025-01-01 00:00:00 +0100
categories: courses
---

![Agentic AI](/agenticai.png)

Developing an agent system through AI is not trivial given the plurality of available frameworks; below is a list of the most widespread ones:

# Building From Scratch

Yes, you can definitely build AI agents from scratch! Below the course:
1. [Build Autonomous AI Agents From Scratch With Python by Udemy](https://www.udemy.com/course/build-autonomous-ai-agents-from-scratch-with-python)

# Leveraging on LangChain

LangChain, with its impressive 90k GitHub stars, stands as the leading framework for developing LLM-based applications. Its extensive suite of tools and components enables the creation of comprehensive AI solutions using a wide range of LLMs. Central to LangChain's functionality are its agents. These autonomous or semi-autonomous tools can execute tasks, make decisions, and interact with various tools and APIs, marking a significant advancement in automating complex workflows with LLMs.

The following code starts an agent with 2 tools and ask question about book wrote by me:

```python
!pip install arxiv

from langchain.agents.agent_toolkits import create_python_agent
from langchain.agents import load_tools, initialize_agent
from langchain.agents import AgentType
from langchain.chat_models import ChatOpenAI

llm = ChatOpenAI(temperature=0, model="gpt-3.5-turbo")
tools = load_tools(["llm-math","wikipedia","arxiv"], llm=llm)

agent= initialize_agent(
    tools, 
    llm, 
    agent=AgentType.CHAT_ZERO_SHOT_REACT_DESCRIPTION,
    handle_parsing_errors=True,
    verbose = True)

question = "Giacomo Veneri is an italian author, which article he wrote?"
result = agent(question) 
```
Below the courses:


1. [LangChain for LLM Application Development by DeepLearning.AI & LangChain](https://www.deeplearning.ai/short-courses/langchain-for-llm-application-development/)

2. [Fundamentals of AI Agents Using RAG and LangChain by Coursera & IBM](https://www.coursera.org/learn/fundamentals-of-ai-agents-using-rag-and-langchain)

## ..or LangGraph

An advanced framework is LangGraph

1. [AI Agents in LangGraph](https://learn.deeplearning.ai/courses/ai-agents-in-langgraph/lesson/1/introduction)

# Microsoft Autogen

Autogen is an open-source framework (by Microsoft Research) designed for creating agentic systems. This framework allows you to build multi-agent collaborations and LLM workflows efficiently.

You can find a lot of [examples](https://microsoft.github.io/autogen/0.2/docs/Examples/).

Below the courses:
1. [AI Agentic Design Patterns with AutoGen by Coursera & Microsoft](https://www.coursera.org/projects/ai-agentic-design-patterns-with-autogen)


# crewAI

CrewAI stands out as a leading agent-based AI framework, enabling rapid development of AI agents and seamless integration with the latest LLMs and your existing codebase. Trusted by major corporations such as Oracle, Deloitte, Accenture, and more, CrewAI is a reliable choice for many.

Below the courses:
1. [Multi AI Agent Systems with crewAI by DeepLearning.AI & CrewAI](https://www.deeplearning.ai/short-courses/multi-ai-agent-systems-with-crewai/)

# LlamaIndex

A very useful example how to parse Invoice and send payment [Invoice to Payment](https://github.com/run-llama/llamacloud-demo/blob/main/examples/document_workflows/invoice_sku_product_catalog_matching/invoice_sku_product_catalog_matching.ipynb)



Below the courses:
1. [Building & Evaluating Advanced RAG Apps by DeepLearning.AI, LlamaIndex & TruEra](https://www.deeplearning.ai/short-courses/building-evaluating-advanced-rag/)

# OpenAI Swarm

OpenAI Swarn is nn educational framework exploring ergonomic, lightweight multi-agent orchestration.

[Swarm](https://github.com/openai/swarm)


# SuperAgentX

SuperAgentX is a lightweight, open-source AI framework built for multi-agent applications with Artificial General Intelligence (AGI) capabilities.

Github:
1. [github](https://github.com/superagentxai/superagentx)

# .... and more

Do not forget


1. [LLMs as Operating Systems: Agent Memory by DeepLearning.AI & Letta](https://learn.deeplearning.ai/courses/llms-as-operating-systems-agent-memory/lesson/1/introduction)
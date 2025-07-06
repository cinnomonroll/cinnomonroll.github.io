---
layout: post
title:  "Retrieval-Augmented Generation with Agents: Combining LLMs and Web Search"
# description:
date: 2025-06-30
categories: [blog]
tags: [LLM, LLaMA]
# published: true
---

## Introduction
Large language models (LLMs) like LLaMA are powerful tools for answering complex questions, but they are limited by the data they were trained on. To overcome this, I built a Retrieval-Augmented Generation (RAG) system with Agents that combines the reasoning power of LLMs with the latest information available on the web. Here’s how it works and why this approach matters.

## System Architecture
The core of this project is an agent-based workflow that orchestrates multiple components, allowing the system to extract keywords, search the web, clarify questions, and synthesize final answers using an LLM.

Here’s the overall architecture:


![The agent-based RAG pipeline used in this project](/assets/flow.png)

## How It Works
1. **Keyword Extraction Agent:**
Identifies the most relevant keywords from a user’s question.

2. **Search Tool:**
Uses those keywords to retrieve the latest information from the web.

3. **Question Extraction Agent:**
Clarifies or reformulates the question for better context if needed.

4. **QA Agent:**
Synthesizes and generates the final answer, leveraging both retrieved knowledge and LLM reasoning.

This modular design makes the system both powerful and flexible, enabling it to provide up-to-date, accurate answers on a wide variety of topics.

Technologies Used
- **Large Language Model:**
Quantized LLaMA 3.1 8B for efficient local inference.

- **Python/Jupyter Notebook:**
The whole workflow is developed in Python using Jupyter notebooks for easy prototyping and visualization.

- **Web Retrieval:**
Integrated with Google Search to supplement LLMs with current, external knowledge.

## Key Benefits
- **Up-to-date Answers:**
No longer limited to the LLM’s training data; the system can fetch new information in real time.

- **Modular Design:**
Each agent can be improved or replaced independently for future enhancements.

- **Transparent Workflow:**
Every step—from keyword extraction to final synthesis—is visible and explainable.

## Example Use Case
Suppose a user asks:

> "What are the latest advancements in battery technology for electric vehicles?"

Step-by-step, the system:

- Extracts keywords like "battery technology" and "electric vehicles."

- Searches the web for the most recent articles and research papers.

- Clarifies the question if needed (e.g., focusing on a particular type of battery).

- Combines all retrieved information and generates a clear, concise summary using the LLM.

### Try It Yourself
The code and instructions are available on **[My GitHub](https://github.com/cinnomonroll/Retrieval-Augmented-Generation-with-Agents/tree/main/ML1)**.
Just clone the repo, follow the notebook instructions, and experiment with your own questions.


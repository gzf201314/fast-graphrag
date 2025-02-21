<h1 align="center">
  <img width="800" src="banner.png" alt="circlemind fast-graphrag">
</h1>
<h4 align="center">
  <a href="https://github.com/circlemind-ai/fast-graphrag/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="fast-graphrag is released under the MIT license." />
  </a>
  <a href="https://github.com/circlemind-ai/fast-graphrag/blob/main/CONTRIBUTING.md">
    <img src="https://img.shields.io/badge/PRs-Welcome-brightgreen" alt="PRs welcome!" />
  </a>
  <a href="https://circlemind.co">
    <img src="https://img.shields.io/badge/Project-Page-Green" alt="Circlemind Page" />
  </a>
  <img src="https://img.shields.io/badge/python->=3.10.1-blue">
</h4>
<p align="center">
  <p align="center"><b>Streamlined and promptable Fast GraphRAG framework designed for interpretable, high-precision, agent-driven retrieval workflows. <br> <a href="https://circlemind.co/"> Looking for a Managed Service? » </a> </b> </p>
</p>

<h4 align="center">
  <a href="#install">Install</a> |
  <a href="#quickstart">Quickstart</a> |
  <a href="https://discord.gg/McpuSEkR">Community</a> |
  <a href="https://github.com/circlemind-ai/fast-graphrag/issues/new?assignees=&labels=&projects=&template=%F0%9F%90%9E-bug-report.md&title=">Report Bug</a> |
  <a href="https://github.com/circlemind-ai/fast-graphrag/issues/new?assignees=&labels=&projects=&template=%F0%9F%92%A1-feature-request.md&title=">Request Feature</a>
</h4>

> [!NOTE]
> Using *The Wizard of Oz*, `fast-graphrag` costs $0.08 vs. `graphrag` $0.48 — **a 6x costs saving** that further improves with data size and number of insertions. Stay tuned for the official benchmarks, and join us as a contributor!

## Features

- **Interpretable and Debuggable Knowledge:** Graphs offer a human-navigable view of knowledge that can be queried, visualized, and updated.
- **Fast, Low-cost, and Efficient:** Designed to run at scale without heavy resource or cost requirements.
- **Dynamic Data:** Automatically generate and refine graphs to best fit your domain and ontology needs.
- **Incremental Updates:** Supports real-time updates as your data evolves.
- **Intelligent Exploration:** Leverages PageRank-based graph exploration for enhanced accuracy and dependability.
- **Asynchronous & Typed:** Fully asynchronous, with complete type support for robust and predictable workflows.

Fast GraphRAG is built to fit seamlessly into your retrieval pipeline, giving you the power of advanced RAG, without the overhead of building and designing agentic workflows.

## Install

**Install from PyPi (recommended)**

```bash
pip install fast-graphrag
```

**Install from source**

```bash
# clone this repo first
cd fast-graphrag
poetry install
```

## Quickstart

Set the OpenAI API key in the environment:

```bash
export OPENAI_API_KEY="sk-..."
```

Download a copy of *A Christmas Carol* by Charles Dickens:

```bash
curl https://raw.githubusercontent.com/circlemind-ai/fast-graphrag/refs/heads/main/mock_data.txt > ./book.txt
```

Use the Python snippet below:

```python
from fast_graphrag import GraphRAG

DOMAIN = "Analyze this story and identify the characters. Focus on how they interact with each other, the locations they explore, and their relationships."

EXAMPLE_QUERIES = [
    "What is the significance of Christmas Eve in A Christmas Carol?",
    "How does the setting of Victorian London contribute to the story's themes?",
    "Describe the chain of events that leads to Scrooge's transformation.",
    "How does Dickens use the different spirits (Past, Present, and Future) to guide Scrooge?",
    "Why does Dickens choose to divide the story into \"staves\" rather than chapters?"
]

ENTITY_TYPES = ["Character", "Animal", "Place", "Object", "Activty", "Event"]

grag = GraphRAG(
    working_dir="./book_example",
    domain=DOMAIN,
    example_queries="\n".join(EXAMPLE_QUERIES),
    entity_types=ENTITY_TYPES
)

with open("./book.txt") as f:
    grag.insert(f.read())

print(grag.query("Who is Scrooge?").response)
```

The next time you initialize fast-graphrag from the same working directory, it will retain all the knowledge automatically.

## Contributing

Whether it's big or small, we love contributions. Contributions are what make the open-source community such an amazing place to learn, inspire, and create. Any contributions you make are greatly appreciated. Check out our [guide](https://github.com/circlemind-ai/fast-graphrag/blob/main/CONTRIBUTING.md) to see how to get started.

Not sure where to get started? You can join our [Discord](https://discord.gg/McpuSEkR) and ask us any questions there.

## Philosophy

Our mission is to increase the number of successful GenAI applications in the world. To do that, we build memory and data tools that enable LLM apps to leverage highly specialized retrieval pipelines without the complexity of setting up and maintaining agentic workflows.

## Open-source or Managed Service

This repo is under the MIT License. See [LICENSE.txt](https://github.com/circlemind-ai/fast-graphrag/blob/main/LICENSE) for more information.

The fastest and most reliable way to get started with Fast GraphRAG is using our managed service. Your first 100 requests are free every month, after which you pay based on usage.

<h1 align="center">
  <img width="800" src="demo.gif" alt="circlemind fast-graphrag demo">
</h1>

To learn more about our managed service, [book a demo](https://circlemind.co/demo) or see our [docs](https://docs.circlemind.co/quickstart).

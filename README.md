# 🎨 GenOps - Generative Operations Platform

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRO](https://img.shields.io/badge/PRO-Architecture-blue.svg)](https://websim.com/@Leirbag/ai-architectures)
[![BFS](https://img.shields.io/badge/Processing-BFS-green.svg)](https://en.wikipedia.org/wiki/Breadth-first_search)

> **Generative Operations Platform with CI-like multimodal pipeline for content generation, testing, versioning, and deployment using BFS layer-by-layer processing with strategic interconnections to EC-RAG, AgentOps, and MetaReasoner**

---

## 📋 Table of Contents

- [What This Architecture Does](#what-this-architecture-does)
- [Visual BFS Flow](#visual-bfs-flow)
- [Why BFS > DFS](#why-bfs--dfs)
- [Repository Structure (Screaming Architecture)](#repository-structure-screaming-architecture)
- [Strategic Interconnections](#strategic-interconnections)
- [Roles & Personas](#roles--personas)
- [Required Skills](#required-skills)
- [BFS Workflow Tasks](#bfs-workflow-tasks)
- [AI-Powered Features](#ai-powered-features)
- [Optimization Strategy](#optimization-strategy)
- [Recommended Use Cases](#recommended-use-cases)
- [Quick Start Guide](#quick-start-guide)
- [Docker Compose Example](#docker-compose-example)
- [CI/CD Pipeline Template](#cicd-pipeline-template)
- [Export Capabilities](#export-capabilities)
- [Integration Helpers](#integration-helpers)
- [License](#license)

---

## 🎯 What This Architecture Does

**GenOps** is a **Generative Operations Platform** that implements a CI-like multimodal pipeline for automated asset generation, quality assurance, and deployment. Unlike traditional sequential approaches, GenOps uses **Breadth-First Search (BFS)** processing to execute all generation tasks in parallel layers, ensuring:

- ⚡ **Parallel execution** across multiple generators
- 🔄 **No recursion** - all async parallel execution
- ✅ **Layer-by-layer validation** at each BFS level
- 📦 **Automated deployment** to CDN/storage

### Core Capabilities:

```
┌─────────────────────────────────────────────────────────────┐
│  GenOps Pipeline: Multimodal Asset Generation (BFS)         │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  Asset Request ──> Layer 1 (Optimize) ──> Layer 2 (Gen)   │
│                                              │              │
│                                              ├─> Stable     │
│                                              │   Diffusion  │
│                                              │              │
│                                              └─> Layer 3    │
│                                                  (QA)       │
│                                                   │         │
│                                              Layer 4        │
│                                              (Deploy)       │
└─────────────────────────────────────────────────────────────┘

```

---

## 🌊 Visual BFS Flow

### Layer-by-Layer Processing

GenOps processes asset generation in **4 distinct BFS layers**, where each layer completes fully before moving to the next:

```
┌──────────────────────────────────────────────────────────────┐
│  LAYER 1: PROMPT OPTIMIZATION (BFS)                          │
├──────────────────────────────────────────────────────────────┤
│  ├─> Template Injection                                      │
│  ├─> Directional Stimulus Generation                        │
│  └─> Parameters for Embeddings                              │
└──────────────────────────────────────────────────────────────┘
                           ↓
┌──────────────────────────────────────────────────────────────┐
│  LAYER 2: ASSET SYNTHESIS (PARALLEL)                         │
├──────────────────────────────────────────────────────────────┤
│  ├─> Parallel Generators (Stable Diffusion, DALL-E, etc)    │
│  └─> Raw Asset Collection (Async Caller)                    │
└──────────────────────────────────────────────────────────────┘
                           ↓
┌──────────────────────────────────────────────────────────────┐
│  LAYER 3: QUALITY ASSURANCE                                  │
├──────────────────────────────────────────────────────────────┤
│  ├─> Aesthetic Scoring (CLIP)                               │
│  ├─> Technical Validation                                    │
│  └─> Policy Filter                                          │
└──────────────────────────────────────────────────────────────┘
                           ↓
┌──────────────────────────────────────────────────────────────┐
│  LAYER 4: DELIVERY                                           │
├──────────────────────────────────────────────────────────────┤
│  ├─> CI/CDN Upload                                           │
│  └─> Metadata Tagging                                        │
└──────────────────────────────────────────────────────────────┘
```

---

## ⚡ Why BFS > DFS

| Aspect | BFS (Breadth-First) ✅ | DFS (Depth-First) ❌ |
|--------|----------------------|---------------------|
| **Parallelization** | Natural parallel execution at each layer | Sequential, one path at a time |
| **Resource Usage** | Balanced across all generators | Uneven, can bottleneck |
| **Failure Handling** | Isolated to specific layer | Cascading failures |
| **Optimization** | Cache-friendly (Layer 2) | Cache-inefficient |
| **Debugging** | Clear layer boundaries | Complex call stacks |
| **Scalability** | Horizontal scaling per layer | Vertical scaling only |

**GenOps Choice:** BFS ensures all asset generation happens in parallel (Layer 2), then all QA happens together (Layer 3), maximizing throughput and resource utilization.

---

## 📁 Repository Structure (Screaming Architecture)

```
arch-genops/
├── src/
│   ├── layers/
│   │   ├── layer1_prompt_optimization.py
│   │   ├── layer2_asset_synthesis.py
│   │   ├── layer3_quality_assurance.py
│   │   └── layer4_delivery.py
│   ├── generators/
│   │   ├── stable_diffusion.py
│   │   ├── dalle_interface.py
│   │   └── comfyui_adapter.py
│   ├── validators/
│   │   ├── clip_scorer.py
│   │   ├── technical_validator.py
│   │   └── policy_filter.py
│   └── deployers/
│       ├── cdn_uploader.py
│       └── metadata_tagger.py
├── config/
│   ├── pipeline.yaml
│   └── generators.json
├── tests/
├── docs/
├── docker-compose.yml
├── Dockerfile
├── requirements.txt
├── README.md
└── LICENSE
```

The structure **screams "Generative Pipeline"** – you instantly see layers, generators, validators, and deployers.

---

## 🔗 Strategic Interconnections

### Knowledge Graph

GenOps integrates with **7 other PrompTitecture architectures**:

```
          MCP-Swarm       SaaS-AI       EAI-MHIA
              │             │             │
              └───────┬───────┘             │
                    │                       │
        MetaReasoner──┤     GenOps (YOU)      ├──AgentOps
                    │                       │
              ┌───────┴───────┐             │
              │             │             │
            RCOP        EC-RAG          DCE
```

### Crosspoints:

- **⇄ EC-RAG** [LINKED] - Shared stages/infra/dataflow anchors detected (SFx, parallel)
- **⇄ AgentOps** [LINKED] - Shared stages/infra/dataflow anchors detected (nBn)
- **⇄ DCE** [LINKED] - Shared stages/infra/dataflow anchors detected (parallel)
- **⇄ MCP-Swarm** [LINKED] - Shared stages/infra/dataflow anchors detected (SFx, parallel)
- **⇄ EAI-MHIA** [LINKED] - Shared stages/infra/dataflow anchors detected (SFx, parallel)
- **⇄ SaaS-AI** [LINKED] - Shared stages/infra/dataflow anchors detected (SFx, parallel)
- **⇄ RCOP** [LINKED] - Shared stages/infra/dataflow anchors detected (SFx)

---

## 👥 Roles & Personas

- **Creative Technologist** - Designs prompt templates and optimization strategies
- **Technical Artist** - Configures generators and quality thresholds
- **Workflow Automater** - Orchestrates CI/CD pipelines for assets
- **Quality Agent** - Monitors aesthetic scores and compliance

---

## 🎯 Required Skills

- Prompt engineering (template design, embeddings)
- ComfyUI pipelines (node-based generation workflows)
- CI/CD for media (asset versioning, CDN deployment)
- Asset-metadata standards (IPTC, XMP, Dublin Core)

---

## 🌊 BFS Workflow Tasks

### ① Layer 1: Prompt Optimization (BFS)

- **Template Injection**: Insert variables into base prompts
- **Directional Stimulus Generation**: Add style/mood modifiers
- **Parameters for Embeddings**: Configure LoRA, hypernetworks

### ② Layer 2: Asset Synthesis (Parallel)

- **Parallel Generators**: Stable Diffusion, DALL-E, Midjourney APIs
- **Raw Asset Collection**: Async caller gathers all outputs

### ③ Layer 3: Quality Assurance

- **Aesthetic Scoring (CLIP)**: Rate visual appeal
- **Technical Validation**: Check resolution, format, metadata
- **Policy Filter**: Ensure content compliance

### ④ Layer 4: Delivery

- **CI/CDN Upload**: Deploy to Cloudflare, AWS S3, etc.
- **Metadata Tagging**: Add searchable keywords, attribution

---

## 🧠 AI-Powered Features

### AI Deepening Analysis

> **"Generative Asset Pipeline is a key component in complex pipelines."**

### 🚀 Optimization Strategy

- **Enable caching at Layer 2** to reuse generated assets for similar prompts
- Reduces API costs and improves response time

### 💡 Recommended Use Cases

1. **General Automation** - Batch generation for marketing campaigns
2. **Specific Domain Task** - Medical illustration, architectural visualization

---

## 🚀 Quick Start Guide

```bash
# Clone repository
git clone https://github.com/GaboBase/arch-genops.git
cd arch-genops

# Install dependencies
pip install -r requirements.txt

# Configure generators
cp config/generators.json.example config/generators.json
# Edit with your API keys

# Run pipeline
python src/main.py --prompt "cyberpunk city at night" --count 5
```

---

## 🐳 Docker Compose Example

```yaml
version: '3.8'

services:
  genops:
    build: .
    environment:
      - STABLE_DIFFUSION_API=https://api.stability.ai
      - CDN_ENDPOINT=https://cdn.example.com
    volumes:
      - ./output:/app/output
      - ./cache:/app/cache
    ports:
      - "8080:8080"

  redis:
    image: redis:7-alpine
    ports:
      - "6379:6379"

  postgres:
    image: postgres:15
    environment:
      - POSTGRES_DB=genops
      - POSTGRES_PASSWORD=genops_secret
    volumes:
      - pgdata:/var/lib/postgresql/data

volumes:
  pgdata:
```

---

## 🔧 CI/CD Pipeline Template

```yaml
name: GenOps Asset Pipeline

on:
  push:
    branches: [main]
  workflow_dispatch:

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v3
      
      - name: Set up Python
        uses: actions/setup-python@v4
        with:
          python-version: '3.11'
      
      - name: Install dependencies
        run: pip install -r requirements.txt
      
      - name: Layer 1 - Optimize Prompts
        run: python src/layers/layer1_prompt_optimization.py
      
      - name: Layer 2 - Generate Assets (Parallel)
        run: python src/layers/layer2_asset_synthesis.py
        env:
          STABLE_DIFFUSION_KEY: ${{ secrets.SD_API_KEY }}
      
      - name: Layer 3 - Quality Check
        run: python src/layers/layer3_quality_assurance.py
      
      - name: Layer 4 - Deploy to CDN
        run: python src/layers/layer4_delivery.py
        env:
          CDN_KEY: ${{ secrets.CDN_API_KEY }}
```

---

## 📦 Export Capabilities

GenOps supports **3 export formats** (integrated from Estrategias v47):

1. **Detailed JSON** - Complete architecture data with BFS metrics and interconnection graphs
2. **Markdown Docs** - Human-readable documentation
3. **Full System** - Orchestration plans with strategic interconnections

---

## 🧩 Integration Helpers

### WebSim API Integration

```javascript
fetch('https://websim.com/api/generate', {
  method: 'POST',
  body: JSON.stringify({
    architecture: 'genops',
    prompt: 'futuristic robot',
    layers: ['optimize', 'generate', 'qa', 'deploy']
  })
});
```

---

## 📄 License

MIT License - See [LICENSE](LICENSE) file for details.

---

## 🔗 Related Architectures

- [arch-ec-rag](https://github.com/GaboBase/arch-ec-rag) - Enterprise Cognitive RAG
- [arch-agentops](https://github.com/GaboBase/arch-agentops) - Self-healing Infrastructure
- [arch-mcp-swarm](https://github.com/GaboBase/arch-mcp-swarm) - Decentralized Agent Coordination
- [arch-rcop](https://github.com/GaboBase/arch-rcop) - Recursive Cognitive Orchestration

---

**Part of the [PrompTitecture Ecosystem](https://websim.com/@Leirbag/ai-architectures) v2.0**

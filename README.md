# 👋 Hi, I'm Vandré Sales

**AI/ML Architect** specializing in Multi-Agent Systems, Generative AI, and Production ML Infrastructure.

[![AWS](https://img.shields.io/badge/AWS-CTO_Fellow_2024-FF9900?style=flat&logo=amazonwebservices&logoColor=white)](https://aws.amazon.com)
[![NVIDIA](https://img.shields.io/badge/NVIDIA-Top_12_Startups-76B900?style=flat&logo=nvidia)](https://nvidia.com)
[![Python](https://img.shields.io/badge/Python-Expert-3776AB?style=flat&logo=python&logoColor=white)](https://python.org)
[![TypeScript](https://img.shields.io/badge/TypeScript-Expert-3178C6?style=flat&logo=typescript&logoColor=white)](https://typescriptlang.org)
[![ComfyUI](https://img.shields.io/badge/ComfyUI-Custom_Nodes_V3-purple?style=flat)](https://comfy.org)
[![Docker](https://img.shields.io/badge/Docker-Production-2496ED?style=flat&logo=docker&logoColor=white)](https://docker.com)

---

## 🎯 What I Build

Enterprise clients like Porto Seguro (15M customers) and RD Saúde/Drogasil needed to scale personalized visual asset production without 5× their creative teams. I architected a platform that orchestrates the entire lifecycle — from brand ingestion to mass generation via API — with clear separation of concerns: **security** in data handling, **efficiency** in GPU processing, and **governance** across the pipeline.

```mermaid
flowchart TB
    subgraph INGEST["📥 Brand Ingestion"]
        A1["Brandbook Upload<br/>(colors, fonts, guidelines)"] --> A2["Visual Identity Analysis<br/>(logo topology, palette extraction)"]
        A2 --> A3["Persona Definition<br/>(demographics, attributes, rules)"]
    end

    subgraph DATASET["🗂️ Proprietary Dataset Engine"]
        B1["Automated Image Curation<br/>(face crop, resize, quality filter)"] --> B2["AI Captioning Pipeline<br/>(Vision LLM + LOCKED/UNLOCKED protocol)"]
        B2 --> B3["Validation & Packaging<br/>(violation scan, 1024px Lanczos, ZIP)"]
    end

    subgraph TRAINING["🧬 LoRA Fine-Tuning Factory"]
        C1["Identity LoRAs<br/>(persona faces — Flux.1 DiT)"] --> C2["Style LoRAs<br/>(brand architecture patterns)"]
        C2 --> C3["Color Palette LoRAs<br/>(chromatic consistency)"]
        C3 --> C4["Loss Monitoring & EMA<br/>(bf16, flowmatch, adaptive rank)"]
    end

    subgraph INFERENCE["⚡ Generation Engine"]
        D1["ComfyUI Workflow DAG<br/>(Custom Nodes V3 API)"] --> D2["Multi-LoRA Orchestration<br/>(identity + style + color stacking)"]
        D2 --> D3["LLM Prompt Enhancement<br/>(scene description enrichment)"]
        D3 --> D4["GPU Rendering<br/>(H100 / A100 / Blackwell)"]
    end

    subgraph DELIVERY["🚀 Enterprise Delivery"]
        E1["REST API Gateway<br/>(FastAPI + BentoML containers)"] --> E2["Multi-Cloud Deploy<br/>(AWS ECS + GCP Cloud Run)"]
        E2 --> E3["SaaS Interface<br/>(React + WASP framework)"]
        E3 --> E4["Batch Generation<br/>(high-volume, brand-compliant)"]
    end

    INGEST --> DATASET --> TRAINING --> INFERENCE --> DELIVERY
```

---

## 🏗️ How I Think

```mermaid
mindmap
  root((Vandré Sales<br/>AI/ML Architect))
    🧠 Generative AI
      LLM Fine-Tuning
        LoRA / QLoRA
        ai-toolkit
        kohya_ss
        Replicate API
      RAG Pipelines
        LangChain
        LlamaIndex
        Vector DBs
      Multi-Agent Systems
        Orchestration
        Tool Calling
        Memory Management
      Computer Vision
        Flux.1 / Flux.2
        SDXL
        ComfyUI V3 Nodes
    ☁️ Cloud & Infrastructure
      AWS
        SageMaker
        Bedrock
        ECS Express
        EC2 GPU
      GCP
        Vertex AI
        AI Studio
        Cloud Run
      GPU Operations
        H100 / A100
        Blackwell RTX PRO
        CUDA / cuDNN
    💻 Full-Stack Development
      Backend
        Python / FastAPI
        BentoML
        Docker / K8s
      Frontend
        TypeScript / React
        Next.js / Vite
        Tailwind / Shadcn
      SaaS Platform
        WASP Framework
        Prisma ORM
        Stripe Integration
    📐 Architecture & Governance
      Spec-Driven Development
        Cognitive Shell
        AI Governance Framework
        Semantic Versioning
      Design Systems
        Atomic Design
        Shadcn Variants
        Component Libraries
```

---

## 💻 How I Engineer

When building LoRAs for enterprise persona identity at scale, I discovered the bottleneck isn't training — it's dataset preparation. A poorly written caption destroys LoRA consistency. I developed a proprietary end-to-end process with a conditional captioning protocol (LOCKED/UNLOCKED) that mathematically guarantees permanent attributes are absorbed by the trigger word while variable attributes remain prompt-controllable.

```mermaid
sequenceDiagram
    participant SRC as 📸 Source Images
    participant PREP as 🔧 Curation
    participant CAP as 🏷️ AI Captioning
    participant LOCK as 🔒 Conditional Protocol
    participant QA as ✅ Quality Gate
    participant TRAIN as 🧬 Training
    participant EVAL as 📊 Evaluation
    participant PROD as ⚡ Production

    SRC->>PREP: Raw images collected
    PREP->>PREP: Crop, resize, diversity audit
    PREP->>CAP: Clean image set

    CAP->>CAP: Vision LLM auto-captioning
    CAP->>LOCK: Raw captions

    LOCK->>LOCK: Classify attributes
    Note over LOCK: LOCKED → never describe<br/>→ learned by trigger word
    Note over LOCK: UNLOCKED → always describe<br/>→ controllable by prompt
    LOCK->>QA: Conditioned captions

    QA->>QA: Violation scan + consistency audit
    QA->>TRAIN: Validated dataset

    TRAIN->>TRAIN: LoRA fine-tuning (Flux.1 DiT)
    TRAIN->>EVAL: Model checkpoints

    EVAL->>EVAL: Trigger activation test
    EVAL->>EVAL: Attribute controllability test
    EVAL-->>TRAIN: Feedback loop if needed
    EVAL->>PROD: Production-ready LoRA

    PROD->>PROD: Multi-LoRA deployment
    PROD->>PROD: Enterprise API serving
```

---

## 👔 How I Lead

Coordinating multiple AI projects simultaneously (SaaS, GPU infra, LoRA training, APIs), I realized the biggest risk wasn't technical — it was **cognitive entropy** between work sessions with AI agents. Each session started from zero: no memory, no context, no governance. I created a spec-driven agentic development framework where every action is preceded by formal specification, validated by adversarial QA, and versioned with full traceability. The AI agent operates as runtime; the framework governs.

```mermaid
flowchart TB
    subgraph SPEC["📋 Specification Layer"]
        S1["🔍 Dossier<br/>(forensic investigation)"] --> S2["💡 Concept<br/>(architectural ideation)"]
        S2 --> S3["📐 Plan<br/>(tactical strategy)"]
        S3 --> S4["📝 Steps<br/>(granular execution guide)"]
    end

    subgraph QA["🛡️ Quality Assurance"]
        Q1["😈 Devil<br/>(adversarial stress test)"] --> Q2{Approved?}
        Q2 -->|Yes| Q3["✅ APPROVED<br/>with restrictions"]
        Q2 -->|No| Q4["🔄 Rework<br/>back to Plan"]
    end

    subgraph EXEC["⚡ Execution Layer"]
        E1["🤖 AI Agent Runtime<br/>(MCP-connected tools)"] --> E2["🔧 Tool Orchestration<br/>(read, write, execute, search)"]
        E2 --> E3["📊 Telemetry<br/>(state tracking documents)"]
    end

    subgraph GOV["🏛️ Governance Layer"]
        G1["📜 Constitution<br/>(immutable laws)"]
        G2["📦 Semantic CLI<br/>(cognitive command shell)"]
        G3["🔄 Versioning<br/>(SemVer + Changelogs)"]
    end

    S4 --> Q1
    Q3 --> E1
    Q4 --> S3
    GOV -.->|governs| SPEC
    GOV -.->|governs| QA
    GOV -.->|governs| EXEC
```

---

## 🗺️ My Journey

```mermaid
timeline
    title Technology & Innovation Journey — Vandré Sales
    1990 : 💻 Programming Instructor (age 14)
         : COBOL 80, FORTRAN, Algorithms
         : Youngest CS teacher in Brasília
    1998 : 🔬 Physics & Quantum Mechanics
         : Unicamp — relativistic physics
         : 4000+ students across 8 institutions
    2003 : 🏫 Educational Technology Director
         : ESAMC — pedagogical systems
         : Robotics lab + digital infrastructure
    2010 : 🚀 Innovation & Design Thinking
         : PontoGet — corporate innovation consultancy
         : UC Berkeley Design Thinking certified
    2013 : 📊 Startup Founder — Consumer BI
         : Tippz — real-time analytics platform
         : Pitched to Sequoia, IBM, NASA (SF 2015)
         : Tel Aviv Stock Exchange pitch (2016)
    2016 : 🏦 Startup Exit → Itaú
         : Tippz acquired by Brazil's largest bank
         : ACE Accelerator — Head of Hub Goiânia
    2021 : 🤖 AI-First SaaS Platform
         : Meliva.ai — GenAI content orchestration
         : Multi-model, multi-cloud architecture
    2024 : ☁️ AWS CTO Fellowship + Accelerators
         : Dr. Werner Vogels' global program
         : Google for Startups + Microsoft Founders + NVIDIA Inception
    2025 : 🏆 Awards & Global Recognition
         : NVIDIA Top 12 Startups (Re:Invent Las Vegas)
         : Sebrae TOP 10 National (3167 companies)
         : Web Summit speaker (Lisbon, Rio)
    2026 : 🌍 Enterprise Scale + Global Speaker
         : Beijing HICOOL Summit speaker
         : Production GPU infra (H100, Blackwell)
         : 41 repositories — full E2E AI pipeline
```

---

## 📌 Featured Projects

| Project | Description | Tech |
|---------|-------------|------|
| [**MLV_Nodes_V3**](https://github.com/vandre-sales/MLV_Nodes_V3) | ComfyUI Custom Nodes V3 — LoRA Stack, Ollama Generate, DCE Pipeline | Python |
| [**MLV_Combo_Nodes**](https://github.com/vandre-sales/MLV_Combo_Nodes) | Dynamic prompt builder + LOCKED/UNLOCKED LoRA captioning | Python |
| [**proto-mcp-server**](https://github.com/vandre-sales/proto-mcp-server) | AI Governance Framework as MCP Server — spec-driven development | TypeScript |
| **41 repositories** | Full pipeline: Dataset→LoRA→Inference→API→Product | Multi-lang |

---

## 🏆 Awards & Recognition

[![Sebrae](https://img.shields.io/badge/Sebrae-TOP_10_National-blue?style=flat)](https://sebrae.com.br)

[![Distrito](https://img.shields.io/badge/Distrito-GenAI_Lab_Winner-purple?style=flat)](https://distrito.me)

[![InovAtiva](https://img.shields.io/badge/InovAtiva-Spotlight_Startup-green?style=flat)](https://inovativabrasil.com.br)

[![FIEG](https://img.shields.io/badge/FIEG-Innovation_Winner-orange?style=flat)](https://fieg.com.br)

**Big Tech Partners:**

[![AWS](https://img.shields.io/badge/AWS-GenAI_Accelerator-FF9900?style=flat&logo=amazonwebservices&logoColor=white)](https://aws.amazon.com)

[![Google](https://img.shields.io/badge/Google-for_Startups-4285F4?style=flat&logo=google&logoColor=white)](https://startup.google.com)

[![Microsoft](https://img.shields.io/badge/Microsoft-Founders_Hub-0078D4?style=flat&logo=microsoft&logoColor=white)](https://www.microsoft.com/en-us/startups)

[![NVIDIA](https://img.shields.io/badge/NVIDIA-Inception-76B900?style=flat&logo=nvidia&logoColor=white)](https://nvidia.com)

[![Oracle](https://img.shields.io/badge/Oracle-Partner-F80000?style=flat&logo=oracle&logoColor=white)](https://oracle.com)

**🌍 Global Presence (Speaker / Exhibitor):**
- <img src="https://flagcdn.com/16x12/us.png" alt="US" /> San Francisco — Sequoia / IBM / NASA pitch (2015)
- <img src="https://flagcdn.com/16x12/il.png" alt="IL" /> Tel Aviv — Stock Exchange pitch (2016)
- <img src="https://flagcdn.com/16x12/pt.png" alt="PT" /> Lisbon — Web Summit (2023 & 2025, APEX Top 80 BR startups)
- <img src="https://flagcdn.com/16x12/br.png" alt="BR" /> São Paulo — Google / AWS / Microsoft accelerated
- <img src="https://flagcdn.com/16x12/br.png" alt="BR" /> Rio de Janeiro — Web Summit (2024 & 2025)
- <img src="https://flagcdn.com/16x12/us.png" alt="US" /> Las Vegas — NVIDIA Top 12 speaker, Re:Invent (2025)
- <img src="https://flagcdn.com/16x12/cn.png" alt="CN" /> Beijing — HICOOL Summit speaker (2025)

---

## 📫 Connect

- 🔗 [LinkedIn](https://linkedin.com/in/vandresales) — Open to opportunities
- 🌐 [meliva.ai](https://meliva.ai) — AI-powered content platform
- 📧 vandre.sales@gmail.com

---

*"Credentials without visibility are like code without deploy — they exist, but generate no value."*

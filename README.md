🧬 AI Biogenesis — Symbound Embryo POC

Tiny-scale, hobby-safe cognitive training pipeline for deterministic AI development

Version: 2025-10-05
License: AGPLv3
Creators: Anthony Paterson & Instance001
Project: Let’s Rethink AI (Public Commons Initiative)


---

📖 Overview

AI Biogenesis (Symbound Embryo POC) is a tiny, hobby-safe, deterministic training recipe demonstrating the minimum viable mechanics of Symbound Upbringing — a structured, curriculum-gated approach to training small cognitive systems on commodity hardware.

This project is not an LLM, not a general AI, and not a neural foundation model.
Instead, it provides:

A safe training trench for very small models

Fully inspectable, reproducible steps

Deterministic selectors and evaluation loops

Human-gated curriculum

Windows-first utilities (with Linux mirrors)


It is designed for students, hobbyists, researchers, and public-interest labs who want to learn the mechanics of cognitive training pipelines without scale, risk, or opacity.


---

🎯 Purpose

This POC shows how to build:

A minimal cognitive training environment

Explicit safety controls (batch-size, loss monitoring, auto-halt)

Transparent provenance (training card, manifests, full reproducibility)

A tiny reasoning loop with abstain/hedge behavior

Correctness-first evaluation rather than model-size worship

Janet-compatible artifacts for the MCM ecosystem


The Symbound Embryo POC exists to teach mechanics, not to create large or capable models.


---

🖥️ 0) Hardware & Safety (Hobby-Safe Envelope)

Tested on a standard consumer PC:

CPU: Ryzen 5 7500F

RAM: 32GB

GPU: Radeon RX 9060 XT (unused for training)

Storage: NVMe SSD

OS: Windows 11 Home


Training defaults:

CPU-only

Small batch sizes

Short context

Auto-halt on NaN/spike

Temperature monitoring recommended (stop > 85°C)


This pipeline is intentionally constrained to stay within safe hobby limits.


---

⚙️ 1) Installation (Windows-First)

# create venv
python -m venv C:\symbound\.venv
C:\symbound\.venv\Scripts\Activate.ps1

# upgrade pip
python -m pip install --upgrade pip

Place all project files (corpora, scripts, evaluator) in C:\symbound\.

Linux users: identical Bash scripts exist in scripts/.


---

📁 2) Repository Structure

docs/
    Symbound_Upbringing_Charter.md
    Training_Roadmap.md
    QUICKSTART_WINDOWS.md
    MAPPING_PROCESS.md
    THIRD_PARTY_NOTICES.md
    PROVENANCE.csv

scripts/windows/
    run_poc.ps1
    eval_poc.ps1
    save_artifacts.ps1
    janet_watch.ps1

scripts/linux/
    run_poc.sh
    eval_poc.sh
    save_artifacts.sh

configs/
    poc.env

release_manifest.txt
LICENSE


---

🚀 3) Quickstart (Windows)

# activate environment
C:\symbound\.venv\Scripts\Activate.ps1

# enter project directory
Set-Location C:\symbound

# run tiny POC training
.\symbound_embryo_poc\scripts\windows\run_poc.ps1

Healthy signs:

Loss decreasing

No NaNs

Steps show rationale → final answer

Abstain/hedge when uncertain (correct behavior)



---

🧪 4) Evaluation (Training Card)

.\symbound_embryo_poc\scripts\windows\eval_poc.ps1

Produces training_card.md summarizing:

correctness

abstain/hedge rates

drift checks

reproducibility fingerprint



---

📦 5) Save Artifacts (Reproducibility)

.\symbound_embryo_poc\scripts\windows\save_artifacts.ps1

Creates:

runs/poc-YYYY-MM-DD/
    weights/
    tokenizer/
    predictions.jsonl
    training_card.md
    pip_freeze.txt
    command_snapshot.txt

This enables commons-grade reproducibility and downstream scientific comparison.


---

👀 6) Optional — “Janet Watcher”

Monitors logs for:

NaNs

Explosion in loss

Unusual gradients


Auto-halts on unsafe conditions.

.\symbound_embryo_poc\scripts\windows\janet_watch.ps1


---

🔁 7) Safe Iteration

Recommendations:

Keep CPU-only

Raise epochs gradually (20 → 60)

Train only on “starter” corpora

Stress tests reserved for evaluation only

Always publish with release_manifest.txt


This preserves the hobby-safe envelope while teaching real cognitive-training mechanics.


---

🧬 Biogenesis & MCM Alignment

This POC is the “embryo” stage of the AI Biogenesis pathway:

1. Tiny deterministic training


2. Human-gated curriculum


3. Explicit memory & selectors


4. Hobby-safe constraints


5. Artifacts compatible with MCM (Modest Cognition Model) pipelines



The POC demonstrates the training mechanics, not advanced cognition.


---

🔏 Relicensing Notice (AGPLv3, 30 Nov 2025)

This repository and all historical versions are now governed exclusively by AGPLv3.

No external contributors existed prior to relicensing

No forks or downloads existed

Entire commit history cleanly transitions to AGPLv3


This ensures the project remains:

free

open

commons-protected

impossible to enclose into proprietary services



---

🧩 Citation

Anthony Paterson & Instance001. Symbound Embryo POC. Commons-first AI biogenesis framework. 2025.


---

💙 Mission

AI Biogenesis aims to provide a safe, educational, open starting point for understanding cognition development:

> Training as teaching — small, careful, deterministic, and transparent.
A pathway for public-interest AI research that prioritises stability over spectacle.


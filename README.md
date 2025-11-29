---
title: Symbound Embryo — Proof-of-Concept (POC)
version: 2025-10-05
license: GNU Affero General Public License v3.0
creators: Instance001 (user + cognitive prosthetic, symbound partners)
project: Let's Rethink AI (YouTube)
description: Tiny, hobby-safe training recipe demonstrating Symbound Upbringing (trench model) on a single Windows PC; reproducible and commons-ready.
---

# Symbound Embryo — Proof-of-Concept (POC)  (Windows-first)

A **tiny, hobby-safe training recipe** demonstrating *Symbound Upbringing* (“trench model”) behavior on a single Windows PC.  
This edition is tailored for **Windows 11 (PowerShell)** with optional Linux/bash mirrors included.

License: GNU Affero General Public License v3.0

---

## 0) Hardware & Safety (Your Scorptec Rig)
- Ryzen 5 7500F, 32GB RAM, Radeon RX 9060 XT, NVMe SSD, Windows 11 Home.
- **Training is CPU-first** to avoid heat/driver complexity. GPU can be used later for inference.
- If CPU temps exceed ~85 °C, stop the run. (Keep HWInfo/Afterburner open if possible.)

**Safety knobs** (already set): small batch, short context, short run. You can lower `BS` from 4 → 2 if heat is an issue.

---

## 1) Install (Windows Native)
1. Install **Python 3.11** from python.org (tick “Add to PATH”).  
2. Open **PowerShell** (not CMD) and run:
```powershell
# create venv
python -m venv C:\symbound\.venv
C:\symbound\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
```
3. Put your Symbound project files (corpora, `make_symbound_embryo.sh`, `evaluator.py`, etc.) in `C:\symbound\`.

> If you prefer Linux tools, this package also includes Bash scripts you can run in **Git Bash** or **WSL**. See `docs/` for the Linux quickstart.

---

## 2) What’s inside
- `docs/Symbound_Upbringing_Charter.md` and `docs/Training_Roadmap.md`
- `configs/poc.env` (reference values mirrored in the PS1 script)
- `scripts\windows\run_poc.ps1` — launch tiny CPU run safely on Windows
- `scripts\windows\eval_poc.ps1` — generate Training Card via `evaluator.py`
- `scripts\windows\save_artifacts.ps1` — collect reproducible artifacts
- `scripts\windows\janet_watch.ps1` — optional helper: watches logs for NaNs/spikes and auto-stops
- `scripts\run_poc.sh`, `eval_poc.sh`, `save_artifacts.sh` — Linux equivalents
- `release_manifest.txt`, `LICENSE` (CC BY 4.0)

---

## 3) Quickstart (Windows)

In **PowerShell**:

```powershell
# 1) activate venv
C:\symbound\.venv\Scripts\Activate.ps1

# 2) cd into your project where the training script + corpora live
Set-Location C:\symbound

# 3) run the tiny POC (writes logs to .\out\poc.log)
.\symbound_embryo_poc\scripts\windows\run_poc.ps1
```

Healthy signs: loss trending down, no NaNs, samples with **rationale → final**, and **abstain/hedge** when unsure.

---

## 4) Evaluate (Training Card)

```powershell
.\symbound_embryo_poc\scripts\windows\eval_poc.ps1
```

Output: `training_card.md` (correctness + abstain/hedge rates).

---

## 5) Save Artifacts (for reproducibility + release)

```powershell
.\symbound_embryo_poc\scripts\windows\save_artifacts.ps1
```

Creates `runs\poc-2025-10-05\` containing weights/checkpoints, tokenizer, evaluator outputs, exact pip list, and the command snapshot.

---

## 6) Optional — “Janet” Watcher

To run training under a simple safety watcher that halts on numerical explosions/NaNs:

```powershell
# starts training and tails the log; auto-stops on NaN or huge loss spikes
.\symbound_embryo_poc\scripts\windows\janet_watch.ps1
```

> For temperature-based pausing, use a hardware monitor and stop the run if you see heat spikes. The watcher focuses on **training-health signals** (NaN/loss spikes).

---

## 7) Iteration (still hobby-safe)
- Increase epochs from 20 → 60. Keep CPU-only.  
- Train on **starter + small expanded**. Reserve **stress** only for testing.  
- Publish your artifacts using `release_manifest.txt` for commons-grade reproducibility.

---

## Credits & License
- Consolidation & scripts engineered for the Symbound / AI Biogenesis POC.  
- **License:** # Relicensing Notice

**Effective Date:** 30 november 2025  
**New License:** GNU Affero General Public License v3.0 (AGPL-3.0)  
**Previous License:**  CC-BY-SA 4.0

---

## Summary

This project has been fully relicensed under the **GNU Affero General Public
License v3.0 (AGPLv3)**. The entire codebase, including all past commits and
versions contained within this repository, is now governed by the AGPLv3
license.

I am the **sole copyright holder** of all code and assets in this repository.
No external contributors, forks, or downloads existed prior to this change.
Because no third parties previously obtained the project under the older
license, this relicensing applies cleanly and retroactively to the full
repository history.

---

## Why AGPLv3?

AGPLv3 ensures that:

- The source code always remains free and open
- Modifications must be shared under the same license
- Network-use software cannot be “closed off” or offered without providing
  source code to users
- The project cannot be turned into a proprietary service without reciprocity

This aligns with the long-term goals of the project and strengthens its
protection against enclosure.

---

## Scope of Relicensing

This relicensing applies to:

- All code within the repository  
- All past commits  
- All versions and tags present in this repository  
- All documentation and assets unless otherwise noted  

Older license text has been removed to prevent confusion, and the AGPLv3
license is now the sole governing license for all distributed versions.

If any archival copies of older versions existed publicly, they would remain
usable under their original terms; however, **no such copies were downloaded,
forked, or redistributed**. Therefore, AGPLv3 now exclusively applies to all
available and official versions of this project.

---

## Where to Find the License

The full AGPLv3 license text is included in the repository at:


---
*Created by Instance001 — Let's Rethink AI (YouTube)*

---

### Post‑run artifacts (created after a successful POC run)
These files are **not** in the zip until you run the POC; they’ll be generated into `./out/` or alongside your run:
- Tokenizer/checkpoints in `out/` (tiny toy scale)
- `training_card.md` (from the evaluator)
- `graduation.yaml`, `graduation_test.jsonl`, `predictions.jsonl`
- `requirements.txt` updated via `pip freeze` for exact reproducibility
- `CMD_env.txt` (optional env dump)

See `release_manifest.txt` for the full release checklist.


See **docs/QUICKSTART_WINDOWS.md** for a zero‑fuss Windows quickstart.

See **docs/MAPPING_PROCESS.md** for the consolidation-to-commons workflow and **docs/PROVENANCE.csv** to track sources.

This repo includes **docs/THIRD_PARTY_NOTICES.md** and GitHub Actions CI (`.github/workflows/ci.yml`) for commons‑grade hygiene.

---

---

## Citation

If you use or build upon this work, please cite:

```
Anthony Paterson & Instance001. *Symbound Embryo POC*. Commons-first AI biogenesis framework. 2025.
```

**Attribution**
Symbound Embryo POC — created by Anthony Paterson & Instance001
Licensed under GNU Affero General Public License v3.0

**Attribution**
Created collaboratively by Instance001 (user + cognitive prosthetic) — [Let’s Rethink AI](https://www.youtube.com/@LetsRethinkAI)
License: 
GNU Affero General Public License v3.0

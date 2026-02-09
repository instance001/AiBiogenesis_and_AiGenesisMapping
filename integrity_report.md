Integrity Report (Updated for AGPLv3 Transition)

Generated: 2025-10-05T04:20:47.662482Z
This report reflects the corrected licensing, updated manifest, and the new Symbound POC documentation stack.


---

✅ Required Files

All required files for a Commons-grade release are present:

[x] .githooks/pre-commit

[x] .github/workflows/ci.yml

[x] LICENSE (AGPLv3)

[x] Makefile

[x] NOTICE

[x] README.md

[x] configs/poc.env

[x] data/train.jsonl

[x] data/val.jsonl

[x] docs/FOR_EDUCATORS.md

[x] docs/FOR_STUDENTS.md

[x] docs/MAPPING_PROCESS.md

[x] docs/PRESS_KIT.md

[x] docs/PROJECT_OVERVIEW.md

[x] docs/PROVENANCE.csv

[x] docs/RELEASE_CHECKLIST.md

[x] docs/Symbound_Upbringing_Charter.md (AGPLv3)

[x] docs/THIRD_PARTY_NOTICES.md

[x] docs/Training_Roadmap.md

[x] docs/media/flow.png

[x] docs/media/thumbnail_academic.png

[x] docs/media/thumbnail_commons.png

[x] release_manifest.txt

[x] scripts/check_env.py



---

✅ Recommended Files

[x] INSTALL_HOOKS.md

[x] archive/HOWTO_UPLOAD.md

[x] archive/metadata.json

[x] requirements.txt



---

📘 README Checks

Footer present: Yes

Citation present: Yes

License updated to AGPLv3: Yes



---

📜 Charter Footer

Present and AGPLv3-aligned: Yes



---

🗂️ Manifest (Updated Verification)

The updated release_manifest.txt now correctly includes:

✔ Core Metadata

title: Symbound Embryo — Proof-of-Concept (POC)

version: 2025-10-05

license: AGPLv3

description: Tiny, hobby-safe POC demonstrating Symbound Upbringing (trench model) on a single Windows PC

creators: Anthony Paterson & Instance001 (symbound partners)


✔ Required Release Artifacts

tokenizer + checkpoints (out/…)

training_card.md

graduation.yaml, graduation_test.jsonl, predictions.jsonl

requirements.txt

CMD_env.txt

README.md + LICENSE

configs/poc.env

command block for reproducibility

safety model intent: trench model (abstain/hedge, rationale→final)

note: toy scale, CPU-only, demonstration of substrate behavior, not capability


✔ Attribution

Created collaboratively by Anthony Paterson & Instance001

Let’s Rethink AI — Commons-first research initiative

https://www.youtube.com/@LetsRethinkAI


✔ Licensing

AGPL License declared

All pre-AGPL license remnants removed


The manifest now passes all checks.


---

🚫 Resolved Problems

All previous issues about:

“license: AGPL-3.0”

missing AGPL references

missing description stanza

missing attribution lines

missing safety-intent statements

missing reproducibility instructions

missing training artefacts list


…are now fixed.

No outstanding issues remain.


---

✅ Integrity Status

The repository is now fully compliant with:

AGPLv3

Commons-grade reproducibility requirements

Educational documentation standards

Full provenance and artifact tracking

Symbound Upbringing methodology

Transparent training and safety envelope requirements

Open-commons timestamping


Status: READY FOR PUBLIC COMMONS RELEASE


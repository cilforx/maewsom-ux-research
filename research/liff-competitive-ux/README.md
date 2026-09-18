# LIFF Competitive UX Research

---
topic: liff-competitive-ux
status: synthesized
started: 2026-09-18
canonical: false
---

## Purpose

ศึกษาว่า MaewSom ควรแบ่งหน้าที่ระหว่าง LINE Chat, Quick Reply, Flex Message, Rich Menu และ LIFF อย่างไร โดยอ้างอิงคู่แข่ง personal finance, banking, AI finance และ LINE ecosystem.

## Current runs

| Run | Researcher | Status | Notes |
|---|---|---|---|
| `archive/liff-competitive-ux/01–06` | prior model/research run | RAW / needs cross-check | ย้ายแบบ rename-only; มีบาง competitor claims ที่ขัดกับ current primary sources |
| `runs/2026-09-18_chatgpt/independent-research.md` | ChatGPT / GPT-5.6 Sol | RAW independent pass | ทำโดยไม่ถือ legacy conclusions เป็น product truth |
| `runs/2026-09-18_gemini/2026-09-18_gemini_independent-research.md` | Gemini | RAW independent pass | indexed แล้ว; รอ cross-model synthesis |
| `runs/2026-09-18_glm-flash/2026-09-18_glm-flash_independent-research.md` | GLM Flash | RAW / needs source verification | citation tokens `turn0search*` are session-local and not portable; verify numeric/feature claims before synthesis |
| `runs/2026-09-18_glm-5.3/2026-09-18_glm-5.3_independent-research.md` | GLM 5.3 | RAW / contains known conflicts | several Thai competitor and LINE claims conflict with current checked evidence; use for hypothesis generation only until re-verified |
| `runs/2026-09-18_opus/` | Claude / Opus 4.6 | RAW independent pass | comprehensive run already present in repo; requires source verification before synthesis |
| `runs/2026-09-18_1554_gemini-3.8-flash/independent-research.md` | Gemini / 3.8 Flash | RAW / needs verification | implementation-oriented synthesis; several numeric, competitor and LINE-platform claims must be verified before use |
| `runs/2026-09-18_1602_fable-5.1/independent-research.md` | Fable / 5.1 | RAW / source-rich | strongest current run on LINE Messaging UX/platform economics; official LINE claims are high-value, secondary Thai market statistics still need targeted verification |

## Important rule

**Do not implement directly from a single research run.**

Flow:

```text
independent runs
→ verify disputed claims
→ cross-model synthesis
→ Owner Direction
→ canonical docs in cilforx/maewsom
```

## Known disputes already identified

Legacy files 01–06 และ GLM 5.3 มีข้อมูล competitor ไทยบางจุดที่ต้องตรวจใหม่ เช่น MeowJot, Nabtang, รับจ่ายจด และ BooJot ถูกอธิบายเป็น manual-heavy/limited automation ในบางส่วน ขณะที่ current product listings/evidence แสดง OCR, voice, statement หรือ automation capabilities.

Resolution rule:

> Evidence wins, not model majority.

## Synthesis — Complete

The multi-model research cycle has been cross-checked and synthesized into:

- `synthesis/01_cross-model-findings.md`
- `synthesis/02_disputed-claims.md`
- `synthesis/03_design-implications.md`

Product authority has been promoted to the main repository as:

- `cilforx/maewsom/docs/review/mochi/49-owner-direction-line-liff-trust-and-reconciliation-boundary.md`

Status:

```text
research complete
→ disputed claims checked
→ synthesis complete
→ Owner Direction accepted (OD49)
→ core flow contract NEXT
```

Do not reopen resolved research claims from individual RAW runs unless new primary evidence materially changes them.


## Run collision prevention

Independent runs are **immutable** and must never reuse another run's directory or filename.

Use:

```text
runs/YYYY-MM-DD_HHMM_<model-slug>/
└── independent-research.md
```

Examples:

```text
runs/2026-09-18_1510_gemini-pro/
runs/2026-09-18_1530_gemini-2-modern/
runs/2026-09-18_1545_gemini-flash/
```

Rules:

1. Never write a second model run into an existing run directory.
2. Never update another model's `independent-research.md`.
3. If the exact model name is unknown, use a unique owner-provided label plus timestamp.
4. A model rerun must create a new timestamped directory even if it is the same model.
5. Historical run files are append-only/immutable; corrections belong in synthesis or a new run.
6. Before creating a run, check whether the target path already exists. If it exists, choose a new timestamp/slug.

> **One execution = one unique path. No overwrite.**

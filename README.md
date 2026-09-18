# MaewSom UX Research

คลังงานวิจัย UX / Product / Competitor / LINE ecosystem / AI finance สำหรับโครงการ **MaewSom**

> **Important:** เอกสารใน repository นี้เป็น research evidence และ analysis ไม่ใช่ implementation specification โดยอัตโนมัติ

ข้อสรุปที่ถูกนำไปใช้จริงในผลิตภัณฑ์ต้องถูกยืนยันและบันทึกใน repository หลัก `cilforx/maewsom`.

## Repository rule

**Topic first, model second.**

จัดงานตามหัวข้อวิจัยก่อน แล้วค่อยแยก run ของแต่ละโมเดล เพื่อให้ค้นงานจาก “เรื่องที่กำลังตัดสินใจ” ได้ง่ายกว่าค้นจากชื่อ AI

โครงสร้างเป้าหมาย:

```text
maewsom-ux-research/
├── README.md
├── research/
│   ├── liff-competitive-ux/
│   │   ├── README.md
│   │   ├── runs/
│   │   │   ├── 2026-09-18_gemini/
│   │   │   ├── 2026-09-18_chatgpt/
│   │   │   ├── 2026-09-18_glm-flash/
│   │   │   └── 2026-09-18_<other-model>/
│   │   ├── synthesis/
│   │   └── evidence/
│   ├── line-rich-menu/
│   ├── line-platform/
│   ├── persona-relationship/
│   ├── thai-finance-behavior/
│   ├── transaction-semantics/
│   ├── reconciliation/
│   ├── ai-financial-assistant/
│   ├── monetization-premium/
│   ├── trust-privacy/
│   ├── onboarding-retention/
│   └── future-concepts/
└── archive/
```

## Research lifecycle

```text
RAW MODEL OUTPUT
        ↓
CROSS-CHECK
        ↓
SYNTHESIS
        ↓
OWNER / TEAM DECISION
        ↓
CANONICAL PRODUCT DOC
```

### Status meanings

- **RAW** — ผลจาก researcher/model รอบเดียว ยังไม่ใช่ข้อสรุปสุดท้าย
- **CROSS-CHECKED** — claims สำคัญตรวจเทียบกับ primary/official sources แล้ว
- **DISPUTED** — หลายแหล่งหรือหลายโมเดลให้ข้อมูลขัดกัน
- **SYNTHESIZED** — รวมผลหลาย research runs พร้อมระบุ conflicts และ uncertainty
- **ACCEPTED** — Owner/team นำ finding ไปใช้เป็น product direction แล้ว
- **SUPERSEDED** — มีงานใหม่แทนที่แล้ว แต่เก็บไว้เพื่อ historical trace

## Source of truth

ลำดับ authority:

```text
Owner Decision
      ↓
cilforx/maewsom canonical docs
      ↓
Cross-model synthesis
      ↓
Cross-checked research
      ↓
Individual model research
      ↓
Raw notes / hypotheses
```

ถ้า research ขัดกับ canonical docs ใน repo หลัก ให้ implementation ทำตาม canonical docs จนกว่าจะมี Owner Direction เปลี่ยนแปลง

## Current active stream — LIFF Competitive UX

**Started:** 2026-09-18

Scope:
- Thai personal finance competitors
- Thai banking / fintech
- global personal finance
- AI / conversational finance
- LINE MINI App / LIFF ecosystem

### Archived legacy package

ไฟล์ legacy 01–06 ถูกย้ายแบบ rename-only ไปที่ `archive/liff-competitive-ux/` โดยไม่มีการแก้เนื้อหา และควรถือเป็น **RAW / needs cross-check** จนกว่าจะมี synthesis:

| File | Content | Status |
|---|---|---|
| `archive/liff-competitive-ux/01_executive_summary.md` | Market direction, competitive maps, white space | RAW |
| `archive/liff-competitive-ux/02_research_matrix.md` | 50-product comparison matrix | RAW |
| `archive/liff-competitive-ux/03_deep_dives.md` | Deep dives and transaction lifecycles | RAW |
| `archive/liff-competitive-ux/04_ux_patterns_and_pain_points.md` | UX patterns and competitor pain points | RAW |
| `archive/liff-competitive-ux/05_line_and_ai_ecosystem.md` | Chat vs LIFF, LINE ecosystem, AI trust | RAW |
| `archive/liff-competitive-ux/06_maewsom_design_strategy.md` | Proposed design principles and LIFF IA | RAW / hypothesis |

**Do not treat 01–06 as canonical product requirements.**

บาง competitor claims ในไฟล์เดิมมีข้อมูลขัดกับ primary/current sources และต้อง resolve ใน synthesis.

## Independent model runs

Research เรื่องเดียวกันสามารถให้หลายโมเดลทำอย่างอิสระเพื่อลด confirmation bias.

ตัวอย่าง:

```text
research/liff-competitive-ux/runs/
├── 2026-09-18_gemini/
├── 2026-09-18_chatgpt/
└── 2026-09-18_<other-model>/
```

แต่ละ model ไม่ควรอ่าน conclusion ของอีก model ก่อนทำ independent pass ถ้าต้องการ independent validation.

หลังจากนั้นรวมผลใน:

```text
research/liff-competitive-ux/synthesis/
```

## Research provenance

ไฟล์ใหม่ควรมี metadata ด้านบนเมื่อเหมาะสม:

```yaml
---
topic: liff-competitive-ux
date: 2026-09-18
researcher: ChatGPT
model: GPT-5.6 Sol
status: raw
research_type: independent-pass
canonical: false
---
```

ถ้าไม่ทราบรุ่น model ให้ใช้ `model: unknown` และห้ามเดา.

## Naming convention

ภายในแต่ละ topic:

```text
YYYY-MM-DD_<model>_<type>.md
```

ตัวอย่าง:

```text
2026-09-18_gemini_competitor-research.md
2026-09-18_chatgpt_independent-research.md
2026-09-19_claude_critique.md
```

Synthesis:

```text
synthesis/
├── 2026-09-19_cross-model-findings.md
├── 2026-09-19_disputed-claims.md
└── 2026-09-20_design-implications.md
```

## Evidence vs inference

Research ควรแยก:

1. **Evidence** — source สนับสนุนโดยตรง
2. **Insight / Inference** — สิ่งที่ researcher ตีความ
3. **Recommendation** — สิ่งที่เสนอให้ MaewSom ทำ

Recommended chain:

```text
Evidence
↓
Insight
↓
Implication
↓
MaewSom Requirement Candidate
```

Requirement Candidate ยังไม่ใช่ requirement จริงจนกว่า Owner Direction จะรับรอง.

## Contradictory findings

ถ้าหลายโมเดลให้ข้อมูลไม่ตรงกัน:

- อย่าเลือกจากเสียงข้างมาก
- ตรวจ primary evidence
- บันทึก conflict ใน `synthesis/disputed-claims.md`
- resolve ด้วย evidence

หลักการ:

> **Evidence wins, not model majority.**

## Source quality preference

1. Official documentation
2. Official product/company source
3. LINE Developers / LINE for Business
4. App Store / Google Play
5. Reputable industry publication
6. UX case study
7. User reviews / community
8. AI-generated claim without source

## Research registry

| Topic | Date | Models | Status | Synthesis | Product Impact |
|---|---|---|---|---|---|
| LIFF Competitive UX | 2026-09-18 | ChatGPT, Gemini, GLM Flash | Active | Pending | LIFF architecture |
| LINE Rich Menu UX | existing | multiple | To index | Pending | LINE entry/navigation |
| Persona & Relationship | existing | multiple | To index | Partial | Character system |
| Monetization / Premium | existing | multiple | To index | Partial | Subscription |
| Thai Finance Behavior | partial/future | — | Open | — | User behavior |

เพิ่ม stream ใหม่ลง registry นี้เมื่อเริ่ม research topic ใหม่.

## Old research

อย่าลบงานเก่าเพียงเพราะมีงานใหม่กว่า.

ถ้าถูกแทนที่:
- mark เป็น `SUPERSEDED`
- ระบุ `superseded_by`
- ย้ายเข้า `archive/<topic>/` เมื่อเหมาะสม

## Research → main repository

```text
maewsom-ux-research
       │
       │ evidence / synthesis
       ▼
Owner Direction
       │
       ▼
cilforx/maewsom
```

Research อยู่ที่นี่เพื่ออธิบายว่า decision มาจากหลักฐานอะไร ส่วน requirement ที่ใช้ implement ต้องอยู่ repo หลัก.

## Agent instructions

AI agent ที่เข้ามาใช้ repository นี้ต้อง:

1. อ่าน `README.md` ก่อน
2. ตรวจ status ของเอกสาร
3. ห้ามใช้ RAW research เป็น requirement โดยตรง
4. ตรวจว่ามี synthesis ใหม่กว่าหรือไม่
5. ตรวจว่า finding ถูก superseded หรือไม่
6. ถ้าข้อมูลขัดกัน ให้รายงาน conflict
7. ห้ามเลือกข้อสรุปเพราะหลายโมเดลพูดเหมือนกัน
8. ให้ primary evidence มีน้ำหนักมากกว่า model opinion
9. Product decision ต้องอ้างกลับไป canonical docs ใน `cilforx/maewsom`
10. อย่าแก้ historical research ให้ดูเหมือนตรงกับ decision ปัจจุบัน

## Current priority

```text
Independent model research
        ↓
Cross-check disputed claims
        ↓
Cross-model synthesis
        ↓
LINE / LIFF responsibility model
        ↓
Financial Trust Model
        ↓
Owner Direction
        ↓
LIFF information architecture
        ↓
Wireframe
```

**Do not start visual design solely from one model's research output.**

## Repository philosophy

เป้าหมายของ repo นี้ไม่ใช่พิสูจน์ว่า MaewSom ถูกต้อง แต่เพื่อเก็บหลักฐานว่า assumption ไหนถูกหรือผิด และทำไม product จึงตัดสินใจแบบนั้น.

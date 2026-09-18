# LIFF Competitive UX Research

---
topic: liff-competitive-ux
status: active
started: 2026-09-18
canonical: false
---

## Purpose

ศึกษาว่า MaewSom ควรแบ่งหน้าที่ระหว่าง LINE Chat, Quick Reply, Flex Message, Rich Menu และ LIFF อย่างไร โดยอ้างอิงคู่แข่ง personal finance, banking, AI finance และ LINE ecosystem.

## Current runs

| Run | Researcher | Status | Notes |
|---|---|---|---|
| Legacy package `/01–06` | prior model/research run | RAW / needs cross-check | มีบาง competitor claims ที่ขัดกับ current primary sources |
| `runs/2026-09-18_chatgpt/independent-research.md` | ChatGPT / GPT-5.6 Sol | RAW independent pass | ทำโดยไม่ถือ legacy conclusions เป็น product truth |
| Gemini run | Gemini | Pending indexing | ควรเก็บแยก run แล้วค่อย synthesis |

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

Legacy files 01–06 มีข้อมูล competitor ไทยบางจุดที่ต้องตรวจใหม่ เช่น Nabtang, รับจ่ายจด และ BooJot ถูกอธิบายเป็น manual-heavy ในบางส่วน ขณะที่ current product listings/evidence แสดง OCR, voice หรือ automation capabilities.

Resolution rule:

> Evidence wins, not model majority.

## Next outputs

- `synthesis/cross-model-findings.md`
- `synthesis/disputed-claims.md`
- `synthesis/design-implications.md`

Do not start final LIFF visual design until synthesis is complete.

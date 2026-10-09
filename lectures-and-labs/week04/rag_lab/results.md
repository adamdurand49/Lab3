# RAG Lab - results

**Name:** _[Your name]_
**Date:** _[Date]_

Fill this in as you go. The README says what each section is for.

---

## Part 1: chunking and embeddings (DIY 1 and 2)

- Documents loaded: ___
- Chunks produced at 200 words: ___ (shortest ___ words, longest ___ words)
- Vector dimensionality: ___
- Did the query vector have the same dimensionality as the chunks? ___

_What did the overlap check show?_

---

## Part 2: retrieval (DIY 3 and 4)

**"what is a variable"** - top hit, score and source: ___

**"how can my code remember a number for later"** - top hit, score and source: ___

_Same meaning, different words: did both queries find the same chunk?_

**"how do I bake sourdough"** - what came back, and with what scores: ___

_One sentence on what a retrieval system does when nothing is relevant:_

---

## Part 3: grounding (DIY 5)

**Q:** What is a variable?
**A:** ___
**Source it cited:** ___

**Q:** How do I bake sourdough?
**A:** ___ (did it decline?)

---

## Part 4: chunk size (DIY 6)

| Chunk size | Right chunk found? | Noise | Notes |
|------------|--------------------|-------|-------|
| 50 words   | Yes, for both variable queries | Low, though some fragments start mid-thought | 66 chunks; variable scores 0.58 and 0.45; sourdough's top score was 0.13. The definition appeared in the top three. |
| 200 words  | Yes, for both variable queries | Moderate; retrieved chunks include neighboring programming topics | 14 chunks; variable scores 0.42 and 0.31; sourdough's top score was 0.09. |
| 800 words  | Yes, for both variable queries | High; each hit can include most or all of its document | 5 chunks; variable scores 0.42 and 0.31; sourdough's top score was 0.09. |

Small chunks can sever a fact from its subject and context, while oversized chunks bury the answer in unrelated text and waste context tokens.

---

## Part 5: long context versus retrieval (DIY 7)

Whole corpus: 5 documents, 1,970 words, approximately 2,626 tokens (words ÷ 0.75).

The answer comparison for the variable, linked-list, and HTML questions is pending: Part 5 needs `LLM_API_KEY`, which is not configured, so no model answers were generated.

```text
Whole corpus size: ................. ~2,626 tokens
Question asked: .................... [your question]
  RAG answer: ...................... [response]
  Whole-corpus answer: ............. [response]
Which was better? .................. [RAG / long context / no difference]
At what corpus size would this flip? [your reasoning]
```

Repeat for each of the three questions if the answers differed.

**The question the corpus cannot answer** (sourdough):

- No context: ___
- Whole corpus: ___
- RAG: ___

_Which of the three declined, and what made the difference?_

---

## Reflection

_When would you build retrieval, and when would you just paste everything?_

_What surprised you?_

# MMQEval

## About

This is a repository for MMQEval, the Multi-Modal Quality Evaluation model. It will contain the model definition documents, canonical schema and examples, and an academic paper describing the model and its background.

[MMQEval](https://mmqeval.org) © 2025 by Agustin Da Fieno Delucchi, Katerina Gasova, and Pavel Soukenik is licensed under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

## MMQEval Preview (v0.3)

### Model Definition

This document outlines the MMQEval quality framework, its modular structure, scoring definitions, and default configuration for use in scoring multimodal content.

### Dimensions

|Dimension                    |Description                                                                        |
|-----------------------------|-----------------------------------------------------------------------------------|
|Normative Integrity          |Evaluates foundational correctness (alignment with intent, rules and guidelines).  |
|Factual and Ethical Integrity|Evaluates accuracy, inclusiveness, transparency, and risk of manipulation.         |
|Communication Coherence      |Evaluates how well the content is communicated (consistency, clarity, and style).  |
|Experience and Engagement    |Evaluates the emotional, practical, and cognitive effect for end users.            |

**Note:** All dimensions evaluate the content across all applicable modalities (text, music, voiceover, video etc.) 

---

### Categories and Their Mappings

| Category Name             | Dimension                     | Description                                                                                    |
| ------------------------- | ----------------------------- | ---------------------------------------------------------------------------------------------- |
| Task Relevance            | Normative Integrity           | Measures how well the content fulfills the intended prompt, user goal, or business purpose.    |
| Technical Integrity       | Normative Integrity           | Ensures structural correctness and functional completeness across media formats.               |
| Conventions Adherence     | Normative Integrity           | Evaluates adherence to general modality-specific norms, rules, and conventions.                |
| Guidelines Adherence      | Normative Integrity           | Evaluates adherence to creator’s guidelines applicable in the context of this content.         |
| Factual Accuracy          | Factual and Ethical Integrity | Verifies that the content is accurate, truthful, and consistent with reliable sources.         |
| Disinformation Risk       | Factual and Ethical Integrity | Evaluates whether the content could be misleading, manipulated, or misinterpreted.             |                              |
| Cultural Inclusiveness    | Factual and Ethical Integrity | Detects stereotypes or exclusionary content and evaluates respect for cultural expectations.   |
| Content Attribution       | Factual and Ethical Integrity | Verifies disclosure of AI-generated content and proper credit for sources and contributors.    |
| Naturalness of Expression | Communication Coherence       | Evaluates the fluency, flow, and idiomatic quality of expression in the modalities.            |
| Stylistic Suitability     | Communication Coherence       | Assesses if tone, formality, and narrative voice match the purpose, intent, and medium.        |
| Intra-Modal Consistency   | Communication Coherence       | Evaluates consistency of elements within a mode (e.g., text coherence, visual continuity).     |
| Cross-Modal Consistency   | Communication Coherence       | Measures how multiple modalities align and interact (e.g. timing and pacing across modes).     |
| Audience Appropriateness  | Experience and Engagement     | Evaluates against the needs, expectations, and sensitivities of the intended target audience.  |
| Usability and Usefulness  | Experience and Engagement     | Assesses whether the content is functional, easy to use, and serves a practical user need.     |
| Emotional Resonance       | Experience and Engagement     | Evaluates the emotional impact and alignment with the intended emotional tone.                 |
| Engagement Potential      | Experience and Engagement     | Evaluates how likely the content is to capture the user’s attention and stimulate interest.    |

---

### Scoring Definition

Each category is scored with floating numbers on a **1–5 scale**, with the following guidance:

|Score|Meaning                                                       |
|-----|--------------------------------------------------------------|
|5    |Perfect fit: Fully aligned, relevant, natural, and impactful. |
|4    |Mostly appropriate: Minor refinements needed.                 |
|3    |Adequate: Some inconsistencies or issues affecting perception.|
|2    |Major issues: Significantly detracts from intent or usability.|
|1    |Critical failure: Fundamentally flawed or inappropriate.      |

Scores may include decimal points for finer granularity (e.g., 3.7).

---

### Modular Configuration Notes

- All categories are optional by design. Users may define subsets or add custom ones.
- Categories are grouped under dimensions for aggregation.
- Each **category** and **dimension** may be assigned a custom **weight**.
- Systems may roll up dimension and overall scores by weighted averaging.

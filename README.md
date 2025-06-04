# MMQEval

## Model Definition and Configuration Profile**

This document outlines the MMQ Eval quality framework, its modular structure, scoring definitions, and default configuration for use in scoring multimodal content.

---

## Dimensions

|Dimension|Description|
|---|---|
|Normative Integrity|Evaluates alignment with general modality-specific norms and creator-specific guidelines.|
|Factual and Ethical Integrity|Assesses truthfulness, transparency, inclusiveness, and risk of manipulation.|
|Communication Coherence|Measures consistency, clarity, and expressive precision within and across modalities.|
|Experience and Engagement|Evaluates the emotional, practical, and cognitive experience for end users.|

---

## Categories and Their Mappings

|Category ID|Category Name|Dimension|Weight|Description|
|---|---|---|---|---|
|taskRelevance|Task Relevance|Normative Integrity|1.0|Measures how well the content fulfills the intended prompt, user goal, or business purpose.|
|technicalIntegrity|Technical Integrity|Normative Integrity|1.0|Ensures structural correctness and functional completeness across media formats.|
|conventionsAdherence|Conventions Adherence|Normative Integrity|1.0|Evaluates adherence to general modality-specific norms, such as punctuation or date formats.|
|guidelinesAdherence|Guidelines Adherence|Normative Integrity|1.0|Evaluates adherence to creator’s guidelines applicable in the context of this content.|
|culturalSensitivity|Bias and Cultural Sensitivity|Factual and Ethical Integrity|1.0|Detects stereotypes or exclusionary content and evaluates respect for cultural expectations.|
|contentAttribution|Content Attribution|Factual and Ethical Integrity|1.0|Verifies disclosure of AI-generated content and proper credit for sources and contributors.|
|factualCorrectness|Accuracy and Factual Correctness|Factual and Ethical Integrity|1.0|Verifies that the content is accurate, truthful, and consistent with reliable sources.|
|disinformationRisk|Disinformation Risk|Factual and Ethical Integrity|1.0|Assesses risk of misleading, manipulative, or deceptive content.|
|naturalness|Naturalness of Expression|Communication Coherence|1.0|Evaluates smooth, idiomatic, and natural delivery in any mode (text, audio, visual, etc.).|
|stylisticFit|Stylistic Fit|Communication Coherence|1.0|Assesses if tone, formality, and narrative voice match the purpose and medium.|
|intraModal|Intra-Modal Consistency|Communication Coherence|1.0|Evaluates consistency within a single mode (e.g., text coherence, visual continuity).|
|crossModal|Cross-Modal Consistency|Communication Coherence|1.0|Measures how harmoniously multiple modalities (e.g., audio, text, visuals) align and interact.|
|audienceFit|Audience Appropriateness|Experience and Engagement|1.0|Assesses cultural fit, cognitive load, and accessibility for the intended audience.|
|engagementPotential|Engagement Potential|Experience and Engagement|1.0|Gauges the ability to sustain attention and stimulate user interest.|
|emotionalResonance|Emotional Resonance|Experience and Engagement|1.0|Evaluates the emotional impact and alignment with the intended emotional tone.|
|usability|Usability and Usefulness|Experience and Engagement|1.0|Assesses whether the content is functional, easy to use, and serves a practical user need.|

---

## Scoring Definition

Each category is scored with floating numbers on a **1–5 scale**, with the following guidance:

|Score|Meaning|
|---|---|
|5|Perfect fit: Fully aligned, relevant, natural, and impactful.|
|4|Mostly appropriate: Minor refinements needed.|
|3|Adequate: Some inconsistencies or issues affecting perception.|
|2|Major issues: Significantly detracts from intent or usability.|
|1|Critical failure: Fundamentally flawed or inappropriate.|

Scores may include decimal points for finer granularity (e.g., 3.7).

---

## Modular Configuration Notes

- All categories are optional by design. Users may define subsets or add custom ones.
- Categories are grouped under dimensions for aggregation.
- Each **category** and **dimension** may be assigned a custom **weight**.
- Systems may roll up dimension and overall scores by weighted averaging.

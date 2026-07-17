# AgriGround Task Reference

AgriGround contains 14 instruction-tuning tasks spanning captioning, segmentation, localization, counting, conversation, and agricultural question answering. Counts below follow the current manuscript statistics and include both train and test samples.

## Task Distribution

| Task | Output supervision | Train | Test | Total | Share |
|---|---|---:|---:|---:|---:|
| Semantic segmentation | Text + masks | 1,651,229 | 422,187 | 2,073,416 | 18.15% |
| Phrase grounding | Bounding boxes | 1,638,327 | 418,948 | 2,057,275 | 18.01% |
| Referring expression segmentation | Text + masks | 1,638,327 | 418,948 | 2,057,275 | 18.01% |
| Part segmentation | Text + masks | 820,240 | 209,124 | 1,029,364 | 9.01% |
| Region-level conversation | Region + multi-turn text | 749,141 | 191,757 | 940,898 | 8.24% |
| Region-level captioning | Region + text | 722,833 | 185,023 | 907,856 | 7.95% |
| Classification QA | Text | 639,962 | 163,786 | 803,748 | 7.04% |
| Image-level captioning | Text | 400,872 | 102,587 | 503,459 | 4.41% |
| Grounded caption generation | Interleaved text + masks | 379,023 | 97,007 | 476,030 | 4.17% |
| Multi-turn grounded conversation | Multi-turn text + masks | 379,023 | 97,007 | 476,030 | 4.17% |
| Grounded counting | Count | 21,865 | 5,596 | 27,461 | 0.24% |
| Grounded detection | Count + bounding boxes | 21,637 | 5,535 | 27,172 | 0.24% |
| Reasoning detection | Count + bounding boxes | 21,637 | 5,535 | 27,172 | 0.24% |
| Negative absence QA | Text | 11,204 | 2,788 | 13,992 | 0.12% |
| **Total** |  | **9,095,320** | **2,325,828** | **11,421,148** | **100%** |

## Task Definitions

### Captioning

**Image-level captioning** generates a holistic agricultural description without requiring spatial output.

**Region-level captioning** receives a specified image region and describes the localized agricultural content.

**Grounded caption generation** produces a detailed caption with grounded phrases interleaved with `[SEG]` tokens. Every grounded phrase is paired with a corresponding mask.

### Segmentation

**Referring expression segmentation** segments the object or region described by a natural-language expression.

**Semantic segmentation** segments one or more instances of a requested semantic category.

**Part segmentation** targets a specific plant or object component, such as a stem, branch, leaf, flower structure, or lesion.

### Detection and Localization

**Phrase grounding** maps a phrase to a normalized bounding box.

**Grounded counting** reports the number of requested agricultural objects in an image.

**Grounded detection** reports the count and normalized bounding boxes for all requested instances.

**Reasoning detection** uses an agricultural-context prompt to infer and localize the target instances.

### Conversation and QA

**Region-level conversation** supports follow-up questions about a selected image region.

**Multi-turn grounded conversation** combines image-level discussion with later phrase localization or segmentation.

**Classification QA** answers questions about species, diseases, pests, weeds, conditions, and other agricultural classes.

**Negative absence QA** teaches the model to state when a requested entity is not visible instead of producing an unsupported mask.

## Annotation Representation

The public schema will be documented with the annotation release. Records are expected to include an image reference, task identifier, user instruction, target response, and task-dependent spatial supervision such as masks, regions, or normalized bounding boxes.

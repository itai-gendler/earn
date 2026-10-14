---
appliesTo:
- type: entity
  id: submission
  facts:
  - Quote
- type: capability
  id: apply-to-project
references:
- kind: code
  role: implementation
  target: src/features/listings/utils/submissionFormSchema.ts
---

# A quote falls within the range the project allows

Projects with range compensation take quotes between the lowest and highest amount set; projects with variable compensation require a quote.

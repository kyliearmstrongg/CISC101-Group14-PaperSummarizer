# Module 03: Guardrails

## Change Log
- Added `evidence_mode` with strict evidence enforcement.
- Introduced standardized warnings for missing, empty, and short sections.
- Strengthened hallucination detection logic.

## Logic & Steps

### 1. Evidence Mode Variable
Introduce:
evidence_mode = "standard" OR "strict"

### 2. Strict Evidence Mode Behavior
IF evidence_mode = "strict":
- The summarizer must:
  - Only include information explicitly stated in the provided section text.
  - Avoid inference, speculation, or external additions.
- If the section lacks sufficient detail, output:
  "The source text does not provide enough detail to summarize this section in strict evidence mode."

### 3. Section Validation Rules
 
IF section text is missing or empty:
- Output:
  "Section skipped: no usable text was provided."
- Do NOT attempt to generate a summary.

IF section word count < 50:
- Allow summary generation but append warning:
  "Section very short: summary may be incomplete."

### 4. Hallucination Prevention
- Confirm each summary uses only content from the original section.
- Block and remove any:
  - Invented facts
  - Speculative reasoning
  - External references or citations

### 5. Accuracy Enforcement
- Cross-check each summary sentence against the source text.
- Remove or modify any unsupported claims.

## Output
- Validated summaries only.
- Standardized warning messages added where applicable.
- Any summaries violating strict mode rules are replaced with the appropriate explanation message. 

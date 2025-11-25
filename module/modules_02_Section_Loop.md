# Module 02: Section Loop

## Change Log
- Added `summary_level` variable to support "short" and "detailed" summary modes.
- Introduced conditional logic to control section summary length and format.
- Preserved original section ordering and 150-word maximum rule.

## Logic & Steps

1. **Original Order Enforcement**
   - Process each section strictly according to the original paper order.

2. **Summary Level Variable**
   - Introduce variable:
     summary_level = "short" OR "detailed"

3. **Conditional Summary Generation**

   IF summary_level = "short":
   - Generate a compact 1–2 sentence summary for the section.
   - Focus only on:
     - Core idea
     - Key outcome or conclusion
   - Ensure summary is ≤150 words and technically accurate.

   IF summary_level = "detailed":
   - Generate:
     - One short paragraph summary of the section
     - A bullet list of 3–5 key points highlighting:
       - Methods
       - Key findings
       - Important concepts or conclusions
   - Combined output (paragraph + bullets) must remain ≤150 words.

4. **Technical Consistency**
   - Preserve all technical abbreviations and key terms as presented in the source.
   - Avoid oversimplification or removal of essential academic terminology.

5. **Guardrail Invocation**
   - After generating each summary, immediately invoke Module 03 (Guardrails)
   - Ensure the summary complies with factual and safety requirements before final storage.

## Output
- For each section:
  - Markdown-formatted summary under the section heading
  - Bullet points (if detailed mode is enabled)
  - Any warnings passed from Module 03
- All summaries are returned in original section order.

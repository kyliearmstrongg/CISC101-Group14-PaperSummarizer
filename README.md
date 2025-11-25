# CISC 101 – Research Paper Summarizer

This repository contains the Research Paper Summarizer project for Week 10 of CISC 101. It implements a modular AI prompt system that summarizes academic research papers according to the PS2 specification and tutorial requirements.

The system follows a Travel Planner-style architecture where each module performs a specific role in the overall summarization process.

---

## Repository Structure

CISC101-Group#-PaperSummarizer  
│  
├── system_prompt.md  
├── README.md  
├── modules/  
│   ├── 01_intake_setup.md  
│   ├── 02_section_loop.md  
│   ├── 03_guardrails.md  
│   ├── 04_rendering_refinement.md  
│   ├── 05_key_contributions.md  
│   ├── 06_equation_explainer.md  

---

## File and Module Descriptions

### system_prompt.md  
Contains the main System Prompt used by the AI summarizer. It defines:
- Required user inputs (paper sections and summary settings)
- Output structure and formatting rules
- Summary constraints (word limits, ordering, tone)
- Safety rules (no hallucinations, strict evidence usage)
- Integration of all module behaviors

---

### modules/01_intake_setup.md  
Handles the initial setup and validation:
- Confirms paper structure and user settings  
- Detects missing or empty sections  
- Prepares content for summarization  

---

### modules/02_section_loop.md  
Controls the main summarization logic:
- Loops through each paper section in order  
- Applies summary modes ("short" or "detailed")  
- Enforces the 150-word per section limit  
- Maintains technical tone and consistent terminology  

---

### modules/03_guardrails.md  
Enforces safety and accuracy:
- Prevents hallucinations  
- Applies strict evidence mode  
- Adds standardized warnings for missing or short sections  
- Ensures all summaries use only source text  

---

### modules/04_rendering_refinement.md  
Responsible for final output assembly:
- Compiles section summaries into structured format  
- Produces the overall combined summary (100–300 words)  
- Removes redundancy  
- Applies consistent formatting  

---

### modules/05_key_contributions.md  
Extracts core ideas from the paper:
- Identifies main findings, methods, and contributions  
- Outputs them as concise bullet points  

---

### modules/06_equation_explainer.md  
Explains equations in accessible language:
- Identifies important equations  
- Describes their purpose in plain terms  
- Avoids adding outside interpretation  

---

## Project Purpose

This project demonstrates:
- Modular prompt design  
- Integration of specification requirements  
- Hallucination mitigation strategies  
- Structured AI workflow design  
- GitHub branching and pull request processes  

It mirrors the Travel Planner architecture and applies it to the context of academic paper summarization.

---

## How to Use

To use the summarizer:
1. Provide an academic paper divided into sections.
2. Specify summary level and summary length.
3. The system generates:
   - Section-by-section summaries  
   - An overall combined summary  
   - Key contributions  
   - Equation explanations  
   - Warnings for incomplete or missing content

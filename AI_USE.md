# AI Usage Disclosure (`AI_USE.md`)

This document outlines the scope and nature of artificial intelligence (AI) tools utilized during the development, debugging, and execution of this cloud computing project. In accordance with academic guidelines, AI was employed strictly as a technical reference, syntax assistant, and debugging co-pilot. All architectural decisions, testing, and final code validation were performed directly by the student.

---

### 1. Summary of AI Assistance

AI tools (such as large language models acting as coding assistants) were consulted for the following specific tasks:

* **Error Troubleshooting & Traceback Analysis:** Diagnosing runtime exceptions, such as missing library dependencies (e.g., Hugging Face `accelerate`), Mac ARM64 multiprocessing warnings, and dataset mapping column errors (`ValueError: Column name ['text'] not in the dataset`).
* **Data Cleaning & Regex Logic:** Refining the cleaning script (`clean.py`) logic to robustly parse teacher model outputs (handling markdown code-block wrappers like ```json ... ``` and unexpected conversational text from `phi3.5`).
* **Boilerplate & Configuration Formatting:** Structuring local automation scripts, `Makefile` rules, and verifying YAML syntax conventions for Kubernetes deployment manifests.
* **Documentation & Reflection Structuring:** Brainstorming narrative structures and technical checklists for the final project reflection and performance review tables.

---

### 2. Human Oversight & Verification (The "Human-in-the-Loop" Process)

To ensure academic integrity and technical correctness, every piece of assistance provided by AI underwent rigorous human verification:

1. **Code Validation:** No AI-generated script or snippet was copy-pasted blindly. All code blocks were reviewed against project rubric requirements, tested locally within the virtual environment (`.venv`), and modified to match the specific architecture of the student kit.
2. **Environment Testing:** Execution steps—including parallel worker shard generation via SeaweedFS, cleaning runs, model training smoke tests (`make train SUBSET=50`), and Locust load testing—were manually executed, verified via terminal outputs, and debugged locally.
3. **Evaluation Compliance:** The final scoring outputs (`score.py`), metric validations, and git release tags (`final`) were verified independently against project specification guidelines.

---

### 3. Declaration

I confirm that I understand the code, pipeline mechanics, and infrastructure design implemented in this repository, and that AI tools were used ethically to accelerate problem-solving rather than to automate the core learning outcomes of the project.

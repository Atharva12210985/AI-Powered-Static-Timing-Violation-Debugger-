# 🚀 Microwatt Challenge Proposal: GenAI-powered Timing Violation Debugger

---

## 👨‍💻 Team
- Atharva Awate  
- Tushar Bhandari  
- Yash Pahade  

---

## 📌 Project Description
This project proposes a **Generative AI-powered debugger for Static Timing Analysis (STA) reports**.  
The tool automates the tedious and complex process of analyzing timing violations in digital integrated circuits (ICs), a critical step in the physical design and verification flow.

The debugger leverages **[OpenSTA](https://github.com/The-OpenROAD-Project/OpenSTA)**, an open-source static timing analysis engine, to generate standard timing reports from synthesized designs (e.g., the **Microwatt CPU using SKY130 libraries**).  
These reports are then parsed and analyzed using a **Large Language Model (LLM)**, running on a high-speed inference engine like **Groq**, to perform in-depth, quantitative analysis of each timing path.

The system identifies the **root cause of violations** and provides **specific, actionable recommendations** for fixes, accelerating the timing closure process.

---

## ✨ Key Features
- **AI-Powered Root Cause Analysis**  
  Fine-tuned prompts + LLM to pinpoint exact causes of timing violations (e.g., excessive cell delay, high fanout, clock skew).

- **Actionable Fixes**  
  Precise, tool-agnostic suggestions such as replacing cells, resizing gates, or adjusting the clock tree.

- **Integration with OpenSTA**  
  Automates STA runs with support for:
  - Verilog netlists  
  - Liberty (`.lib`) files (SKY130)  
  - SDC constraints  
  Generates `sta_report.txt` files for analysis.

- **Comprehensive Reporting**  
  Outputs a detailed analysis in:
  - Interactive **JSON** format  
  - Professionally formatted **PDF** reports  

- **User-Friendly Interface**  
  Built with **Streamlit** for a clean, intuitive, web-based dashboard to upload reports, configure options, and view results.

---

## 🎯 Relevance to the Microwatt Challenge
This project directly addresses a major pain point in the physical design flow, **timing closure**, which is critical for CPU/microprocessor design such as the **Microwatt core**.

By combining **OpenSTA + AI-driven debugging**, the tool can:
- Generate timing reports for **Microwatt synthesized with SKY130**  
- Automatically analyze STA violations  
- Suggest fixes to accelerate timing closure  

This demonstrates the **value of open-source EDA + GenAI**, making chip design **more accessible, efficient, and intelligent**.

---

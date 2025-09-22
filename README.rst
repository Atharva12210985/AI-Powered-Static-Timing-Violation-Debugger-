Microwatt Challenge Proposal: GenAI-powered Timing Violation Debugger
=====================================================================

The **GenAI-powered Timing Violation Debugger** is a project designed for the 
**Microwatt Challenge Hackathon**. It addresses one of the most 
time-consuming steps in the physical design flow: debugging and closing 
timing violations in digital integrated circuits (ICs).  

The project integrates **OpenSTA** (an open-source static timing analysis tool) 
with **Generative AI (LLM-based analysis on Groq inference engine)** to 
automatically analyze STA reports, identify the root causes of violations, 
and suggest actionable fixes.  

This README provides information about the project’s purpose, features, 
and usage. Additional documentation may be added later.  

-------------------------------------------------------------------------------

Table of Contents
=================

- Module Overview
- Designing
- Building
- Submitting
- Contributing
- License

-------------------------------------------------------------------------------

Module Overview
===============

The **GenAI-powered Timing Violation Debugger** combines open-source 
EDA with generative AI to simplify **timing closure** for CPU designs 
such as the **Microwatt RISC-V core** on SKY130.  

Key components include:  

- **OpenSTA** for generating STA reports from synthesized netlists.  
- **Large Language Model (LLM)** for analyzing reports and pinpointing 
  root causes of timing violations.  
- **Streamlit Web Interface** for interactive debugging and visualization.  

Supported inputs:  
- Verilog netlists  
- Liberty (.lib) files (SKY130 PDK)  
- SDC timing constraints  

Generated outputs:  
- ``sta_report.txt`` (raw OpenSTA output)  
- JSON analysis (interactive format)  
- PDF analysis report (for documentation)  

-------------------------------------------------------------------------------

Designing
=========

The primary objective is to reduce **manual effort in STA debugging**.  

The workflow is:  

1. **Synthesize Microwatt design** with SKY130 libraries.  
2. **Run OpenSTA** with Verilog, Liberty, and SDC inputs to produce timing reports.  
3. **Upload report** into the Streamlit-based interface.  
4. **AI-powered analysis**:  
   - Identifies issues such as large combinational delay, excessive fanout, or clock skew.  
   - Suggests actionable fixes (cell replacement, gate sizing, clock adjustments).  
5. **Export results** in JSON or PDF for review.  

This design ensures that both experts and beginners can understand 
and resolve timing issues more efficiently.  

-------------------------------------------------------------------------------

Building
========

This project is a **Python-based web application**.  

.. code-block:: bash

   # Clone the repository
   git clone https://github.com/your-username/your-repo-name.git
   cd your-repo-name

   # Install dependencies
   pip install -r requirements.txt

   # Run the Streamlit application
   streamlit run app/ui.py

Dependencies:  
- Python 3.8+  
- Streamlit  
- OpenSTA  
- Report generation libraries (for JSON, PDF export)  

-------------------------------------------------------------------------------

Submitting
==========

(To be completed)

-------------------------------------------------------------------------------

Contributing
============

Bug fixes and feature improvements are welcome.  
Potential contributions may include:  

- Support for additional STA tools.  
- Enhancements to visualization of timing paths.  
- Integration with OpenLane for full P&R + STA flow.  

-------------------------------------------------------------------------------

License
=======

This project is licensed under the **MIT License**.  
See the ``LICENSE`` file for details.  

-------------------------------------------------------------------------------

Microwatt Challenge Proposal: GenAI-powered Timing Violation Debugger
=====================================================================

Overview
--------
The **GenAI-powered Timing Violation Debugger** is developed for the  
**Microwatt Challenge Hackathon**.  

It addresses one of the most time-consuming steps in the digital IC physical design flow:  
debugging and closing static timing violations.  

By integrating **OpenSTA** (an open-source static timing analysis tool) with **Generative AI**  
(LLM-based analysis accelerated on the Groq inference engine), the tool automates the  
analysis of STA reports, identifies root causes of violations, and suggests actionable fixes.  

This README provides hackathon-focused documentation of the project’s purpose, features,  
and submission details.

Table of Contents
-----------------
- Module Overview
- Designing
- Building
- Submitting
- Contributing
- License

Module Overview
---------------
The project demonstrates the combination of **open-source EDA tools** and **Generative AI**  
to simplify timing closure for RISC-V CPUs such as the Microwatt core on **SKY130 PDK**.  

Key Components:
^^^^^^^^^^^^^^^
- **OpenSTA** for generating STA reports from synthesized netlists.  
- **Large Language Model (LLM)** for analyzing timing reports and pinpointing root causes.  
- **Streamlit Web Interface** for interactive debugging and visualization.  

Supported Inputs:
^^^^^^^^^^^^^^^^^
- Verilog netlists  
- Liberty (.lib) files from SKY130 PDK  
- SDC timing constraints  

Generated Outputs:
^^^^^^^^^^^^^^^^^^
- ``sta_report.txt`` (raw OpenSTA output)  
- JSON analysis (interactive format)  
- PDF analysis report (for documentation/sharing)  

Designing
---------
The primary objective of the tool is to **reduce manual effort** in debugging STA violations.  

Workflow:
^^^^^^^^^
1. **Synthesize** the Microwatt design using SKY130 libraries.  
2. **Run OpenSTA** with Verilog netlist, Liberty, and SDC constraints → generate reports.  
3. **Upload STA report** into the Streamlit-based interface.  
4. **AI-powered analysis**:  
   - Identifies issues such as large combinational delay, excessive fanout, or clock skew.  
   - Suggests actionable fixes such as cell replacement, gate resizing, or clock adjustments.  
5. **Export results** in JSON or PDF formats for review and documentation.  

This design ensures that both experienced engineers and beginners can understand  
and resolve timing issues efficiently.

Building
--------
(To be completed)

Submitting
----------
(To be completed)

Contributing
------------
Contributions are welcome for extending the functionality and robustness of the tool.  
Future enhancements may include:  

- Support for multiple STA engines beyond OpenSTA.  
- Visualization improvements for timing paths and violation hotspots.  
- Integration with **OpenLane** for a complete open-source P&R + STA flow.  

License
-------
This project is licensed under the **MIT License**.  
See the ``LICENSE`` file for details.

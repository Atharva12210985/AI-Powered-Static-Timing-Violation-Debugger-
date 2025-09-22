Microwatt Challenge Proposal: GenAI-powered Timing Violation Debugger
=====================================================================

Overview
--------
The **GenAI-powered Timing Violation Debugger** is a project designed for the  
**Microwatt Challenge Hackathon**, focusing on improving the efficiency of the  
physical design and verification flow for digital integrated circuits (ICs).  

One of the most challenging and time-consuming tasks in the physical design cycle  
is **Static Timing Analysis (STA)** and the subsequent **debugging of timing violations**.  
Traditional STA tools like OpenSTA generate detailed reports of timing paths,  
but analyzing these reports, identifying the true root causes of violations,  
and deciding on corrective actions often require significant manual expertise  
and effort. This can lead to **delays in timing closure**, especially in complex  
designs such as CPU cores.  

The proposed tool integrates **OpenSTA** with **Generative AI** to automate this  
debugging process. Using an LLM running on a high-speed inference engine  
(such as **Groq**), the system parses STA reports and provides a **layered analysis**:  

- **Quantitative timing analysis** of each path.  
- **Identification of root causes** such as excessive cell delay, long combinational logic chains,  
  poor gate sizing, high fanout, or clock skew.  
- **Actionable recommendations** that are tool-agnostic and can be directly applied  
  during design iterations.  

In addition, the project provides a **user-friendly web interface** built with  
**Streamlit**, where designers can upload STA reports, configure analysis options,  
and visualize results interactively. The tool also produces structured outputs  
in **JSON** (for machine-readable analysis pipelines) and **PDF** (for documentation/sharing).  

This project demonstrates how combining **open-source EDA tools** (OpenSTA, SKY130 PDK)  
with **cutting-edge Generative AI** can make timing closure more **accessible, efficient,  
and intelligent**. For the Microwatt core, this translates into a faster path  
from synthesis to a timing-clean CPU implementation.

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
The **GenAI-powered Timing Violation Debugger** is composed of four main modules,  
each addressing a specific part of the flow:  

1. **OpenSTA Integration**  
   - Accepts Verilog netlists, Liberty (.lib) files from SKY130 PDK, and SDC constraints.  
   - Performs static timing analysis on the synthesized Microwatt design.  
   - Generates standard reports (``sta_report.txt``) which serve as the raw input to the AI system.  

2. **AI-Powered Analysis (LLM on Groq Engine)**  
   - Parses STA reports to extract critical timing paths and violation details.  
   - Applies reasoning using a fine-tuned LLM to:  
     * Detect the exact cause of each violation.  
     * Differentiate between issues such as excessive combinational delay, unbalanced clock skew,  
       or high fanout.  
   - Outputs structured insights in JSON format for downstream use.  

3. **Recommendation Engine**  
   - Converts AI insights into **actionable design fixes**, such as:  
     * Replacing slow standard cells with faster equivalents.  
     * Resizing gates to reduce propagation delay.  
     * Buffer insertion or restructuring high-fanout nets.  
     * Clock tree adjustments to reduce skew.  
   - Provides suggestions in a **tool-agnostic manner**, so they can be applied with  
     any P&R flow (including OpenLane).  

4. **Streamlit User Interface & Reporting**  
   - Web-based interactive dashboard.  
   - Allows users to upload reports, view AI analysis, and explore critical paths visually.  
   - Exports results in:  
     * **JSON** → for automation pipelines.  
     * **PDF** → for documentation and team review.  

By combining these modules, the tool ensures:  
- Faster debugging of timing violations.  
- Reduced manual effort for engineers.  
- Improved accessibility for students and beginners learning physical design flows.  

This modular design highlights the hackathon’s goal: making open-source chip design flows  
more practical and efficient through AI-driven innovation.

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

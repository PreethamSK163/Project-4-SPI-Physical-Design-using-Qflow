# Static Timing Analysis
> Pre-Route STA using Vesta — Critical Path Analysis, Slack Calculation & Timing Reports

![Tool](https://img.shields.io/badge/Tool-Vesta-blue)
![Tool](https://img.shields.io/badge/Tool-Qflow-blue)
![PDK](https://img.shields.io/badge/PDK-OSU018-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

<h2>🔍 Overview</h2>

- Performed pre-route static timing analysis using Vesta on the placed SPI Controller netlist — analyzing 321 timing paths against the OSU018 standard cell library (6,142 lines processed) and identifying the critical path with a maximum delay of 4,305.4 ps.
- Generated the top 20 maximum delay paths report — confirming clock skew of 348.187 ps and setup time of 94.1149 ps, providing timing closure guidance before proceeding to detailed routing with Qrouter.

<h2>⚙️ Tasks Covered</h2>

| Task | Description |
|:---|:---|
| Library Parsing | OSU018 stdcells.lib — 6,142 lines, 3,130 netlist lines processed |
| Path Enumeration | 321 timing paths analyzed — setup and hold checks |
| Critical Path Analysis | Top 20 maximum delay paths identified and reported |
| Slack Calculation | Clock skew and setup time calculated for timing closure |

<h2>📝 Stage Details</h2>

**Task 1 — STA Execution & Library Parsing** &nbsp;|&nbsp; `Vesta` `osu018_stdcells.lib` `321 Paths`

Vesta static timing analysis tool (for Qflow 1.3.17, © 2013–2018 Tim Edwards, Open Circuit Design) executed pre-route STA using the command:
```
vesta --long spi_top.rtlnopwr.v /usr/share/qflow/tech/osu018/osu018_stdcells.lib
```
Parsed the OSU018 standard cell library — processed 6,142 lines — then read the Verilog netlist with 3,130 lines. Analyzed all 321 timing paths in the design for setup and hold time compliance.

**Task 2 — Critical Path Analysis & Timing Report** &nbsp;|&nbsp; `Critical Path` `4305.4 ps` `Clock Skew` `Setup Time`

Identified the critical path as DFFSR_42/CLK → DFFSR_180/D with a total delay of 4,305.4 ps — propagating through 20 logic stages including NAND3X1, NOR3X1, NAND2X1, OAI21X1, BUFX4, and INVX8 cells. Generated the top 20 maximum delay paths report for timing analysis and optimization guidance.

<h2>📊 STA Results</h2>

| Metric | Value |
|:---|:---|
| Library | osu018_stdcells.lib — 6,142 lines |
| Netlist Lines Processed | 3,130 |
| Total Paths Analyzed | 321 |
| Critical Path | DFFSR_42/CLK → DFFSR_180/D |
| Maximum Path Delay | 4,305.4 ps |
| Clock Skew at Destination | 348.187 ps |
| Setup Time at Destination | 94.1149 ps |
| STA Type | Pre-Route (before Qrouter) |
| Tool | Vesta (Qflow 1.3.17) |

<h2>🖼️ Implementation Results</h2>

### Qflow Manager — STA Okay, Routing In Progress
![8_Image_after_STA_and_routing_in_progress](8_Image_after_STA_and_routing_in_progress.png)

### STA Log File — Critical Path & Timing Report
![9_Image_of_the_STA_log_file](9_Image_of_the_STA_log_file.png)

<h2>🔗 Navigation</h2>

[Back to Repository Overview](../README.md) &nbsp;|&nbsp; [Previous : 03 : Placement](../03%20:%20Placement/README.md) &nbsp;|&nbsp; [Next : 05 : Routing](../05%20:%20Routing/README.md)

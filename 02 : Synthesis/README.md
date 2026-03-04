# Synthesis
> RTL to Gate-Level Netlist using Yosys + ABC with OSU018 Standard Cell Library

![Tool](https://img.shields.io/badge/Tool-Yosys-blue)
![Tool](https://img.shields.io/badge/Tool-ABC-blue)
![Tool](https://img.shields.io/badge/Tool-blifFanout-blue)
![PDK](https://img.shields.io/badge/PDK-OSU018-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

<h2>🔍 Overview</h2>

- Executed RTL synthesis of the SPI Controller using Yosys with ABC for logic optimization and technology mapping to the OSU018 standard cell library — generating a gate-level netlist of 3,106 standard cells with RTL Verilog, SPICE, and BLIF output files for downstream physical design.
- blifFanout performed fanout analysis and buffer insertion — identifying the top internal fanout of 16 (load 524.125) on `wb_clk_i` and flagging 880 gates exceeding specified minimum load, with synthesis completing cleanly on Wednesday 02 July 2025 at 11:30:39 PM IST.

<h2>⚙️ Tasks Covered</h2>

| Task | Description |
|:---|:---|
| RTL Synthesis | Yosys parses `spi_top.v`, elaborates hierarchy, maps to OSU018 cells |
| Logic Optimization | ABC combinational optimization and technology mapping |
| Fanout Balancing | blifFanout — buffer insertion, load balancing, fanout reduction |
| Netlist Generation | RTL Verilog, SPICE netlist, BLIF files generated in synthesis directory |

<h2>📝 Stage Details</h2>

**Task 1 — RTL Synthesis & Technology Mapping** &nbsp;|&nbsp; `Yosys` `ABC` `osu018` `Gate-Level Netlist`

Initiated synthesis from the Qflow Manager GUI — selected osu018 technology library and `spi_top.v` as the source. Yosys parsed and elaborated the SPI RTL hierarchy, applied behavioral processing (proc pass), logic optimization (opt pass), and technology mapping via ABC using the OSU018 Liberty file. Synthesis completed generating the gate-level netlist with 3,106 standard cells mapped across drive strength groups — 253 (strength ""), 2,251 (strength "1"), 285 (strength "2"), 293 (strength "4"), and 24 (strength "8").

**Task 2 — Fanout Balancing & Output Generation** &nbsp;|&nbsp; `blifFanout` `Buffer Insertion` `SPICE` `BLIF`

blifFanout analyzed the synthesized netlist — identified top internal fanout of 16 on `wb_clk_i bF$buf1` driven by CLKBUF1 with strength 231.615, and top input node fanout of 15 on `wb_clk_i`. Flagged 880 gates exceeding minimum load with overload ratios up to 6.37x on NAND3X1. Generated the following output files in `/home/preethamsk/synthesis/`:

| Output File | Description |
|:---|:---|
| `spi_top.rtl.v` | Gate-level RTL Verilog netlist |
| `spi_top.rtlnopwr.v` | RTL Verilog without power connections |
| `spi_top.rtlbb.v` | Black-box RTL Verilog |
| `spi_top.spc` | SPICE netlist for simulation |

<h2>📊 Synthesis Results</h2>

| Metric | Value |
|:---|:---|
| Total Standard Cells | 3,106 |
| Drive Strength "" | 253 gates |
| Drive Strength "1" | 2,251 gates |
| Drive Strength "2" | 285 gates |
| Drive Strength "4" | 293 gates |
| Drive Strength "8" | 24 gates |
| Gates Resized | 0 |
| Top Internal Fanout | 16 — wb_clk_i bF$buf1 |
| Top Input Fanout | 15 — wb_clk_i |
| Synthesis Script End | Wed 02 July 2025, 11:30:39 PM IST |

<h2>🖼️ Implementation Results</h2>

### Qflow Manager — After Running Synthesis
![4_Image_after_running_synthesis](4_Image_after_running_synthesis.png)

### Synthesis Log File Output
![5_Output_of_the_Synthesis](5_Output_of_the_Synthesis.png)

<h2>🔗 Navigation</h2>

[Back to Repository Overview](../README.md) &nbsp;|&nbsp; [Previous : 01 : Tool Setup & Invocation](../01%20:%20Tool%20Setup%20%26%20Invocation/README.md) &nbsp;|&nbsp; [Next : 03 : Placement](../03%20:%20Placement/README.md)

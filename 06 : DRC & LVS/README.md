# DRC & LVS
> Design Rule Checking using Magic & Layout vs Schematic using Netgen — Clean Verification

![Tool](https://img.shields.io/badge/Tool-Magic-blue)
![Tool](https://img.shields.io/badge/Tool-Netgen-blue)
![Tool](https://img.shields.io/badge/Tool-Qflow-blue)
![PDK](https://img.shields.io/badge/PDK-OSU018-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

<h2>🔍 Overview</h2>

- Performed Design Rule Checking using Magic 8.3 — processed 50,000 rectangles across all standard cells and confirmed `drc = 0` with zero violations, verifying full manufacturability compliance with OSU018 design rules.
- Followed by LVS verification using Netgen — extracted the layout netlist from the GDSII and compared against the schematic netlist, confirming "Circuits match uniquely" with full pin and device equivalence between `spi_top` layout and schematic.

<h2>⚙️ Tasks Covered</h2>

| Task | Description |
|:---|:---|
| DRC | Magic 8.3 — 50,000 rects processed, drc = 0 |
| LVS Extraction | Netgen extracts layout netlist from all standard cells |
| LVS Comparison | Layout vs schematic netlist — circuits match uniquely |

<h2>📝 Stage Details</h2>

**Task 1 — Design Rule Checking** &nbsp;|&nbsp; `Magic 8.3` `drc=0` `OSU018` `50000 Rects`

DRC executed using Magic 8.3 revision 105 via the script `run_drc_spi_top.tcl`. Magic loaded the OSU018 LEF file (2,941 lines processed) and performed DRC on the complete layout — processing 50,000 rectangles across all standard cell instances including BUFX2, FILL, AND2X2, NOR2X1, NAND2X1, AOI21X1, INVX2, DFFSR, INVX1, OAI21X1, CLKBUF1, XNOR2X1, NOR3X1, INVX4, NAND3X1, OR2X2, OAI22X1, BUFX4, XOR2X1, INVX8, MUX2X1, and AOI22X1. Result: **drc = 0** — zero violations. DRC checking script ended Thursday 03 July 2025 at 12:06:03 AM IST.

**Task 2 — Layout Versus Schematic Verification** &nbsp;|&nbsp; `Netgen` `Cell Extraction` `Pin Equivalence` `LVS Clean`

LVS executed using Netgen — extracted layout netlists for all standard cell instances including OR2X2, OAI22X1, BUFX4, XOR2X1, INVX8, MUX2X1, AOI22X1, and spi_top. Compared the extracted layout netlist against the schematic netlist (gate-level). Result:
- **Cell pin lists are equivalent**
- **Device classes spi_top and spi_top are equivalent**
- **Circuits match uniquely** — LVS clean ✅

<h2>📊 Verification Results</h2>

| Metric | Value |
|:---|:---|
| DRC Tool | Magic 8.3 revision 105 |
| DRC Script | run_drc_spi_top.tcl |
| LEF Lines Processed | 2,941 |
| Rectangles Processed | 50,000 |
| DRC Violations | 0 (drc = 0) |
| DRC Script End | Thu 03 July 2025, 12:06:03 AM IST |
| LVS Tool | Netgen |
| LVS Result | Circuits match uniquely |
| Pin Equivalence | Cell pin lists are equivalent |
| LVS Status | Clean ✅ |

<h2>🖼️ Implementation Results</h2>

### Qflow Manager — DRC Completed, LVS In Progress
![12_Image_Post_DRC_Completion](12_Image_Post_DRC_Completion.png)

### DRC Log File — drc = 0
![13_Image_of_DRC_Logfile](13_Image_of_DRC_Logfile.png)

### Qflow Manager — LVS Completed
![14_Image_Post_LVS_Completion](14_Image_Post_LVS_Completion.png)

### LVS Log File — Circuits Match Uniquely
![15_Image_of_LVS_Logfile](15_Image_of_LVS_Logfile.png)

<h2>🔗 Navigation</h2>

[Back to Repository Overview](../README.md) &nbsp;|&nbsp; [Previous : 05 : Routing](../05%20:%20Routing/README.md) &nbsp;|&nbsp; [Next : 07 : GDSII Generation](../07%20:%20GDSII%20Generation/README.md)

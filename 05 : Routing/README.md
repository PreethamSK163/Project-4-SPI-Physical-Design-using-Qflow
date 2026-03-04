# Routing
> Detailed Routing using Qrouter — 22,417 Routes Completed with Zero Failures

![Tool](https://img.shields.io/badge/Tool-Qrouter-blue)
![Tool](https://img.shields.io/badge/Tool-Qflow-blue)
![PDK](https://img.shields.io/badge/PDK-OSU018-orange)
![Status](https://img.shields.io/badge/Status-Completed-brightgreen)

<h2>🔍 Overview</h2>

- Executed detailed routing using Qrouter 1.4.71 across 3 stages — completing 22,417 total routes with zero failed routes, generating the routed DEF file (`spi_top_route.def`) with 3,155 nets and 2 special nets.
- Ran post-route back-annotation using annotate.tcl — converting Qrouter output to Vesta delay format, SPEF format, and SDF format for accurate post-route static timing analysis, completing routing on Wednesday 02 July 2025 at 11:38:39 PM IST.

<h2>⚙️ Tasks Covered</h2>

| Task | Description |
|:---|:---|
| Detailed Routing | Qrouter — 3-stage routing, 22,417 routes, 0 failures |
| DEF Generation | spi_top_route.def — 3,155 nets, 2 special nets |
| RC File Generation | spi_top_route.rc — parasitic RC for back-annotation |
| Post-Route Back-Annotation | rc2dly, SPEF, SDF conversion for post-route STA |

<h2>📝 Stage Details</h2>

**Task 1 — Detailed Routing** &nbsp;|&nbsp; `Qrouter` `3 Stages` `22417 Routes` `No Failures`

Initiated routing from the Qflow Manager GUI — Qrouter 1.4.71 launched with `qrouter -noc -s spi_top.cfg`. The router executed 3 progressive routing stages — completing all nets sequentially. Final routing summary:
- Stage 3 total routes completed: **22,417**
- **No failed routes**
- DEF file written: `spi_top_route.def` — 3,155 nets and 2 special nets
- RC file written: `spi_top_route.rc` for parasitic extraction

**Task 2 — Post-Route Back-Annotation** &nbsp;|&nbsp; `rc2dly` `SPEF` `SDF` `annotate.tcl`

Ran annotate.tcl to convert Qrouter routing output to multiple delay formats for post-route STA:
- **Vesta delay format** — `rc2dly -r spi_top.rc` → `spi_top.dly`
- **SPEF format** — `rc2dly -D` → `spi_top.spef`
- **SDF format** — `rc2dly -r spi_top.rc` → `spi_top.sdf`

Found and connected FILL cell pinlist for VDD/GND power connections. Router script ended on Wednesday 02 July 2025 at 11:38:39 PM IST.

<h2>📊 Routing Results</h2>

| Metric | Value |
|:---|:---|
| Router | Qrouter 1.4.71 |
| Routing Stages | 3 |
| Total Routes Completed | 22,417 |
| Failed Routes | 0 |
| DEF File | spi_top_route.def |
| Total Nets in DEF | 3,155 nets + 2 special nets |
| RC File | spi_top_route.rc |
| Back-Annotation Formats | Vesta delay (.dly), SPEF (.spef), SDF (.sdf) |
| Routing Script End | Wed 02 July 2025, 11:38:39 PM IST |

<h2>🖼️ Implementation Results</h2>

### Routing Log File
![10_Image_of_Routing_Logfile](10_Image_of_Routing_Logfile.png)

### Post-Routing Log File
![11_Image_of_Post_Routing_Logfile](11_Image_of_Post_Routing_Logfile.png)

<h2>🔗 Navigation</h2>

[Back to Repository Overview](../README.md) &nbsp;|&nbsp; [Previous : 04 : Static Timing Analysis](../04%20:%20Static%20Timing%20Analysis/README.md) &nbsp;|&nbsp; [Next : 06 : DRC & LVS](../06%20:%20DRC%20%26%20LVS/README.md)

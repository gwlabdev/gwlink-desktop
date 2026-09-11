# Validation suite

Thirty models GWlink did not write, published by the MODFLOW 6 examples, FloPy and GMDSI, plus a set of synthetic models from the GWlink test suite that cover packages the published ones do not (CLN, HFB, MAW, DISV Voronoi grids).

Each clip is the real interface, recorded with no cuts. The model is imported from its published files, written back out by GWlink, run with the engine when the published suite ships no heads, and opened in the 3D viewer with iso-surfaces banded between the 5th and 95th percentile of the computed heads. Constant head models show the coloured model instead.

| Model | Engine | Published by | Packages |
|---|---|---|---|
| [Freyberg MODFLOW-USG](https://gwlink.gwlab.cl/videos/validation/canonical-freyberg_usg.mp4) | MODFLOW-USG | [FloPy](https://github.com/modflowpy/flopy) | `DISU BAS LPF SMS OC WEL GHB RCH SFR GNC` |
| [GMDSI Milford MFUSG](https://gwlink.gwlab.cl/videos/validation/canonical-milford.mp4) | MODFLOW-USG | [GMDSI tutorials](https://github.com/gmdsi/GMDSI_notebooks) | `BAS DISU LPF SMS OC RCH EVT WEL RIV DRN CLN` |
| [lakeex2a — MF6 SFR 22-reach chain coupled to LAK via MVR](https://gwlink.gwlab.cl/videos/validation/canonical-lakeex2a.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF STO IMS OC CHD EVT RCH SFR LAK MVR` |
| [TWRI](https://gwlink.gwlab.cl/videos/validation/canonical-twri.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD WEL DRN RCH` |
| [Advanced Tidal](https://gwlink.gwlab.cl/videos/validation/canonical-advtidal.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DISV IC NPF IMS OC CHD WEL RCH EVT GHB` |
| [BCF2 Steady-State](https://gwlink.gwlab.cl/videos/validation/canonical-bcf2ss.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD WEL RCH` |
| [MF6 Tutorial 01](https://gwlink.gwlab.cl/videos/validation/canonical-mf6_tutorial01.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF IMS OC CHD RCH` |
| [Flow and Head Boundary Replication](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_fhb.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF STO IMS OC CHD WEL OBS TS` |
| [Capture Fraction Analysis](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_capture.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD WEL RIV RCH` |
| [MODFLOW-NWT Problem 3 High Recharge](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_nwt_p03a.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD RCH` |
| [Flow Diversion Newton](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_bump_p01a.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD` |
| [MODFLOW-NWT Problem 2 Newton](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_nwt_p02a.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF STO IMS OC CHD RCH` |
| [Zaidel Drainage Problem](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_zaidel_p02a.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD` |
| [Horizontal Anisotropy Reference](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_hanir.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC CHD WEL` |
| [Whirl Flow](https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_whirl.mp4) | MODFLOW 6 | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples) | `DIS IC NPF IMS OC WEL` |
| [FloPy Structured Grid Demo](https://gwlink.gwlab.cl/videos/validation/canonical-flopy_structured_grid_demo.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF IMS OC CHD` |
| [FloPy Budget Example](https://gwlink.gwlab.cl/videos/validation/canonical-flopy_budget_example.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF STO IMS OC CHD WEL` |
| [FloPy Formhead](https://gwlink.gwlab.cl/videos/validation/canonical-flopy_formhead.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF IMS OC CHD` |
| [FloPy Time Demo](https://gwlink.gwlab.cl/videos/validation/canonical-flopy_time_demo.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF STO IMS OC` |
| [FloPy Splitter Model](https://gwlink.gwlab.cl/videos/validation/canonical-flopy_splitter_model.mp4) | MODFLOW 6 | [FloPy](https://github.com/modflowpy/flopy) | `DIS IC NPF IMS OC CHD WEL` |
| [Freyberg USG with Outputs](https://gwlink.gwlab.cl/videos/validation/canonical-freyberg_usg_output.mp4) | MODFLOW-USG | [FloPy](https://github.com/modflowpy/flopy) | `DISU BAS LPF SMS OC WEL GHB RCH` |
| [Freyberg TVM (Time-Varying Materials)](https://gwlink.gwlab.cl/videos/validation/canonical-freyberg_tvm.mp4) | MODFLOW-USG | GWlink test suite | `DISU BAS LPF SMS OC WEL GHB RCH` |
| [CLN Vertical Wells MFUSG](https://gwlink.gwlab.cl/videos/validation/canonical-cln_well_mfusg.mp4) | MODFLOW-USG | GWlink test suite | `DISU BAS LPF SMS OC CLN WEL` |
| [MODFLOW-USG CLN Conduit Well (Example 3a)](https://gwlink.gwlab.cl/videos/validation/canonical-cln_conduit_mfusg.mp4) | MODFLOW-USG | GWlink test suite | `DISU BAS LPF SMS OC CLN WEL` |
| [MAW MF6 DISV](https://gwlink.gwlab.cl/videos/validation/canonical-maw_disv.mp4) | MODFLOW 6 | GWlink test suite | `DISV IC NPF STO IMS OC MAW CHD` |
| [DISV Voronoi Grid](https://gwlink.gwlab.cl/videos/validation/canonical-disv_voronoi.mp4) | MODFLOW 6 | GWlink test suite | `DISV IC NPF IMS OC` |
| [HFB MF6 DISV](https://gwlink.gwlab.cl/videos/validation/canonical-hfb_mf6_disv.mp4) | MODFLOW 6 | GWlink test suite | `DISV IC NPF IMS OC HFB CHD` |
| [HFB MFUSG](https://gwlink.gwlab.cl/videos/validation/canonical-hfb_mfusg.mp4) | MODFLOW-USG | GWlink test suite | `DISU BAS LPF SMS OC HFB` |
| [HFB Rich MF6](https://gwlink.gwlab.cl/videos/validation/canonical-hfb_rich_mf6.mp4) | MODFLOW 6 | GWlink test suite | `DISV IC NPF IMS OC HFB CHD WEL RCH` |
| [HFB Rich MFUSG](https://gwlink.gwlab.cl/videos/validation/canonical-hfb_rich_mfusg.mp4) | MODFLOW-USG | GWlink test suite | `DISU BAS LPF SMS OC HFB CHD WEL RCH` |

## What the round trip proves

The run is expected to converge and the written files are compared with the imported ones. That catches a package silently dropped, an array reshaped or a stress period lost. It does not prove that GWlink reproduces every published result to the last decimal, and it says nothing about whether your own model is a good model. It says the software gives you back what you gave it.

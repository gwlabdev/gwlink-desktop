# GWlink

Desktop application for building, running and reading MODFLOW 6 and MODFLOW-USG groundwater models. The graphical interface, a Python script, a notebook and an embedded AI agent are four views of the same model, kept in sync by one backend.

<p align="center"><img src="media/hero.gif" width="800" alt="Freyberg MODFLOW-USG head iso-surfaces spinning in the GWlink 3D viewer"></p>

GWlink is in beta and runs on macOS (Apple Silicon) and Windows. Request access at [gwlink.gwlab.cl/request-access](https://gwlink.gwlab.cl/request-access). Current version is **0.1.86**, see [CHANGELOG.md](CHANGELOG.md).

## GWlinkViewer

[GWlinkViewer](https://gwlink.gwlab.cl/viewer) is a free, read only desktop edition built from the same code as GWlink. It imports MODFLOW 6 and MODFLOW-USG model folders and opens `.gwlink` projects to inspect the model and its results. It cannot edit the model, run MODFLOW or save changes.

GWlinkViewer is distributed through its own installers for macOS and Windows and uses a separate update channel. Its version matches the full GWlink version. It is distinct from the [MODFLOW AI web viewer](https://viewer.modflow.ai), which opens published snapshots through links in a browser.

## What it does

The workflow runs left to right through the stages DATA, GRID, TIME, PACKAGES, RUN, ZBUD, RESULTS and MATCH.

- **Data.** Shapefiles, GeoJSON, DXF, GeoTIFF and point clouds in UTM. Rivers, lakes and boundaries fetched from OpenStreetMap. Existing MODFLOW 6, MODFLOW-USG and MODFLOW-2005 models imported as they are.
- **Grid.** Voronoi and quadtree meshes refined around wells, rivers and faults, written as DISV or DISU.
- **Packages.** Properties and boundary conditions linked to spatial data by value, by zone or by expression, so a change in a shapefile flows through to the model. 18 MODFLOW 6 packages including SFR, MAW, LAK, HFB and the GWT transport pair, 16 MODFLOW-USG packages including CLN.
- **Time.** Stress periods and time series as curves bound to parameters, resolved by the backend at every period.
- **Run.** Writes the input files, runs the engine, follows convergence and solver diagnostics live.
- **Results.** Heads, drawdown, water table, budgets, zone budgets, contours, 2D cross sections and a 3D viewer with iso-surfaces.
- **Match.** History matching with PEST++ over observations and zones.
- **Script and notebook.** The model is also a FloPy script and a Jupyter notebook, generated from the same state, byte for byte the same code in both.
- **Agent.** An AI agent that runs on your own Claude Code or Codex account. It changes the model only by driving the real controls of the interface, so everything it does is visible on screen and can be recorded and replayed as a flow.

## Validation on published models

Every model below was written by someone else. GWlink opens it, writes it back, runs it and renders the head iso-surfaces in 3D. Each poster links to the recorded clip of the real interface doing exactly that. The full list, grouped by publisher, is at [gwlink.gwlab.cl/validation](https://gwlink.gwlab.cl/validation).

<table>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-freyberg_usg.mp4"><img src="media/posters/canonical-freyberg_usg.poster.jpg" width="100%" alt="Freyberg MODFLOW-USG"></a><br><sub>Freyberg MODFLOW-USG · MODFLOW-USG</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-milford.mp4"><img src="media/posters/canonical-milford.poster.jpg" width="100%" alt="GMDSI Milford MFUSG"></a><br><sub>GMDSI Milford MFUSG · MODFLOW-USG</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-lakeex2a.mp4"><img src="media/posters/canonical-lakeex2a.poster.jpg" width="100%" alt="lakeex2a — MF6 SFR 22-reach chain coupled to LAK via MVR"></a><br><sub>lakeex2a — MF6 SFR 22-reach chain coupled to LAK via MVR · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-twri.mp4"><img src="media/posters/canonical-twri.poster.jpg" width="100%" alt="TWRI"></a><br><sub>TWRI · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-advtidal.mp4"><img src="media/posters/canonical-advtidal.poster.jpg" width="100%" alt="Advanced Tidal"></a><br><sub>Advanced Tidal · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-bcf2ss.mp4"><img src="media/posters/canonical-bcf2ss.poster.jpg" width="100%" alt="BCF2 Steady-State"></a><br><sub>BCF2 Steady-State · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-mf6_tutorial01.mp4"><img src="media/posters/canonical-mf6_tutorial01.poster.jpg" width="100%" alt="MF6 Tutorial 01"></a><br><sub>MF6 Tutorial 01 · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_fhb.mp4"><img src="media/posters/canonical-ex_gwf_fhb.poster.jpg" width="100%" alt="Flow and Head Boundary Replication"></a><br><sub>Flow and Head Boundary Replication · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_capture.mp4"><img src="media/posters/canonical-ex_gwf_capture.poster.jpg" width="100%" alt="Capture Fraction Analysis"></a><br><sub>Capture Fraction Analysis · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_nwt_p03a.mp4"><img src="media/posters/canonical-ex_gwf_nwt_p03a.poster.jpg" width="100%" alt="MODFLOW-NWT Problem 3 High Recharge"></a><br><sub>MODFLOW-NWT Problem 3 High Recharge · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_bump_p01a.mp4"><img src="media/posters/canonical-ex_gwf_bump_p01a.poster.jpg" width="100%" alt="Flow Diversion Newton"></a><br><sub>Flow Diversion Newton · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_nwt_p02a.mp4"><img src="media/posters/canonical-ex_gwf_nwt_p02a.poster.jpg" width="100%" alt="MODFLOW-NWT Problem 2 Newton"></a><br><sub>MODFLOW-NWT Problem 2 Newton · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_zaidel_p02a.mp4"><img src="media/posters/canonical-ex_gwf_zaidel_p02a.poster.jpg" width="100%" alt="Zaidel Drainage Problem"></a><br><sub>Zaidel Drainage Problem · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_hanir.mp4"><img src="media/posters/canonical-ex_gwf_hanir.poster.jpg" width="100%" alt="Horizontal Anisotropy Reference"></a><br><sub>Horizontal Anisotropy Reference · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-ex_gwf_whirl.mp4"><img src="media/posters/canonical-ex_gwf_whirl.poster.jpg" width="100%" alt="Whirl Flow"></a><br><sub>Whirl Flow · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-flopy_structured_grid_demo.mp4"><img src="media/posters/canonical-flopy_structured_grid_demo.poster.jpg" width="100%" alt="FloPy Structured Grid Demo"></a><br><sub>FloPy Structured Grid Demo · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-flopy_budget_example.mp4"><img src="media/posters/canonical-flopy_budget_example.poster.jpg" width="100%" alt="FloPy Budget Example"></a><br><sub>FloPy Budget Example · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-flopy_formhead.mp4"><img src="media/posters/canonical-flopy_formhead.poster.jpg" width="100%" alt="FloPy Formhead"></a><br><sub>FloPy Formhead · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-flopy_time_demo.mp4"><img src="media/posters/canonical-flopy_time_demo.poster.jpg" width="100%" alt="FloPy Time Demo"></a><br><sub>FloPy Time Demo · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-flopy_splitter_model.mp4"><img src="media/posters/canonical-flopy_splitter_model.poster.jpg" width="100%" alt="FloPy Splitter Model"></a><br><sub>FloPy Splitter Model · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-freyberg_usg_output.mp4"><img src="media/posters/canonical-freyberg_usg_output.poster.jpg" width="100%" alt="Freyberg USG with Outputs"></a><br><sub>Freyberg USG with Outputs · MODFLOW-USG</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-freyberg_tvm.mp4"><img src="media/posters/canonical-freyberg_tvm.poster.jpg" width="100%" alt="Freyberg TVM (Time-Varying Materials)"></a><br><sub>Freyberg TVM (Time-Varying Materials) · MODFLOW-USG</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-cln_well_mfusg.mp4"><img src="media/posters/canonical-cln_well_mfusg.poster.jpg" width="100%" alt="CLN Vertical Wells MFUSG"></a><br><sub>CLN Vertical Wells MFUSG · MODFLOW-USG</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-cln_conduit_mfusg.mp4"><img src="media/posters/canonical-cln_conduit_mfusg.poster.jpg" width="100%" alt="MODFLOW-USG CLN Conduit Well (Example 3a)"></a><br><sub>MODFLOW-USG CLN Conduit Well (Example 3a) · MODFLOW-USG</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-maw_disv.mp4"><img src="media/posters/canonical-maw_disv.poster.jpg" width="100%" alt="MAW MF6 DISV"></a><br><sub>MAW MF6 DISV · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-disv_voronoi.mp4"><img src="media/posters/canonical-disv_voronoi.poster.jpg" width="100%" alt="DISV Voronoi Grid"></a><br><sub>DISV Voronoi Grid · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-hfb_mf6_disv.mp4"><img src="media/posters/canonical-hfb_mf6_disv.poster.jpg" width="100%" alt="HFB MF6 DISV"></a><br><sub>HFB MF6 DISV · MODFLOW 6</sub></td></tr>
<tr><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-hfb_mfusg.mp4"><img src="media/posters/canonical-hfb_mfusg.poster.jpg" width="100%" alt="HFB MFUSG"></a><br><sub>HFB MFUSG · MODFLOW-USG</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-hfb_rich_mf6.mp4"><img src="media/posters/canonical-hfb_rich_mf6.poster.jpg" width="100%" alt="HFB Rich MF6"></a><br><sub>HFB Rich MF6 · MODFLOW 6</sub></td><td width="33%" valign="top"><a href="https://gwlink.gwlab.cl/videos/validation/canonical-hfb_rich_mfusg.mp4"><img src="media/posters/canonical-hfb_rich_mfusg.poster.jpg" width="100%" alt="HFB Rich MFUSG"></a><br><sub>HFB Rich MFUSG · MODFLOW-USG</sub></td></tr>
</table>

The round trip is a strong check on the file layer. It catches a package silently dropped, an array reshaped or a stress period lost. It is not a claim that GWlink reproduces every published figure to the last decimal, and it says nothing about whether your own model is a good model. Details in [docs/validation.md](docs/validation.md).

## Examples

Four GWlink workspaces under [examples/](examples/), ready to open on your first session. Each holds the project, the model GWlink wrote, the run where it fits, and the published deck it was imported from. Freyberg USG with 25 stress periods, a DISV Voronoi grid, TWRI, and an SFR chain coupled to lakes. Each one is public domain or GWLab's own, and each is part of the validation suite above.

## Reporting a problem

Open an [issue](../../issues/new/choose). The HELP stage inside the app also has a *Report a problem* link that opens an email with the version and build already filled in.

## Links

- Website [gwlink.gwlab.cl](https://gwlink.gwlab.cl)
- Download GWlinkViewer [gwlink.gwlab.cl/viewer](https://gwlink.gwlab.cl/viewer)
- Changelog [gwlink.gwlab.cl/changelog](https://gwlink.gwlab.cl/changelog)
- Specifications, engine by engine and package by package [gwlink.gwlab.cl/specifications](https://gwlink.gwlab.cl/specifications)
- FAQ [gwlink.gwlab.cl/faq](https://gwlink.gwlab.cl/faq)

GWlink is developed by [GWLab](https://www.gwlab.cl) in Santiago, Chile.

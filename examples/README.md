# Examples

Four GWlink workspaces, one per folder. Each one was made by importing a published MODFLOW deck with GWlink, writing it back and running it. So every folder holds the project GWlink saved (`project.gwlink.json`), the model GWlink wrote (`model/`, with the heads and budget of the run where they fit), the arrays it keeps beside the project (`data/`) and the deck it started from (`source/`). They are the same models GWlink's validation suite imports, writes back and runs on every build.

[GWlinkViewer](https://gwlink.gwlab.cl/viewer) can open these workspaces and inspect their saved models and results. Writing or running a model requires the full GWlink edition.

| Folder | Model | Engine | Grid | What it shows | Source |
|---|---|---|---|---|---|
| [freyberg-usg](freyberg-usg) | Freyberg MODFLOW-USG | MODFLOW-USG | DISU, 3 layers, 4,497 cells, 25 stress periods | The classic teaching model as an unstructured deck with SFR, GHB, wells and recharge through 25 periods. Good first model for TIME and RESULTS. | [FloPy examples](https://github.com/modflowpy/flopy), public domain (USGS) |
| [disv-voronoi](disv-voronoi) | DISV Voronoi Grid | MODFLOW 6 | DISV, 1 layer, 1,692 cells | A Voronoi grid with constant heads, to see how GWlink draws and inspects unstructured cells. | GWLab |
| [twri](twri) | TWRI | MODFLOW 6 | DIS, 5 layers, 1,125 cells | The USGS benchmark with drains, wells and recharge. Small and quick, useful for ZBUD. | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples), public domain (USGS) |
| [lakeex2a](lakeex2a) | lakeex2a | MODFLOW 6 | DIS, 5 layers, 27 by 17 | A 22 reach SFR chain coupled to two lakes through MVR. Surface water in one small deck. Written but not run, its budget file is 52 MB. | [FloPy test data](https://github.com/modflowpy/flopy), public domain (USGS) |

## Opening one

1. Download or clone this repository.
2. Open GWlink. On the welcome screen choose **Open workspace by path** and type the example folder, for instance `.../examples/freyberg-usg`. The folder is the workspace, so open it from a place you can write to.
3. The model loads in PACKAGES. RESULTS already has the run for three of the four. For lakeex2a, or to run any of them again, go to RUN and press **Write model**, then **Run simulation**.

To see the import itself rather than its result, choose **Import MODFLOW model** instead and point it at the `source/` folder of any example.

## Milford

The GMDSI Milford model (MODFLOW-USG, 190,080 cells, CLN wells) is also in the validation suite, but it is 54 MB and published by GMDSI under AGPL-3.0, so it is not copied here. Clone [gmdsi/gmdsi](https://github.com/gmdsi/gmdsi) and import `tutorials/worked_examples/milford_files/calibration`. The deck carries no projection, so type 3437 in the EPSG field of the import dialog (NAD83 / New Hampshire, US survey feet) to see it on the map.

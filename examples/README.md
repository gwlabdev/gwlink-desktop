# Examples

Four MODFLOW models to open in GWlink, each in its own folder. They are the same decks GWlink's validation suite imports, writes back and runs on every build.

| Folder | Model | Engine | Grid | What it shows | Source |
|---|---|---|---|---|---|
| [freyberg-usg](freyberg-usg) | Freyberg MODFLOW-USG | MODFLOW-USG | DISU, 3 layers, 4,497 cells, 25 stress periods | The classic teaching model as an unstructured deck with SFR, GHB, wells and recharge through 25 periods. Good first model for TIME and RESULTS. | [FloPy examples](https://github.com/modflowpy/flopy), public domain (USGS) |
| [disv-voronoi](disv-voronoi) | DISV Voronoi Grid | MODFLOW 6 | DISV, 1 layer, 1,692 cells | A Voronoi grid with constant heads, to see how GWlink draws and inspects unstructured cells. | GWLab |
| [twri](twri) | TWRI | MODFLOW 6 | DIS, 5 layers, 1,125 cells | The USGS benchmark with drains, wells and recharge. Small and quick, useful for ZBUD. | [MODFLOW 6 examples](https://github.com/MODFLOW-USGS/modflow6-examples), public domain (USGS) |
| [lakeex2a](lakeex2a) | lakeex2a | MODFLOW 6 | DIS, 5 layers, 27 by 17 | A 22 reach SFR chain coupled to two lakes through MVR. Surface water in one small deck. | [FloPy test data](https://github.com/modflowpy/flopy), public domain (USGS) |

## Opening one

1. Download or clone this repository.
2. Open GWlink. On the welcome screen choose **Import MODFLOW model** (also under DATA once a workspace is open).
3. Point it at the example folder. GWlink finds the name file, translates the deck and creates a new workspace next to it.
4. Go to RUN and press **Write model**, then **Run simulation**. The results open in RESULTS.

Only the input files are here. Heads and budgets are produced by your own run.

## Milford

The GMDSI Milford model (MODFLOW-USG, 190,080 cells, CLN wells) is also in the validation suite, but it is 54 MB and published by GMDSI under AGPL-3.0, so it is not copied here. Clone [gmdsi/gmdsi](https://github.com/gmdsi/gmdsi) and import `tutorials/worked_examples/milford_files/calibration`. The deck carries no projection, so type 3437 in the EPSG field of the import dialog (NAD83 / New Hampshire, US survey feet) to see it on the map.

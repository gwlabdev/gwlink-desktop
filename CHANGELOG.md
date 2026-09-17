# Changelog

All notable changes to GWlink are recorded here. Format follows
[Keep a Changelog](https://keepachangelog.com/en/1.1.0/); versions follow
[SemVer](https://semver.org/spec/v2.0.0.html).

## [Unreleased]

## [0.1.92] - 2026-09-17

- Editable CSV table links for boundary records, zone categories in 2D sections, and zone fixes.


## [0.1.91] - 2026-09-16

- Route MF6 recharge to the receiving layer and fix agent setup on Windows.


## [0.1.90] - 2026-09-16

- Use cell selection tools consistently in Grid.


## [0.1.89] - 2026-09-15

- Keep section drawing controls compact.


## [0.1.88] - 2026-09-15

- Show clear feedback while drawing 2D sections.


## [0.1.87] - 2026-09-12

- Viewer link shows the copy as it runs and uploads 16 files at a time; packaged app trusts TLS roots and carries the local API token


## [0.1.86] - 2026-09-10

- Notebook export carries editable zone tables for recharge and hydraulic properties


## [0.1.85] - 2026-09-09

- Clear recents button; white icon tile


## [0.1.84] - 2026-09-08

- DXF plan-view outline on the 2D map: solids seen from above, one polygon per DXF layer, TIN slits sealed


## [0.1.83] - 2026-09-08

- Map legend as a paper plate with per-map colour scales, movable and foldable; draw-order drag ghost; selections save as one dissolved polygon


## [0.1.82] - 2026-09-07

- Map legend overlay, reversible colour ramps, layer reorder that works in the packaged app


## [0.1.81] - 2026-09-07

- Improve output controls, sections, and map legends.


## [0.1.80] - 2026-09-06

- Saved 2D sections, property legends, and map scale bar.


- Save, name, reopen, rename, and delete reusable 2D sections; saved section
  geometry persists with the project and recalculates against the active grid
  and timestep
- Add a scalar legend to 2D section property fills, showing the parameter,
  units, numeric range, and linear or logarithmic color transformation
- Make the map scale bar available throughout DATA, GRID, PACKAGES, and RESULTS;
  it follows the live map zoom and coordinate system and is included in PNG
  captures when visible
- Improve CLN imports by ignoring incomplete coordinates found in inline
  comments, and prevent accidental text selection when opening data-row menus

## [0.1.79] - 2026-09-04

- Bug fixes and improvements.


- Record which mesh engine generated each grid (`MESH_ENGINE_VERSION`, now
  at 2 after P215), warn in the replace-grid dialog before regenerating a
  grid an older engine made, and pin three public recipes in CI so an
  engine change can no longer alter an existing model's mesh silently
- Add `docs/mesh-engine-changelog.md`, the detailed history of the meshing
  engine: every change with its date, commit, PR, the rule that moved and
  whether an existing recipe now builds a different mesh, grouped by
  `MESH_ENGINE_VERSION`. `npm run audit:mesh-engine-changelog` fails when an
  engine commit has no entry

## [0.1.78] - 2026-09-04

- Improve MFUSG import, export, and results reliability


## [0.1.77] - 2026-09-03

- Fix native DISU recharge writing


## [0.1.76] - 2026-09-03

- Add native DISU writing, plus CLN, temporal-zone, and results reliability improvements


## [0.1.75] - 2026-09-01

- Fix bundled Node JIT entitlements on macOS


## [0.1.74] - 2026-09-01

- Improve mesher face topology consistency


## [0.1.73] - 2026-08-31

- Bundle pinned Node runtime so the mesher and in-app agent work without a system Node install


## [0.1.72] - 2026-08-26

- Improve performance curve binding


## [0.1.71] - 2026-08-24

- 3D iso-surfaces now stop at the model boundary. MAW well heads and LAK lake stages can be plotted in RESULTS. Wells added from a shapefile keep their own names. More reliable agent actions.


## [0.1.70] - 2026-08-24

- Window close works again after signing out; NPF advanced options: alternative cell averaging and highest cell saturation.


## [0.1.69] - 2026-08-24

- Help search and Show-me discovery; BC link save verified by the agent; single button spinner; dev ports reclaimed.


## [0.1.68] - 2026-08-24

- Inspector indices now read 1-based; fix property sources, run diagnostics, and cell-table import.


## [0.1.67] - 2026-08-23

- Fix the duplicate IMS solver panel and the import of disjoint stress-period rows.


## [0.1.66] - 2026-08-23

- Lloyd, space2vor Voronoi cells and space2vor triangles now share one
  physical cell-size and gradation contract. Point slopes and grace are no
  longer lost, triangular edge targets are area-calibrated, and dense GIS line
  vertices no longer create unintended refinement.

- GRID now shows engine-specific mesh settings: Lloyd keeps its own controls,
  while space2vor exposes the 12 persisted size-field, optimization, census,
  and finalization parameters that its backend adapter actually consumes.

- Voronoi cells can be built by the space2vor engine (CDT + target size field
  + Tournois optimize + domain-restricted dual) instead of the in-house lloyd
  pipeline. Pick it per grid in the GRID sidebar ("Mesher"), per request
  (`mesher`), or app-wide with `GWLINK_VORONOI_ENGINE`; the request wins and an
  unknown name is refused. Both engines conform and validate their cells
  against the boundary, so neither can ship a mesh with holes in the domain.

- Voronoi grids are meshed by cdt-ts (TypeScript port of Triangle, runs on the
  Node the agent already needs) instead of the downloaded `triangle` binary.
  Same flags as before (`-q20 -a -D`), so the grids are identical cell for
  cell. `GWLINK_TRIANGULATOR=triangle` keeps the old path for A/B; `triangle`
  is no longer downloaded at startup unless selected.

## [0.1.65] - 2026-08-22

- Improve startup, sign-in updates, shapefile exports, and map state.


## [0.1.64] - 2026-08-22

- Pin and verify MODFLOW executable downloads.


## [0.1.63] - 2026-08-21

- Sign-in now uses the same account system as the website; sign in again after updating


## [0.1.62] - 2026-08-21

- Sign-in gate redesigned on the workspace stage; app access now follows the approval flag from the access-requests dashboard

## [0.1.61] - 2026-08-20

- Zone table numbers commit on blur, so scientific notation survives typing


## [0.1.60] - 2026-08-19

- Fix agent access to deep-layer sources and package removal.


## [0.1.59] - 2026-08-19

- Add per-layer NPF and STO conversion controls.


## [0.1.58] - 2026-08-18

- Allow agents to open workspaces from cold start.


## [0.1.57] - 2026-08-18

- Fix contour visibility and portable Macul result paths.


## [0.1.56] - 2026-08-18

- Workspace gate opens on the live Andean basin


## [0.1.55] - 2026-08-18

- Fix zone rasterization and action invocation reliability


## [0.1.54] - 2026-08-17

- Require authentication for desktop sign-in


## [0.1.53] - 2026-08-17

- Clear coordinate frame on project reset


## [0.1.52] - 2026-08-17

- Improve Welcome landing experience


## [0.1.51] - 2026-08-17

- Make boundary gradation agent-accessible


## [0.1.50] - 2026-08-17

- Improve Voronoi refinement controls, mesh diagnostics, and temporal cleanup


## [0.1.49] - 2026-08-17

- Advanced Voronoi mesh tuning panel and DISV vertex merge fix


## [0.1.48] - 2026-08-16

- Voronoi grid: declared cell sizes are built — fill quota and grace band restored


## [0.1.47] - 2026-08-16

- Review of grid generator


## [0.1.46] - 2026-08-16

- Voronoi grid engine: segment mirrors, 20-degree Delaunay remate, stable DISV vertices, and boundary rows at natural depth


## [0.1.45] - 2026-08-15

- adjust in voronoi engine


## [0.1.44] - 2026-08-15

- Improve cross sections, MATCH brushing, and desktop compatibility


## [0.1.43] - 2026-08-15

- Improve isolated development environments and zone import validation


## [0.1.42] - 2026-08-15

- Order-independent transparency for 3D iso surfaces: no more tearing or speckle at any opacity


## [0.1.41] - 2026-08-14

- Restore rainbow elevation colors in 3D


## [0.1.40] - 2026-08-14

- Improve large-model rendering and model import workflows


## [0.1.39] - 2026-08-14

- Restore large-model mesh rendering and controls in authenticated desktop builds


## [0.1.38] - 2026-08-14

- Improve large-model reliability, imports, and desktop lifecycle


## [0.1.37] - 2026-08-13

- Giant models render from map tiles; updating now confirms the restart


## [0.1.36] - 2026-08-12

- Replace a parameter's spatial provenance instead of stacking on it


## [0.1.35] - 2026-08-12

- Forward ✦


## [0.1.34] - 2026-08-12

- MF6 GWT transport: CNC/SRC as real boundary packages authored in PROPS


## [0.1.33] - 2026-08-09

- Prevent MapView normalization loops while loading large projects.


## [0.1.32] - 2026-08-09

- Make scratch status queries read-only and stabilize loaded model state.


## [0.1.31] - 2026-08-09

- Ensure Zones tab mounts its panel


## [0.1.30] - 2026-08-08

- Verify zone table link results


## [0.1.29] - 2026-08-08

- Fix agent control of Radix dropdowns


## [0.1.28] - 2026-08-08

- Fix package accordion targeting and verification


## [0.1.27] - 2026-08-08

- Fix agent save verification and modal blocking


## [0.1.26] - 2026-08-08

- Preserve multilayer BC sources and fix agent UI targeting


## [0.1.25] - 2026-08-08

- Allow MCP to open recent workspaces


## [0.1.24] - 2026-08-08

- Improve external MCP workflows


## [0.1.23] - 2026-08-08

- External MCP E2E and cell Data Source fixes


## [0.1.22] - 2026-08-07

- Fit to bounds works on every model, the 3D camera stays framed under vertical exaggeration, iso-surface colours span the drawn levels, and decimals use dots everywhere.


## [0.1.21] - 2026-08-05

- Fix packaged backend failing to start (corrupt PyInstaller base_library.zip)


## [0.1.20] - 2026-08-05

- Voronoi boundary conformance: meshes now tile the boundary exactly


## [0.1.19] - 2026-08-05

- Zone values link from a CSV again


## [0.1.18] - 2026-08-05

- Type an EPSG code directly in the map CRS picker


## [0.1.17] - 2026-08-05

- Measured distance readout no longer clipped by the toolbar


## [0.1.16] - 2026-08-05

- Installer cleans orphaned files and the tile cache moved out of the install directory



## [0.1.15] - 2026-08-05

- Product name normalized to GWlink



## [0.1.14] - 2026-08-05

- Microsoft Store submission assets and Windows release script fixes



## [0.1.13] - 2026-08-04

- Report a problem path and Windows sign-in fix


## [0.1.12] - 2026-08-04

- Fix email sign-in on Windows


## [0.1.11] - 2026-08-03

- Fix 3D auxiliary zone rendering and add hide-unassigned filter


## [0.1.10] - 2026-08-03

- Fix opening projects with auxiliary zonations


## [0.1.9] - 2026-08-03

- ZBUD reads model output on disk without a redundant Write


## [0.1.8] - 2026-08-01

- Enable PEST MATCH in production and stabilize Macul capture.


## [0.1.7] - 2026-08-01

- Keep map mounted when opening Help


## [0.1.6] - 2026-08-01

- Fix empty PEST depth bands


## [0.1.5] - 2026-08-01

- Smooth 2D section property colors


## [0.1.4] - 2026-08-01

- Fix 2D section property fill artifacts


## [0.1.3] - 2026-08-01

- Render 2D sections by exact crossed cells


## [0.1.2] - 2026-08-01

- Add canonical depth K profile zones


## [0.1.1] - 2026-08-01

- Add headless PESTPP-GLM calibration foundation


## [0.1.0] - 2026-08-01

- Sign-in revocation heartbeat and MODFLOW AI agent tools


## [0.0.99] - 2026-07-31

- Connect the agent to MODFLOW AI and other MCP tool servers


## [0.0.98] - 2026-07-31

- Fix agent flow saving in the packaged app (local API token)


## [0.0.97] - 2026-07-31

- Package icons for SFR/HFB/MAW/DOMAIN, quieter auxiliaries create


## [0.0.96] - 2026-07-31

- Help search: one palette, fixed geometry, visible Find button


## [0.0.95] - 2026-07-31

- Help search over the ui-action-map; agent reveal_action


## [0.0.94] - 2026-07-31

- Section 2D contours on single-layer models; workspaces are always openable


## [0.0.93] - 2026-07-31

- DEM rasters open at 30% opacity


## [0.0.92] - 2026-07-31

- Copy an existing zonation into an auxiliary; fix phantom border token rendering black dividers


## [0.0.91] - 2026-07-31

- Auxiliary zone fields: PROPS auxiliaries, categorical plan/3D views, canonical ZBUD sources


## [0.0.90] - 2026-07-30

- Fix agent screen capture photographing the leftover OAuth browser tab instead of the app


## [0.0.89] - 2026-07-30

- Windows agent fixes from PR 387: cancelable queued turns, native multi-file picker, process-tree stop


## [0.0.88] - 2026-07-30

- Recent projects list in Open Model, visible to the agent via read_state


## [0.0.87] - 2026-07-30

- Ignore replayed OAuth deep links after sign-out


## [0.0.86] - 2026-07-30

- First build on the GWlink Clerk production instance (clerk.gwlab.cl) + security hardening


## [0.0.85] - 2026-07-30

- Security hardening: per-launch local API token, JWT verification, integrity check


## [0.0.84] - 2026-07-30

- Zonation copy: reuse a parameter's zones on other properties or layers, with confirmation


## [0.0.83] - 2026-07-30

- Fix Solver Diagnostics charts growing/shrinking during a run


## [0.0.82] - 2026-07-30

- BC AddSource buffer distance + copy source to layers


## [0.0.81] - 2026-07-30

- Phone-fired agent turns survive iOS backgrounding (detach)


## [0.0.80] - 2026-07-30

- Agent fixes: evict foreign CLI bridge bootstraps; read-only bridge ops fail fast when the window is dead


## [0.0.79] - 2026-07-30

- Zones: All-layers editing + blocked buttons highlight pending applies


## [0.0.78] - 2026-07-30

- Multi-window fixes: new windows wait for their backend before loading; remote mirror retry; per-pid backend logs


## [0.0.77] - 2026-07-30

- Fix multi-window: instance windows get full permissions (close/dialogs) and cascade instead of stacking


## [0.0.76] - 2026-07-30

- Multi-instance: New Window opens a second model with its own backend + agent; workspace lock; per-instance agent discovery
- Agent port discovery survives multiple instances; includes interrupt recovery


## [0.0.75] - 2026-07-29

- Agent recovers from interruptions: queued prompts survive Stop and the session resumes from the transcript


## [0.0.74] - 2026-07-29

- El agente ve y elige opciones de dropdowns (buscador del mapa): offered en invoke + instancias con label en describe


## [0.0.73] - 2026-07-29

- Cámara 2D por coordenadas (centro UTM, zoom, bearing, pitch) y sección A→B tipeada — manejable por el agente


## [0.0.72] - 2026-07-29

- invoke_action dialogPath: el agente responde diálogos nativos (abrir/guardar/exportar) con un path, sin picker


## [0.0.71] - 2026-07-29

- Agente puede abrir proyectos por path (botón Path visible en producción)


## [0.0.70] - 2026-07-29

- Inspector muestra valores de zona en modo link_zone (RCH) + paridad zonas para EVT.rate


## [0.0.69] - 2026-07-29

- Agente: invoke click-to-edit, read_state compacto con lecturas por sección, Zones dock validado E2E


## [0.0.68] - 2026-07-29

- Zone editor: Save siempre habilitado y layout arreglado


## [0.0.67] - 2026-07-29

- Zone link fix: Apply Link batch commit, agent-drivable Zone Editor


## [0.0.66] - 2026-07-29

- igwlink remote access: tailnet listener + live screen monitor in the packaged app


## [0.0.65] - 2026-07-29

- DEM fetch links Top to DEM Elevation officially


## [0.0.64] - 2026-07-28

- Inspector: zonas UH visibles + lectura BC con cache por revision (hover 9s -> 90ms)


## [0.0.63] - 2026-07-28

- fix overlay and performance


## [0.0.62] - 2026-07-27

- Agent can edit CodeMirror expression inputs; DEM reachable and persisted


## [0.0.61] - 2026-07-26

- Agent refactor, Help updates, and runtime welcomes


## [0.0.60] - 2026-07-26

- Agent observes dialog confirmations and cancellations


## [0.0.59] - 2026-07-26

- Agent receives native dialog selections


## [0.0.58] - 2026-07-26

- Agent refactor


## [0.0.57] - 2026-07-25

- Fix MAW package activation sync

## [0.0.56] - 2026-07-24

- Use production authentication on gwlink.gwlab.cl

## [0.0.55] - 2026-07-22

- Add notebook setup files


## [0.0.54] - 2026-07-22

- Save generated notebooks in workspace


## [0.0.53] - 2026-07-22

- Add notebook array sidecars


## [0.0.52] - 2026-07-22

- Fix grid draw order


## [0.0.51] - 2026-07-21

- Fix map layer controls


## [0.0.50] - 2026-07-21

- Add map layer controls


## [0.0.49] - 2026-07-21

- Smoother iso-surfaces.


## [0.0.48] - 2026-07-21

- Add panel-specific PNG capture buttons for plan and 3D views.


## [0.0.47] - 2026-07-21

- Improve 3D overlay loading feedback and stress period synchronization.


## [0.0.46] - 2026-07-21

- Contours now default to black in the 2D section and map results views for better readability. Approved by admin.


## [0.0.45] - 2026-07-21

- CAD 3DFACE DXF support, CRS fix for imported-model CAD overlays, high-visibility red section line, and contour label pin/hide/restore in the 2D section. Approved by admin.


## [0.0.44] - 2026-07-21

- 3D improvements


## [0.0.43] - 2026-07-21

- Add 3D.js isosurface visualization.


## [0.0.42] - 2026-07-20

- Fix drain values per stress period and update Quebradona workflows


## [0.0.41] - 2026-07-20

- Import ZBUD zones from categorical shapefiles


## [0.0.40] - 2026-07-17

- Preserve and display spatial-link provenance


## [0.0.39] - 2026-07-16

- Portable project sources and preserved mesh refinement provenance.


## [0.0.38] - 2026-07-16

- Add zone-based multiimport for hydraulic properties and stabilize MapView teardown

## [0.0.37] - 2026-07-15

- Lock the visual viewport so the top bar no longer slides off-screen when focusing panel inputs


## [0.0.36] - 2026-07-15

- Add NPF K33 ratio and STO ICONVERT controls


## [0.0.35] - 2026-07-14

- Fix layered property copying, reload values, and RCH Base persistence


## [0.0.34] - 2026-07-14

- Prevent macOS WebView viewport jumps and refresh grid-dependent property meshes safely


## [0.0.33] - 2026-07-14

- Canonical layered properties, grid replacement confirmation, and explicit Newton notebook guidance


## [0.0.32] - 2026-07-13

- Live MF6 solver diagnostics


## [0.0.31] - 2026-07-13

- Fix DISV precision and automatic initial-head display


## [0.0.30] - 2026-07-13

- Fix raster linking in packaged macOS app


## [0.0.29] - 2026-07-13

- Add Save As for workspace projects


## [0.0.28] - 2026-07-13

- Fix immediate refinement layer color refresh


## [0.0.27] - 2026-07-13

- Repaint linked layer colors immediately


## [0.0.26] - 2026-07-13

- Fix packaged DEM rendering and Domain layer behavior


## [0.0.25] - 2026-07-13

- Boundary validation and synchronized layer colors


## [0.0.24] - 2026-07-13

- Add linked elevation ranges and clamp notebook arrays


## [0.0.23] - 2026-07-06

- Quadtree refinement levels accept any non-negative value; warn above 10


## [0.0.22] - 2026-07-05

- Enable online sign-in (auth required)


## [0.0.21] - 2026-07-05

- macOS updater verification release


## [0.0.20] - 2026-07-05

- Restore native macOS auto-update


## [0.0.19] - 2026-07-01

- Open macOS updates as DMG downloads


## [0.0.18] - 2026-07-01

- Add log scale for property maps and optimize layer switching


## [0.0.17] - 2026-06-30

- Fix offline macOS startup when auth is disabled.
- Force packaged desktop builds to use dynamic sidecar ports.

## [0.0.16] - 2026-06-30

- Fix macOS updater install
- Add release auth mode flag for builds with or without online sign-in


## [0.0.15] - 2026-06-30

- Fix overlapping menus


## [0.0.14] - 2026-06-30

- Release automation and agent guide cleanup.

## [0.0.13] - 2026-06-30

### Desktop authentication

- Desktop sign-in now carries the Clerk user profile into the Tauri session, so
  the title bar shows the real user avatar or initials instead of only a logout
  icon.

### History Match (in progress)

- **P123 — Match simplification**: History Match will edit K only; write and run
  reuse the canonical RUN path instead of a parallel `hm-run` seam. Removes the
  P98 run tree; persists observations + K ladder in the model `.gwlink.json`.

## [0.0.11] - 2026-06-24

### Inspector

- Fixed Cell Inspector hover on the base mesh when no property map, NPF row, or
  boundary-condition package is expanded. The Inspector now hit-tests the mesh
  directly and can show the default readout or watch list from a plain mesh.

### Data import and model setup

- **P166 — Multilayer source import**: imported boundary-condition cell tables
  now hydrate atomically into layer sources, including stress-period window
  mapping.
- Preserved CSV source paths during data imports and switched Safari upload
  handling to label-driven data upload controls.
- Added AdvTidal multilayer DRN CSV test data.

### Grid and visualization

- **P165 — Field-driven grid refinement**: refinement defaults can now be
  sourced from data fields, with validation for field-backed values.
- **P164 — Inactive 3D overlay**: inactive cells can be visualized in 3D, with
  layer-local matching fixes for inactive box cells.
- **P162 — Synthetic FGB store**: editable imported FGB values are preserved
  through the synthetic store path.
- Selection library work landed for saving selections back to the Data Library.

## [0.0.4] - 2026-05-24

### Transient BC round-trip + Data Library links

- **P115 — Constant curve skip**: constant-in-time BC cells stay static
  `perCell` on import so exported series CSVs hold only cells that actually vary.
- **P116 — Shape + series round-trip**: imported per-cell transient BC exports
  to a shapefile (geometry + `cell_id` + constant columns) plus a long-format
  series CSV and re-imports by joining on `cell_id`. Proven byte-identical on
  the fito MFUSG model (`write(import(fito)) ==
  write(reimport(export(import(fito))))`). Inactive list-BC periods serialize as
  `None`, not phantom zeros.
- **P117 — Imported BC as shape+series link**: imported transient BC shows as a
  read-through Link in the Data Library (FGB geometry + per-layer series item
  joined by `cell_id`) instead of an opaque CURVE badge.
- **P121 — Dedup-aware series export**: DATA-stage export writes unique curves
  once with a per-cell series-id column in the shapefile, shrinking multi-million-row
  CSVs to spreadsheet-reviewable size while keeping reimport byte-identical.

### Desktop packaging

- **P120 — Native Tauri save dialogs**: Export `.py`, Export ZIP, project Save,
  shapefile/CSV/screenshot exports, and mesh export route through
  `saveFileWithDialog` (`@tauri-apps/plugin-dialog` + `@tauri-apps/plugin-fs`)
  in the packaged app; browser Blob download remains the dev/web fallback.
- **New Project** now calls `POST /api/model/reset` so a fresh project starts
  from an empty backend (no stale mesh, packages, or uploaded shapes).

### 3D viewer

- **Native Three.js viewer**: RESULTS now uses the native Three.js 3D viewer
  as the in-app visualization surface, with compact backend mesh streams for
  model geometry, water-table surfaces, terrain draping, BC overlays, layer
  clipping, scalar inspection, and arbitrary slices.
- **P122 — Wireframe + vertical exaggeration defaults**: wireframe mode uses a
  sane solid-gray default; vertical exaggeration defaults to ~2× instead of
  saturating the slider max on load. Dead wireframe scalar-coloring subsystem
  removed.

### Import UX

- **Per-package progress ticks** during model import so long imports show which
  package is being processed.

## [0.0.3] - 2026-05-20

### MATCH stage — history matching

- **P96 — Backend-canonical history match session**: the comparison
  between observed and simulated heads now lives in the backend as a
  canonical session. Observation field mapping is threaded through the
  router and session so the frontend reads it through queries instead of
  reconstructing it locally.
- **P97 — History match panel**: new MATCH stage in the workflow with a
  split view of the hydraulic-conductivity (K) field and simulated heads.
  A paint-style brush edits K directly on the mesh with live preview, a
  thicker brush, a persistent K-step readout, and catalog-backed
  observations. K mesh and observation residuals render as MapLibre
  overlays alongside the map.

### SFR — Streamflow Routing for MODFLOW 6

- **P92 / P94 — SFR package (MF6)**: new advanced boundary-condition
  package. Reaches are derived from a line shapefile, with upstream →
  downstream connectivity auto-built from vertex order. Covers typed
  `SFRParams`, the writer orchestrator and satellites, MF6 import with a
  structural round-trip, `GET /api/model/sfr/reaches`, the complete MF6
  SFR temporal round-trip, and the standalone-script export section.
  MF6 package count goes 12 → 13.
- **SFR map + agent**: coral-rose reach overlay that turns on
  automatically when SFR is present, frontend package registry entry,
  agent tool, and per-reach `PERIODDATA` temporal values surfaced in the
  cell inspector.
- **P95 — Flow S videos**: scripted SFR manual + agent-parity captures,
  with reach ordering and source append order fixed.

### 3D viewer (VTK)

- **Render mode toggle**: switch between shell and full render in the 3D
  viewer controls.
- **Reliable startup**: the 3D viewer no longer gets stuck on
  "VTK WASM not initialized" when the pane opens. Initialization waited
  on a single 100 ms timer and bailed silently if the canvas had not been
  laid out yet; it now waits for the canvas to have real dimensions
  (`ResizeObserver`) before starting, and the fallback message no longer
  blames a missing `VtuViewer.wasm` for what is a timing issue.

### Other improvements

- **Agent**: canonical `ParamAssignment` schemas and an `inspect_model`
  verifier; MFUSG mesher and griddata resolver now unwrap
  `ParamAssignment` dicts.
- **OC**: defaults to `PRINT BUDGET`; ATS toggle surfaced for MFUSG.
- **PROPS**: the stress-period badge only shows for parameters actually
  bound to a curve.
- **GRID**: the grid quality report collapses behind an off-by-default
  chevron.
- **Tooling**: `POST /api/model/reset` for clean E2E/video runs.

## [0.0.2] - 2026-05-16

### Splash screen + boot handshake

- **P89 — Splash capability**: dedicated splash window (`/splash.html`)
  shown while the backend boots. Listens to `boot://status`, `log://line`,
  and `app://ready` Tauri events; main window stays hidden until ready.
- **P90 — Backend URL awaitable**: `backend_base_url` / `tile_proxy_base_url`
  IPC commands wait on a `tokio::sync::watch` channel so the webview can
  `await` them instead of polling, and surface setup-time errors through
  the same channel instead of panicking the Rust process.
- **P91 — Setup handshake**: Rust polls `/health`, then shows the main window
  and closes the splash. The webview resolves the dynamic sidecar URL via
  IPC only (no duplicate browser health probe).
- **Boot logging on the splash**: `backend/startup_log.py` emits
  `__BOOT__ <message>` markers on stdout; the Rust shell forwards them
  to the splash window so users see real boot progress instead of a
  static spinner.
- **`shortcuts/gwlink-build.bat` fix**: aligned with
  `backend/build_sidecar.sh` — switched to `--onedir` PyInstaller output
  and copies to `frontend/src-tauri/resources/gwlink-server/` (the path
  `tauri.conf.json` actually bundles). Previous `--onefile` + `binaries/`
  layout produced installers with an empty resources folder, which made
  the sidecar fail to spawn and left the splash stuck on
  `starting GWlink`.
- **Canonical app version**: `frontend/src-tauri/Cargo.toml` is now the
  single source of truth for the app version.
  - `tauri.conf.json` drops its `version` field and inherits from Cargo.
  - `splash.html` reads the version at runtime via
    `window.__TAURI__.app.getVersion()` instead of a hardcoded string.
  - `frontend/scripts/sync-version.mjs` (wired into npm `prebuild`)
    syncs `package.json` from Cargo.toml on every build, so a release
    bump only touches Cargo.toml + `CHANGELOG.md`.

## [0.0.1] - initial

Baseline release before the splash work landed.

# APEX-ERW Dashboard v2

## Run
Open `index.html` in a modern browser. For best results (especially CSV fetch and embedded maps), serve this folder using a local web server:

```bash
python -m http.server 8000
```

Then visit `http://localhost:8000`.

## Included
- All CSV tables found in the supplied CIPA-AI ERW archive, catalogued in `data/data_catalog.json`.
- All PNG/JPG/WebP figures found in the archive.
- Both supplied interactive HTML maps.
- All GeoTIFF and auxiliary raster files found in the archive.
- Source proposal documents and model configuration files.
- Interactive annual charts, table explorer, figures gallery, maps, formula calculators and model/evidence notes.

## Evidence and interpretation
The source model configuration identifies 2,459 samples, four environmental/social clusters, a 2025 screening year and no available carbon-removal target labels. Environmental predictors do not independently establish measured ERW carbon removal. Candidate-area estimates are preliminary screening results, not approvals or confirmed eligible treatment land.

The dashboard preserves source data as supplied. It does not silently impute missing values or convert proxies into measured social outcomes. Formula calculators are transparent screening tools; confirm variable definitions, units and model provenance before formal publication.

## Data access
Tables are loaded on demand from `data/tables/`. Figures are in `assets/figures/`; maps are in `maps/`; rasters are retained in `data/rasters/`. Large GeoTIFFs are included as source files and are not automatically rendered in the browser.

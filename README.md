# Parallel Satellite Image Analysis – Stage 1 (Sequential NDVI)

ARTI 503 · Group 1 · NDVI = (NIR − Red) / (NIR + Red) on Sentinel-2 L2A bands B04 and B08.

## Folder structure
```
Parallel-Satellite-Image-Analysis_Code/
├── data/
│   ├── sentinel2/              original Sentinel-2 files (only the data preparer needs these)
│   └── ndvi_input_4096.npz     shared input file – download from the team drive
├── src/
│   ├── 0_prepare_data.ipynb    ONE person: cuts the 4096 x 4096 area -> ndvi_input_4096.npz
│   └── 1_sequential_ndvi.ipynb EVERYONE: runs the benchmark, prints a line for the Google Sheet
├── results/
└── README.md
```

## What is measured
Only the NDVI calculation (data is loaded into memory first), for 1024², 2048² and 4096² pixel areas,
in 512 × 512 tiles: 1 warm-up and 5 timed runs each, reporting the median.

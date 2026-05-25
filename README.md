# Stress-Testing Object Detection on MAN TruckScenes: A Condition-Stratified Evaluation

## Repository contents

- **`main.ipynb`** — main pipeline: 3D→2D projection, YOLO dataset export, training (baseline / clear-only / oversampled), holdout evaluation, per-condition and per-camera analysis. [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1d9YfOn3i4hoBOXpK067mPvCRdq9v4TiT?usp=sharing)
- **`metadata_analysis.ipynb`** — exploratory analysis of the TruckScenes condition tags (condition distribution analysis across train/val splits, cross-condition gap identification, per-class composition by condition, camera position analysis) and construction of the stratified holdout split used by `main.ipynb`. [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1jfSTHSXvVIU8Fgc79sCz6F0nWiLvRRKd?usp=sharing)
- **`radar_viz.ipynb`** — qualitative comparison on failure cases, which motivates camera-radar fusion for future research. [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/15r72zsYgUAaW14znvPv247OyWqpX1Mc8?usp=sharing)
- **`downloading_pipeline.ipynb`** — a pipeline to download full MAN TruckScenes dataset. [![Open in Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/drive/1xy24GaGdtLqSBDDQQ_JeIlSPsW_S8L9d?usp=sharing)
- **`truckscenes_yolo/`** — derived dataset artefacts (the underlying images are not committed; only the small metadata/config files):
  - `metadata_train.csv`, `metadata_val.csv` — per-image scene-tag metadata produced by the YOLO export.
  - `truckscenes_4cam.yaml` — Ultralytics dataset config (paths + 12 detection classes).
  - `holdout_split.json` — list of scene tokens carved out of the official train split for stratified evaluation.
  - `runs/` — saved training run artefacts (`best.pt`, `results.csv`, per-condition JSONs).

The full image dataset and model weights live on Google Drive and are referenced by the notebooks via Colab Drive mounts.

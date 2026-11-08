<div align="center">

<!-- Banner: upload a picture named banner.png under Data › Readme pictures; it shows here. -->

# Data curation

**From a raw image pile to a training-ready dataset: quality, duplicates, embeddings on CPU / NVIDIA / Tenstorrent, label check, split and a before/after report.**

Fruit (FruitNet) and zebras (GZCD), same blocks.

![type](https://img.shields.io/badge/type-Data%20curation-blue) ![language](https://img.shields.io/badge/language-Python-3776AB) ![runs on](https://img.shields.io/badge/runs%20on-CPU%20%7C%20NVIDIA%20%7C%20Tenstorrent-6f42c1) [![made with](https://img.shields.io/badge/made%20with-EsaSim-0b7285)](https://esacode.com/)

<!-- More badges: ![licence](https://img.shields.io/badge/licence-MIT-green) — label, value and colour, written in the address. -->

</div>

## Flows

- **1 · Fruit: download and curate**: FruitNet (Good / Bad / Mixed quality of 6 fruits) downloaded once, checked, de-duplicated, labels checked with CLIP, split and reported.
- **2 · Zebras: read from Hugging Face and curate**: A sample of GZCD (Grevy's zebras, Kenya) read at an exact commit, checked, de-duplicated and sorted by CLIP into zebras, giraffes and empty frames.
- **3 · Same step, any accelerator**: The same images embedded on the CPU and on the NVIDIA GPU, images per second side by side (add a Tenstorrent machine for the third).

## What you need

- A machine with the EsaSim worker (Project > Compute); it runs on any machine, faster with: NVIDIA GPU, Tenstorrent.
- Keys to paste in the blocks (kept encrypted, never saved to GitHub): **Token (private datasets only)** of *GZCD on Hugging Face (300 photos)* (2 · Zebras: read from Hugging Face and curate); **Token (private datasets only)** of *GZCD on Hugging Face (300 photos)* (3 · Same step, any accelerator).
- Data it reads: [data.mendeley.com/datasets/b6fftwbr2v/3](https://data.mendeley.com/datasets/b6fftwbr2v/3), downloaded by *FruitNet (Mendeley Data)*; [imageomics/GZCD](https://huggingface.co/datasets/imageomics/GZCD) on the Hugging Face Hub, read by *GZCD on Hugging Face (300 photos)*.
- Python packages, installed by the worker the first time: `requests`, `numpy`, `pillow`, `torch`, `transformers`, `huggingface_hub`.

## How to run it

1. Under **Compute**, check that a machine is available for this project.
2. Open the flow under **Blueprint** and fill in the settings listed above.
3. Press **Run**, choose the machine, and follow the run on the flow's **View** page.
4. The files it made are under **Results**; they stay on the machine until you save or download them.

## What you get

- On the **View** page: *Review the flagged images* (1 · Fruit: download and curate), *Curation report* (2 · Zebras: read from Hugging Face and curate), *Removed, by reason* (2 · Zebras: read from Hugging Face and curate), *Every image removed, and why* (1 · Fruit: download and curate), *Embedding map: images that look alike sit together* (1 · Fruit: download and curate), *Embedding speed* (2 · Zebras: read from Hugging Face and curate), *Images per second* (2 · Zebras: read from Hugging Face and curate), *Review the photos (with what CLIP sees)* (2 · Zebras: read from Hugging Face and curate), *What CLIP sees in each photo* (2 · Zebras: read from Hugging Face and curate), *Embedding map* (2 · Zebras: read from Hugging Face and curate), *CPU speed* (3 · Same step, any accelerator), *GPU speed* (3 · Same step, any accelerator).

## Data and licences

- *FruitNet (Mendeley Data)*: Meshram, V., Patil, K. (2022). FruitNet: Indian fruits image dataset with quality for machine learning applications. Data in Brief 40, 107686. Mendeley Data, doi:10.17632/b6fftwbr2v.3 Licence: CC-BY-4.0.

<!-- esasim: files of the project -->

---

An [EsaSim](https://esacode.com/) project of the workspace Gianluca De Novi's workspace (Data curation).

### Blueprints in this repository

- [1 · Fruit: download and curate](blueprints/1-fruit-download-and-curate.json) · 15 blocks · version 5
- [2 · Zebras: read from Hugging Face and curate](blueprints/2-zebras-read-from-hugging-face-and-curate.json) · 14 blocks · version 1
- [3 · Same step, any accelerator](blueprints/3-same-step-any-accelerator.json) · 7 blocks

Keys pasted in blocks (secret settings) are not saved here. Datasets, results and the team stay in EsaSim.

# Data curation

From a raw image pile to a training-ready dataset: quality, duplicates, embeddings on CPU / NVIDIA / Tenstorrent, label check, split and a before/after report. Fruit (FruitNet) and zebras (GZCD), same blocks.

## Flows

- **1 · Fruit: download and curate**: FruitNet (Good / Bad / Mixed quality of 6 fruits) downloaded once, checked, de-duplicated, labels checked with CLIP, split and reported.
- **2 · Zebras: read from Hugging Face and curate**: A sample of GZCD (Grevy's zebras, Kenya) read at an exact commit, checked, de-duplicated and sorted by CLIP into zebras, giraffes and empty frames.
- **3 · Same step, any accelerator**: The same images embedded on the CPU and on the NVIDIA GPU, images per second side by side (add a Tenstorrent machine for the third).

## What you need

- A machine with the EsaSim worker (Project > Compute); it runs on any machine, faster with: NVIDIA GPU, Tenstorrent.
- Keys to paste in the blocks (kept encrypted, never saved to GitHub): **Token (private datasets only)** of *GZCD on Hugging Face (300 photos)* (2 · Zebras: read from Hugging Face and curate); **Token (private datasets only)** of *GZCD on Hugging Face (300 photos)* (3 · Same step, any accelerator).
- Data it reads: https://data.mendeley.com/datasets/b6fftwbr2v/3, downloaded by *FruitNet (Mendeley Data)*; [imageomics/GZCD](https://huggingface.co/datasets/imageomics/GZCD) on the Hugging Face Hub, read by *GZCD on Hugging Face (300 photos)*.
- Python packages, installed by the worker the first time: `requests`, `numpy`, `pillow`, `torch`, `transformers`, `huggingface_hub`.

## How to run it

1. Under **Compute**, check that a machine is available for this project.
2. Open the flow under **Blueprint** and fill in the settings listed above.
3. Press **Run**, choose the machine, and follow the run on the flow's **View** page.
4. The files it made are under **Results**; they stay on the machine until you save or download them.

<!-- esasim: files of the project -->

---

An [EsaSim](https://esacode.com/) project of the workspace Gianluca De Novi's workspace (Data curation).

### Blueprints in this repository

- [1 · Fruit: download and curate](blueprints/1-fruit-download-and-curate.json) · 13 blocks · version 3
- [2 · Zebras: read from Hugging Face and curate](blueprints/2-zebras-read-from-hugging-face-and-curate.json) · 12 blocks
- [3 · Same step, any accelerator](blueprints/3-same-step-any-accelerator.json) · 7 blocks

Keys pasted in blocks (secret settings) are not saved here. Datasets, results and the team stay in EsaSim.

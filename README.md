# Dental Dataset Catalog

A curated catalog of publicly available dental and oral healthcare datasets for AI research, focusing on dental imaging, computer vision, and vision-language models (VLMs).

This repository stores **metadata and links only**, not raw data. All datasets are listed in [`datasets.csv`](datasets.csv).

## Columns

| Column | Content |
|---|---|
| `name` | Official dataset name |
| `year` | Year of first public release |
| `data_type` | Every kind of data distributed (inputs, not labels): dimension + modality, plus text or tabular metadata, joined with ` + ` (e.g. `3D CBCT + text report`, `2D intraoral photo + tabular clinical metadata`) |
| `size` | Amount of each data type in `data_type` order, joined with ` + `; full breakdown (patients, splits, hidden test sets) in parentheses (e.g. `2000 scans + 5000 photos + 2403 reports (1000 patients)`). Units: `radiographs` (2D X-ray), `photos` (2D camera), `volumes` (CBCT), `scans` (intraoral scan meshes), `reports` (text) |
| `dataset_url` | Official download or landing page |
| `paper_url` | Paper describing the dataset (DOI preferred); `unknown` if none found |
| `access` | `open` / `registration` / `request` / `unavailable` / `unknown` |
| `license` | License as stated on the official dataset page |
| `verified` | Date and maintainer who checked the row against official sources (e.g. `2026-10-23 Yuhan`); empty = not yet checked |
| `notes` | `Annotations: ... \| Formats: ... \|` followed by metadata details, conflicts between sources, aliases, risks |

## Verification rules

- Every value must be traceable to the released files, the official dataset page, or the paper. Never guess.
- Write `unknown` when a value cannot be confirmed.
- When sources disagree, the released files take precedence, then the official dataset page, then the paper. Record every conflict in `notes`.
- In `notes`, mark facts that could not be checked against the files (e.g. download requires an account) as `not confirmed`.
- Fill in `verified` only after a person has checked the row.

## Catalog by modality

| Modality | Datasets |
|---|---|
| Panoramic X-ray | CariesXrays, OralXrays-9, DENTEX, Children's Dental Panoramic Radiographs (CDPR), OdontoAI Open Panoramic Radiographs, Dental Condition Detection - Romania, TED / TED3, Panoramic Radiographs with Periapical Lesions, STS-Tooth (STS-2D), Multimodal Dental Dataset (PhysioNet; acquired panoramic subset) |
| Periapical X-ray | DenPAR, PRAD, CariXray, Multimodal Dental Dataset (PhysioNet; generated periapical views) |
| Lateral cephalometric X-ray | Aariz / CEPHA29, PKU Cephalometric Dataset / Dental-Cepha |
| CBCT | ToothFairy, ToothFairy2, ToothFairy3, ToothFairy4, Pulpy3D, STS-Tooth (STS-3D), FDTooth, MMDental, Multimodal Dental Dataset (PhysioNet) |
| Intraoral scan | Teeth3DS, Teeth3DS+, TeethAlign3D, Pre-/Post-Orthodontic 3D Dental Dataset (Wang/Lei), Bite2Text |
| Intraoral photo | AlphaDent, SMART-OM, Oral Images Dataset, Annotated Oral Cavity Images (OCA-OPMD), FDTooth, Bite2Text |
| Image + text report / clinical record | ToothFairy4, Bite2Text, MMDental |
| Image / video + text QA benchmark | MMOral-OPG-Bench (panoramic X-ray), MMOral-Uni-Bench (multimodal imaging and video; gated file composition not confirmed) |
| Image + text training resource | MMOral-OPG-Training (panoramic-related; gated file composition not confirmed) |
| Image + tabular metadata | DenPAR, SMART-OM, AlphaDent (sex/age in filenames), Annotated Oral Cavity Images (OCA-OPMD), FDTooth, MMDental, Multimodal Dental Dataset (PhysioNet) |
| Oral histopathology | Histopathological Imaging Database for Oral Cancer Analysis, OSCC and Normal Tissue - Alexandria |
| Oral hyperspectral imaging | ODSI-DB (spectral images, embedded RGB previews and measurement metadata) |
| Text-only dental QA | dental_QA, Open-Domain-Oral-Disease-QA-Dataset |
| Corpus with unconfirmed modality | OralCorpus (gated repository; modalities and schema not publicly established) |

## Contributing

Open an issue to suggest a dataset or report a correction.

## Disclaimer

Licenses and access terms are summarized on a best-effort basis. The original authors' terms always take precedence; check them and cite the original paper before use.

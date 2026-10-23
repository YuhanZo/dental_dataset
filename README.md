# Dental Dataset Catalog

A curated catalog of publicly available dental and oral healthcare datasets for AI research, focusing on dental imaging, computer vision, and vision-language models (VLMs).

This repository stores **metadata and links only**, not raw data. All datasets are listed in [`datasets.csv`](datasets.csv).

## Columns

| Column | Content |
|---|---|
| `name` | Official dataset name |
| `year` | Year of first public release |
| `data_type` | Dimension + modality, joined with ` + ` for multiple (e.g. `3D CBCT + text report`) |
| `size` | Amount of data with units (e.g. `480 volumes`) |
| `dataset_url` | Official download or landing page |
| `paper_url` | Paper describing the dataset |
| `access` | `open` / `registration` / `request` / `unavailable` / `unknown` |
| `license` | License as stated on the official dataset page |
| `verified` | Date and maintainer who checked the row against official sources; empty = not yet checked |
| `notes` | Conflicts between sources, aliases, risks |

## Verification rules

- Every value must be traceable to the official dataset page or paper. Never guess.
- Write `unknown` when a value cannot be confirmed.
- When sources disagree, follow the official dataset page and record the conflict in `notes`.
- Fill in `verified` only after a person has checked the row.

## Catalog by modality

| Modality | Datasets |
|---|---|
| Panoramic X-ray | CariesXrays, OralXrays-9, DENTEX |
| Periapical X-ray | DenPAR, PRAD, CariXray |
| CBCT | ToothFairy, ToothFairy2, ToothFairy3, ToothFairy4 |
| Intraoral scan | Teeth3DS, Teeth3DS+, Bite2Text |
| Intraoral photo | AlphaDent, SMART-OM, Bite2Text |
| Image + text report | ToothFairy4, Bite2Text |

## Contributing

Open an issue to suggest a dataset or report a correction.

## Disclaimer

Licenses and access terms are summarized on a best-effort basis. The original authors' terms always take precedence; check them and cite the original paper before use.

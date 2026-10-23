# Metadata Schema

This document defines the columns of [`datasets.csv`](datasets.csv), the single source of truth for this catalog. Every row describes one dataset release.

## General rules

- **Never invent metadata.** Every value must come from the official paper or the official dataset source.
- **No empty cells.** If a value cannot be determined, write `unknown`. This distinguishes "checked but not found" from "not filled in".
- **Multi-value fields** use `; ` (semicolon + space) as the separator, e.g. `segmentation; detection`.
- **Controlled vocabularies** (listed below) must be used exactly as written, in lowercase. To add a new term, update this file in the same pull request.
- **CSV quoting** follows RFC 4180: wrap a value in double quotes if it contains a comma, double quote, or line break. Avoid commas where possible (e.g. write `1000 images`, not `1,000 images`).
- **Attribution:** link to the original source, not to mirrors or re-uploads. If only a mirror exists, say so in `notes`.

## Columns

| Column | Required | Format | Description |
|---|---|---|---|
| `id` | yes | lowercase slug `[a-z0-9_]+` | Permanent unique identifier. Never change or reuse it. Distinct releases get distinct ids (e.g. `toothfairy`, `toothfairy2`). |
| `name` | yes | free text | Official dataset name as given by its authors. |
| `year` | yes | `YYYY` or `unknown` | Year of the first public release, or of the describing paper if the release year is unclear. |
| `modality` | yes | vocabulary, multi-value | Imaging or data modality. See [modality](#modality). |
| `task` | yes | vocabulary, multi-value | Research tasks the dataset is designed for. See [task](#task). |
| `size` | yes | free text with units | Quantity with explicit units, e.g. `1000 images; 500 patients`. Do not give only a file size. |
| `annotation` | yes | vocabulary, multi-value | Types of labels provided. See [annotation](#annotation). |
| `paper_url` | yes | URL or `unknown` | Describing paper. Prefer a DOI link (`https://doi.org/...`). |
| `dataset_url` | yes | URL or `unknown` | Official landing or download page. |
| `source` | yes | vocabulary, multi-value | Platform(s) hosting the data. See [source](#source). |
| `access` | yes | vocabulary | How the data can be obtained. See [access](#access). |
| `license` | yes | SPDX identifier, free text, or `unknown` | Use an [SPDX identifier](https://spdx.org/licenses/) (e.g. `CC-BY-4.0`) when one applies; otherwise quote the license name and explain in `notes`. |
| `verified` | yes | vocabulary | Whether a maintainer has checked the entry against official sources. See [verified](#verified). |
| `last_checked` | yes | `YYYY-MM-DD` | Date the entry was last checked against official sources. |
| `notes` | no | free text | Caveats: conflicting numbers, broken links, mirror-only availability, licensing doubts, etc. May be empty. |

## Controlled vocabularies

### modality

| Value | Meaning |
|---|---|
| `panoramic` | Panoramic radiograph (OPG) |
| `intraoral_xray` | Periapical or bitewing radiograph |
| `cephalometric` | Cephalometric radiograph |
| `cbct` | Cone-beam CT or other 3D volumetric imaging |
| `intraoral_scan` | 3D intraoral scan / dental mesh |
| `clinical_photo` | Intraoral or extraoral clinical photograph |
| `histopathology` | Oral histopathology slide image |
| `text` | Paired text such as reports, captions, or QA (combine with an image modality for vision-language datasets) |
| `other` | Anything else; explain in `notes` |

### task

| Value | Meaning |
|---|---|
| `classification` | Image- or case-level classification |
| `detection` | Object detection (e.g. teeth, lesions) |
| `segmentation` | Semantic or instance segmentation |
| `landmark_detection` | Anatomical landmark localization |
| `numbering` | Tooth numbering / identification |
| `reconstruction` | 3D reconstruction or generation |
| `registration` | Image or mesh registration |
| `report_generation` | Generating radiology or clinical reports |
| `vqa` | Visual question answering |
| `captioning` | Image captioning |
| `retrieval` | Image-text retrieval |
| `instruction_tuning` | Instruction-following data for VLMs |
| `other` | Anything else; explain in `notes` |

### annotation

| Value | Meaning |
|---|---|
| `class_label` | Image- or case-level labels |
| `bounding_box` | Bounding boxes |
| `segmentation_mask` | Pixel/voxel masks |
| `keypoint` | Landmarks or keypoints |
| `mesh_label` | Per-vertex or per-face labels on 3D meshes |
| `text_report` | Free-text clinical or radiology reports |
| `caption` | Short image descriptions |
| `qa_pair` | Question-answer pairs |
| `none` | Unlabeled data |
| `other` | Anything else; explain in `notes` |

### source

`paper` (data only via the paper or its supplementary material), `github`, `huggingface`, `zenodo`, `kaggle`, `figshare`, `mendeley_data`, `physionet`, `institutional` (university or hospital site), `challenge` (e.g. a MICCAI challenge platform), `other`.

### access

| Value | Meaning |
|---|---|
| `open` | Direct download, no account needed |
| `registration` | Free account or click-through agreement required |
| `request` | Must apply to or email the authors; approval needed |
| `restricted` | Limited to specific institutions or uses (e.g. credentialed access) |
| `unavailable` | Described in a publication but not obtainable (dead link, "available on request" with no response, etc.) |
| `unknown` | Not yet determined |

### verified

| Value | Meaning |
|---|---|
| `yes` | All fields checked against the official paper and dataset page |
| `partial` | Some fields checked; details in `notes` |
| `no` | Not yet checked (e.g. copied from a survey paper) |

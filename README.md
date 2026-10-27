# Awesome Oral and Dental Open-source Datasets

A collection of **publicly accessible and request-accessible datasets for oral and dental AI**, organized by acquisition modality, clinical focus, and downstream task.

## Access and Resource

| Label | Meaning |
|---|---|
| **A — Public files** | A publisher or author page provides data files or download links. External-drive permissions and every archive have not been individually tested. Some entries retain their last documented access status, as noted below. |
| **B — Registration or application** | A documented account, credentialing, data-use agreement, gate, or application route exists. Files are not available through unrestricted anonymous download; approval and permitted use depend on the provider. |

This catalog consolidates **41 datasets, dataset families, benchmarks, and corpus repositories: 23 with A access and 18 with B access**. It includes established benchmarks and recent releases; it is not a popularity ranking. Earlier datasets remain included when relevant to recent research.

## Contents

- [Access and Resource Legend](#access-and-resource-legend)
- [Clinical Intraoral RGB Photography](#clinical-intraoral-rgb-photography)
- [2D Dental Radiography](#2D-dental-radiography)
  - [Panoramic Radiographs](#panoramic-radiographs)
  - [Periapical Radiographs](#periapical-radiographs)
  - [Lateral Cephalograms](#lateral-cephalograms)
- [3D CBCT](#3D-cbct)
- [3D Intraoral Surface Scans and Orthodontic Models](#3D-intraoral-surface-scans-and-orthodontic-models)
- [Paired Imaging, Reports, and Clinical Records](#paired-imaging-reports-and-clinical-records)
- [Vision-Language Benchmarks and Dental Language Corpora](#vision-language-benchmarks-and-dental-language-corpora)
  - [Vision-Language Evaluation Benchmarks](#vision-language-evaluation-benchmarks)
  - [Gated Training and Corpus Repositories](#gated-training-and-corpus-repositories)
  - [Text-Only Dental Question Answering](#text-only-dental-question-answering)
- [Oral Histopathology](#oral-histopathology)
- [Oral Hyperspectral Imaging](#oral-hyperspectral-imaging)
- [Task Index](#task-index)
- [Version and Evaluation Notes](#version-and-evaluation-notes)
- [Sources and Acknowledgments](#sources-and-acknowledgments)


## Clinical Intraoral RGB Photography

Real photographs acquired with smartphones, clinical cameras, or intraoral cameras. These capture visible tooth surfaces, gingiva, and oral mucosa.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **01 · AlphaDent** | 2025 | 1,320 photographs; approximately 295 patients; YOLO polygon annotations | Abrasion, fillings, crowns, and six location-based caries classes; lesion detection and instance segmentation | [Data](https://zenodo.org/records/16582489) · [Data card](https://huggingface.co/datasets/ZFTurbo/AlphaDent) · [Project](https://github.com/ZFTurbo/AlphaDent) | **A**; data card lists Apache-2.0 |
| **02 · Oral Images Dataset** | 2021, v2 | 323 original images: 165 benign and 158 malignant; augmented images supplied separately | Benign-versus-malignant oral lesion classification; pixel-level lesion masks not established | [Data](https://data.mendeley.com/datasets/mhjyrn35p4/2) | **A**; CC BY 4.0 |
| **03 · Annotated Oral Cavity Images / OCA–OPMD** | 2024; *Oral Oncology* | 3,000 smartphone white-light images from 714 patients; COCO polygons and clinical metadata | Healthy tissue, benign lesions, oral potentially malignant disorders, and oral cancer; classification and lesion/oral-region segmentation | [Paper](https://doi.org/10.1016/j.oraloncology.2024.106946) · [Data / Application](https://zenodo.org/records/10664056) | **B**; restricted Zenodo files; institutional account/email and research-purpose request |
| **04 · SMART-OM** | 2026; *Scientific Data* | 2,469 smartphone images from 331 participants across eight oral sites; VIA annotations and metadata with different annotation tiers | Normal mucosa, normal variants, potentially malignant disorders, and oral cancer; classification and region/lesion segmentation | [Paper](https://www.nature.com/articles/s41597-026-06954-5) · [Data](https://figshare.com/articles/dataset/SMART-OM_A_SMARTphone_based_expert_annotated_dataset_of_Oral_Mucosa_images/31341790) | **A**; CC BY 4.0 |
| **41 · SMART Intraoral Images Dataset — earlier SMITA release** | 2025; AIKosh / Zenodo v2 | AIKosh: 1,850 smartphone photographs from 235 patients across eight oral sites; Zenodo v2 describes 1,878 images from the same reported patient count; VIA regions and clinical metadata | Oral mucosal abnormality classification, OPMD/oral cancer screening, region annotation, and image triage; patient risk/history metadata | [Data / Login](https://aikosh.indiaai.gov.in/home/datasets/details/smart_intraoral_images_dataset_1.html) · [Zenodo Record](https://zenodo.org/records/16313710) | **B**; AIKosh marks the resource Restricted and Download Dataset redirects to login; license listed as NA; gated files and any further approval requirements not verified |

**Annotation distinctions:** AlphaDent's six caries classes describe lesion locations, not six severity levels. SMART-OM does not provide the same complete lesion-mask annotation for every image. Augmented copies in Oral Images should remain in the same split as their source image.

**SMART version relationship:** The 41 is the earlier SMART resource mentioned in the original CSV's SMART-OM notes. Its 235-patient release and the later 331-participant SMART-OM resource come from the same research group; patient/image overlap has not been established here. Keep the versions distinct without assuming independent cohorts. AIKosh and Zenodo also report different image totals for the earlier release, so preserve the acquired version and manifest rather than combining their counts.

## 2D Dental Radiography

X-ray projections are separate from clinical RGB photographs, even when distributed as three-channel JPEG or PNG files.

### Panoramic Radiographs

Panoramic radiographs, also called OPG, PaX, or DPR, depict both dental arches in a two-dimensional projection.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **05 · DENTEX / HierarchicalDet** | 2023 challenge | Annotation groups: 693 quadrant-labeled images; 634 quadrant-and-tooth-labeled images; 1,005 fully diagnostic images; 1,571 unlabeled images; hierarchical boxes | Caries, deep caries, periapical lesions, and impacted teeth; hierarchical detection, tooth numbering, and diagnosis | [Data](https://huggingface.co/datasets/LUNA0206/DENTEX) · [Project](https://dentex.grand-challenge.org/) · [Code](https://github.com/ibrahimethemhamamci/HierarchicalDet) | **A**; data card specifies CC BY-NC-SA; consult the record for the exact license version |
| **06 · CariesXrays** | AAAI 2024, AI for Social Impact Track | 6,000 panoramic images; 13,783 caries instances; VOC-format boxes | Caries detection, especially small lesions | [Paper](https://ojs.aaai.org/index.php/AAAI/article/view/30196) · [Data / Code](https://github.com/Binz-Chen/AAAI2024_CariesXrays) | **A**; repository links the full dataset through Google Drive; data license not verified |
| **07 · OralXrays-9** | CVPR 2025 | 12,688 images; 84,113 annotated instances; COCO bounding boxes | Nine categories covering pathology, tooth status, and treatment findings; multiclass detection and class-imbalance research | [Paper](https://openaccess.thecvf.com/content/CVPR2025/html/Chen_OralXrays-9_Towards_Hospital-Scale_Panoramic_X-ray_Anomaly_Detection_via_Personalized_Multi-Object_CVPR_2025_paper.html) · [Data / Code](https://github.com/XiaochengFang/CVPR2025_OralXrays-9) | **A**; author-provided drive download; data license not verified |
| **08 · Children's Dental Panoramic Radiographs / CDPR** | 2023; *Scientific Data* | 100 primary pediatric images plus 93 supplementary pediatric images; separately assembled adult resources contain 2,692 images; task-specific masks and JSON | Primary/mixed dentition; tooth-region segmentation and pediatric dental finding detection | [Paper / Data Records](https://www.nature.com/articles/s41597-023-02237-5) | **A**; Figshare download is linked from the paper; check each task package and its terms |
| **09 · OdontoAI Open Panoramic Radiographs** | 2022–2023 release documentation | 4,000 images overall; annotations for 2,000 are released to researchers; the other 2,000 support platform evaluation | Tooth instance segmentation and numbering in complex dentitions, including missing teeth, restorations, implants, and orthodontic appliances | [Data / Application](https://github.com/IvisionLab/OdontoAI-Open-Panoramic-Radiographs) | **B**; use the repository's dataset-request route; agreement governs use |
| **10 · Dental Condition Detection — Romania** | 2025 data record; associated 2024 study | 1,628 source images plus 180 external-validation images; JPEG and YOLO boxes | Fourteen dental findings, including caries, bone loss, periapical disease, impaction, root fragments/resorption, and treatment devices; detection and external validation | [Data](https://zenodo.org/records/15487430) | **A**; custom noncommercial research/education terms; redistribution restricted |
| **11 · TED / TED3** | Source used by MMOral, NeurIPS 2025 | Public WebDataset archives and image previews; the viewer displays approximately 10k training rows; inspect all splits for an exact image count | Panoramic tooth detection/segmentation; source radiographs for derived multimodal datasets | [Data](https://huggingface.co/datasets/Bryceee/TED) · [MMOral source description](https://arxiv.org/html/2509.09254v1#A2.SS1) | **A**; current HF card lists MIT, but source-paper license descriptions differ; verify the acquired version and original-image rights |
| **12 · Panoramic Radiographs with Periapical Lesions** | 2024, v3; Mendeley Data | Publisher reports 3,926 radiographs; original images, augmented images, and annotation folders; original/augmented breakdown requires inspection | Periapical lesion detection and localization; original radiograph source used by MMOral | [Data](https://data.mendeley.com/datasets/kx52tk2ddj/3) | **A**; CC BY 4.0 |

**Label distinctions:** OralXrays-9 includes apical periodontitis, caries, wisdom teeth, missing teeth, fillings, root canal fillings, implants, porcelain crowns, and ceramic bridges. These are not nine diseases. DENTEX annotation groups must not be summed into a unique-patient total without deduplication. Access to DENTEX also does not establish access to every additional label introduced by later papers such as DentalVLM.

### Periapical Radiographs

Periapical radiographs, also called PA, PR, or IOPA, provide localized X-ray views of teeth, roots, periapical tissue, and alveolar bone. Here, “intraoral” describes radiographic acquisition rather than RGB photography.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **13 · DenPAR** | 2024 data / 2025 *Scientific Data* | 1,000 IOPA images; tooth masks, bone-level lines, cementoenamel-junction and apex landmarks, boxes, and tooth metadata | Alveolar bone loss/level measurement; tooth segmentation, landmark localization, and detection | [Paper](https://www.nature.com/articles/s41597-025-05906-9) · [Data](https://zenodo.org/records/16645076) | **A**; CC BY 4.0 |
| **14 · PRAD / PRAD-10K** | MICCAI 2025 | Paper describes 10,000 images; documented application release provides 5,000 images with segmentation labels; nine semantic classes | Teeth, bone, pulp, root filling, crowns, fillings, implants, orthodontic appliances, and periapical lesions; semantic segmentation | [Data / Application / Code](https://github.com/nkicsl/PRAD) | **B**; institutional application with signature/stamp and use review; classification annotations were not part of the documented release |
| **15 · CariXray** | Associated 2026 *Machine Vision and Applications* study | Full and sample download links; YOLO annotations, COCO conversion, and cross-validation utilities; full sample count not verified | Periapical caries detection and instance segmentation | [Data / Code](https://github.com/trongnghia-184297/CariXray) | **A**; author-provided drive links; data license not verified |

**Name and version distinctions:** **CariesXrays** is the panoramic dataset in entry 06; **CariXray** is the periapical resource in entry 15. The PRAD repository now also mentions **PRAD++**; the counts above describe the previously audited PRAD-10K release, not an assumed complete PRAD++ release.

### Lateral Cephalograms

Lateral skull X-rays for craniofacial landmark localization, orthodontic measurements, and skeletal maturation assessment.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **16 · Aariz / CEPHA29** | 2023 preprint/challenge; full release documented in 2025 | 1,000 cephalograms from seven imaging devices; 29 landmarks and cervical vertebral maturation labels | Craniofacial landmark detection, cephalometric analysis, and maturation-stage classification | [Data](https://figshare.com/articles/dataset/Aariz_Cephalometric_Dataset/27986417) · [Project / Code](https://github.com/manwaarkhd/aariz) | **A**; CC BY 4.0 |
| **17 · PKU Cephalometric Dataset / Dental-Cepha** | Earlier benchmark; also used as an OralGPT-Omni source | Cephalograms and landmark-related data; the previously checked Figshare file is approximately 216 MB; exact package composition should be checked in the record | Cephalometric landmark localization and orthodontic anatomical analysis | [Data](https://figshare.com/articles/dataset/dental-cepha-dataset_zip/13265471?file=48632311) | **A**, last direct-download confirmation October 23, 2026; current automated recheck returned an access error; data terms not reverified |

## 3D CBCT

Cone-beam computed tomography provides volumetric information about teeth, roots, jaws, canals, and other maxillofacial structures. STS-Tooth also includes a separate two-dimensional panoramic component.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **18 · ToothFairy** | MICCAI 2023 challenge | 443 CBCT volumes: 153 densely annotated and 290 sparsely annotated; NumPy-format volume/label documentation | Mandibular canal/inferior alveolar nerve pathway segmentation; sparse and semi-supervised learning | [Data / Project](https://ditto.ing.unimore.it/toothfairy/) | **B**; university-portal registration; current download terms apply |
| **19 · ToothFairy2** | 2024 challenge / CVPR 2025 | 480 training volumes plus 50 hidden-test volumes; 42 foreground structures; NIfTI masks; 0.3-mm isotropic spacing | Tooth numbering and segmentation of teeth, jaws, nerve canals, sinuses, pharynx, and treatment structures | [Paper](https://openaccess.thecvf.com/content/CVPR2025/html/Bolelli_Segmenting_Maxillofacial_Structures_in_CBCT_Volumes_CVPR_2025_paper.html) · [Data](https://toothfairy2.grand-challenge.org/dataset/) · [Code / Labels](https://github.com/AImageLab-zip/ToothFairy2-Benchmark) | **B**; registration; CC BY-SA 4.0; hidden test material is not fully public |
| **20 · ToothFairy3** | 2025 challenge / MICCAI 2026 | 532 public volumes plus 50 hidden-test volumes; 77 classes by publisher convention; NIfTI volumes and labels | Fine maxillofacial segmentation, including pulp cavities and small incisive/lingual canals; scanner generalization | [Paper](https://papers.miccai.org/miccai-2026/1066-Paper0853.html) · [Data](https://ditto.ing.unimore.it/toothfairy3/) · [Code](https://github.com/zhiqin1998/U-Mamba2) | **B**; registration; verify current terms separately from ToothFairy2 |
| **21 · Pulpy3D** | MICCAI 2024 | Current portal: 423 volumes and 19 classes; earlier paper uses a 443-volume source cohort; pulp/instance/nerve labels | Pulp and root-canal segmentation, including joint modeling with the inferior alveolar nerve canal | [Data](https://ditto.ing.unimore.it/pulpy3d/) · [Code / Format](https://github.com/mahmoudgamal0/Pulpy3D) | **B**; portal registration; current release terms apply |
| **22 · STS-Tooth / STS-2D + STS-3D** | 2024 data / 2025 *Scientific Data* | 2D: 4,000 panoramic images, 900 masks; 3D documentation: 148,400 slice-level images and 8,800 annotated slices; NIfTI/ROI files | Tooth-region segmentation, semi-supervised learning, and age-related generalization across adult and pediatric data | [Paper](https://www.nature.com/articles/s41597-024-04306-9) · [Data](https://zenodo.org/records/10597292) | **A**; public multipart archive; paper states CC BY |
| **40 · Maxillo / IAN 3D Dataset** | 2022; CVPR 2022 | Publisher lists 91 densely annotated and 256 sparsely annotated CBCT volumes, totaling 347; NumPy volumes with sparse paths and dense-annotation resources | Inferior alveolar nerve/canal localization and 3D segmentation; sparse-to-dense label propagation and reproduction of historical baselines | [Paper](https://doi.org/10.1109/CVPR52688.2022.02046) · [Data](https://ditto.ing.unimore.it/maxillo/) · [Code](https://github.com/AImageLab-zip/alveolar_canal) | **B**; official page requires an account; explicitly marked outdated and superseded by ToothFairy; data-specific license not verified |

**Cohort overlap:** ToothFairy, ToothFairy2, ToothFairy3, and Pulpy3D share source cases or annotations. ToothFairy3 documents 480 scans inherited from ToothFairy2 and 52 additional public scans from another scanner. For STS-Tooth, 148,400 is a slice-level count, not the number of patients or CBCT volumes; the paper describes an original CBCT cohort of 422 patients. The 2D and 3D components should not be assumed to be completely paired.

**Historical predecessor:** Maxillo is the earlier release extended by ToothFairy, not an independent external-validation cohort. 

## 3D Intraoral Surface Scans and Orthodontic Models

Three-dimensional surface geometry, usually OBJ/STL meshes or derived point clouds. Surface scans show crowns and gingiva; they do not directly image internal roots or alveolar bone.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **23 · Teeth3DS / 3DTeethSeg / Teeth3DS+ family** | 2022 original; 2023 challenge; later landmark extension | 1,800 upper/lower scans from 900 patients; OBJ meshes and per-vertex instance/FDI JSON; additional landmark resources depend on version | Tooth/gingiva segmentation, tooth numbering, landmark localization, and 2D–3D representation learning | [Data](https://osf.io/xctdy/) · [Project / Tools](https://github.com/abenhamadou/3DTeethSeg_MICCAI_Challenges) · [Landmark Extension](https://crns-smartvision.github.io/teeth3ds/) | **A**; original data: CC BY-NC-ND 4.0; repository code: MIT; check extension-specific terms |
| **24 · TeethAlign3D** | ICCV 2025 | 837 cases; individual tooth STL geometry and target transformations | Orthodontic tooth alignment, six-degree-of-freedom pose prediction, occlusion, and collision-aware arrangement | [Project](https://californiachen.github.io/datasets/TeethAlign3D) · [Data / Application](https://zenodo.org/records/15834700) | **B**; restricted request and noncommercial-use conditions |
| **25 · Pre-/Post-Orthodontic 3D Dental Dataset — Wang/Lei** | 2024; *Scientific Data* | 1,060 paired models from 435 patients; 200 pairs with landmarks; upper/lower STL and tooth labels | Before/after orthodontic alignment, malocclusion analysis, segmentation, numbering, and landmark localization | [Paper](https://www.nature.com/articles/s41597-024-04138-7) · [Data](https://zenodo.org/records/11392406) · [Agreement](https://github.com/lcshhh/TADPM/blob/main/Data-Use-Agreement.pdf) | **B**; signed data-use agreement and author review with affiliation/research purpose |

## Paired Imaging, Reports, and Clinical Records

Resources with documented combinations of imaging, expert reports, clinical records, or other imaging modalities. The downloadable subset may be smaller than the paper's complete cohort.

| Dataset | Release / Reference | Modalities, Scale, and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **26 · FDTooth** | 2025, v1.0.0 | Clinical intraoral RGB photographs and corresponding CBCT; 241 patients; 1,800 annotated photographs; JPEG/DICOM | Alveolar bone fenestration, dehiscence, and normal anatomy; photo-based screening and multimodal learning | [Data / Documentation](https://physionet.org/content/fdtooth/1.0.0/) · [DOI](https://doi.org/10.13026/v9xk-dy61) | **B**; PhysioNet credentialing, required training, and data-use agreement; Credentialed Health Data License 1.5 |
| **27 · Bite2Text** | ECCV 2026 | Paper: 1,000 patients, 2,000 IOS scans, 5,000 RGB photographs, and 2,403 clinical reports; Italian reports and English translations | IOS/photo-to-report generation; multimodal dental description and structured assessment | [Paper](https://unimore.unifind.cineca.it/resource/item/548900?language=en-US) · [Data](https://ditto.ing.unimore.it/bite2text/) · [Code](https://github.com/AImageLab-zip/IOS-Report) · [Annotation Platform](https://github.com/AImageLab-zip/Yggdrasil) | **B**; account required; portal lists scans, photographs, and reports; hidden test set; paper totals are not confirmed downloadable totals |
| **28 · ToothFairy4** | MICCAI 2026 | CBCT with Italian/English reports and structured findings; paper version: 529 volumes and 893 reports; current portal describes an expanded release | Three-dimensional report generation and evaluation of findings, anatomical locations, and attributes | [Paper](https://papers.miccai.org/miccai-2026/0731-Paper0618.html) · [Data](https://ditto.ing.unimore.it/toothfairy4/) · [Code / Report Labels](https://github.com/AImageLab-zip/CBCT-Report) | **B**; registration; hidden evaluation material; reconcile current case manifest with paper counts |
| **29 · MMDental** | 2025; *Scientific Data* | 660 patients: 403 with paired CBCT/records and 257 with records only; 2,125 records; NIfTI and structured CSV | Image–text alignment, case retrieval, record/report generation, and diagnosis-related multimodal modeling | [Paper](https://www.nature.com/articles/s41597-025-05398-7) · [Data DOI](https://doi.org/10.6084/m9.figshare.28505276) · [Author-Shared Data](https://figshare.com/s/e7061e6459a73ddeaca4) | **A**, publisher-declared public Figshare deposit; repository download not retested; paper states CC BY |
| **30 · Multimodal Dental Dataset — PhysioNet** | 2023 first release; 2024 v1.1 | 169 patients; 329 CBCT scans, 8 acquired panoramic radiographs, and 16,203 generated periapical views | Cross-modality modeling, anatomical analysis, and learning across volumetric data and derived projections | [Data / Documentation](https://physionet.org/content/multimodal-dental-dataset/1.1.0/) | **B**; credentialing, training, agreement, and contributor review; Contributor Review Health Data License 1.5 |

## Vision-Language Benchmarks and Dental Language Corpora

### Vision-Language Evaluation Benchmarks

| Dataset | Release / Reference | Modalities, Scale, and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **31 · MMOral-OPG-Bench** | NeurIPS 2025, Datasets and Benchmarks Track | 100 panoramic images; released version has 491 closed-ended and 578 open-ended questions, totaling 1,069; TSV files with embedded image data | Panoramic dental visual question answering and multimodal-model evaluation | [Paper](https://proceedings.neurips.cc/paper_files/paper/2025/hash/3797b3a3c939156757857cf1b9afde3c-Abstract-Datasets_and_Benchmarks_Track.html) · [Data](https://huggingface.co/datasets/OralGPT/MMOral-OPG-Bench) · [Code](https://github.com/isjinghao/OralGPT) | **A**; two public TSV files; HF card lists MIT |
| **32 · MMOral-Uni-Bench** | OralGPT-Omni, CVPR 2026 | Paper: 2,809 open-ended QA items covering five modalities and five tasks; gated repository displays approximately 568 MB | Multimodal dental understanding and general-purpose dental VLM evaluation | [Paper](https://openaccess.thecvf.com/content/CVPR2026/html/Hao_OralGPT-Omni_A_Versatile_Dental_Multimodal_Large_Language_Model_CVPR_2026_paper.html) · [Data](https://huggingface.co/datasets/OralGPT/MMOral-Uni-Bench) · [Code](https://github.com/isjinghao/OralGPT/tree/main/MMOral-Omni) | **B**; HF login, account-information sharing, and acceptance of conditions; complete file/item coverage not verified anonymously |

### Gated Training and Corpus Repositories

These repositories have verifiable access gates. A gate and a displayed storage size do not establish complete correspondence with a paper's training data.

| Dataset | Release / Reference | Modalities, Scale, and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **33 · MMOral-OPG-Training** | OralGPT official repository; available by the 2026 audit | Panoramic-related training repository; approximately 18.7 GB displayed; exact sample count and file schema not anonymously verified | Training resource for dental image–text modeling; detailed task composition requires the gated files/documentation | [Data](https://huggingface.co/datasets/OralGPT/MMOral-OPG-Training) · [Project](https://github.com/isjinghao/OralGPT) | **B**; HF login and acceptance of access conditions; not evidence that all Omni modalities or training stages are released |
| **34 · OralCorpus** | OralGPT official repository; available by the 2026 audit | Approximately 330 GB displayed; no public data card establishing modality composition, schema, or record count | Official corpus access lead; intended tasks and correspondence to specific training stages remain undocumented publicly | [Data](https://huggingface.co/datasets/OralGPT/OralCorpus) | **B**; HF login and acceptance of conditions; access route verified, contents/completeness unverified |

### Text-Only Dental Question Answering

These resources contain language data rather than paired dental images and questions.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **35 · dental_QA** | Source listed in OralGPT-Omni supplementary material | Dental forum text/QA; exact sample count and release metadata not established in this catalog | Dental language modeling and QA data processing; not an image-grounded reasoning-chain dataset | [Data](https://huggingface.co/datasets/jonathankang/dental_QA) · [Omni Source Table](https://arxiv.org/html/2511.22055v1) | **A**, public page/preview documented October 23, 2026; current automated recheck failed; license not reverified |
| **36 · Open-Domain-Oral-Disease-QA-Dataset** | Public HF dataset record | 672 rows in the displayed split; English questions, model answers, disease categories, validity labels, and related metadata | Oral-disease QA evaluation and response-correctness assessment | [Data](https://huggingface.co/datasets/Lines/Open-Domain-Oral-Disease-QA-Dataset) | **A**; HF card lists MIT; answers include entries labeled incorrect |

**Label quality:** Do not treat every model response in entry 36 as a correct clinical reference answer. Its validity labels and evaluation design must be considered before using it for supervised fine-tuning.

## Oral Histopathology

Microscope-acquired hematoxylin-and-eosin (H&E) tissue images. These are not oral-camera photographs, and image-field counts are not patient counts.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **37 · Histopathological Imaging Database for Oral Cancer Analysis** | 2023, v2 | 1,224 H&E image fields from 230 patients; 100×/400× imaging; normal and cancer labels | Normal oral epithelium versus oral squamous cell carcinoma (OSCC) classification | [Data](https://data.mendeley.com/datasets/ftmp4cvtmb/2) | **A**; CC BY 4.0 |
| **38 · OSCC and Normal Tissue — Alexandria** | 2026 | 1,714 image fields from 115 cases: 49 OSCC and 66 normal; H&E at 100×/400× | Oral cancer classification and case-level pathology modeling; case grading information does not imply complete image-level grading labels | [Paper](https://www.melba-journal.org/papers/2026%3A037.html) · [Data](https://data.mendeley.com/datasets/7m9zkcx539/1) | **A**; CC BY 4.0 |

## Oral Hyperspectral Imaging

Spectral measurements contain multiple wavelength bands. An RGB preview does not make the underlying data an ordinary RGB photograph dataset.

| Dataset | Release / Reference | Scale and Annotation | Clinical Focus and Downstream Tasks | Resources | Access / Data Terms |
|---|---|---|---|---|---|
| **39 · ODSI-DB** | 2020; *Applied Sciences* | 316 oral reflectance hyperspectral images; multiband TIFF data with RGB previews and tissue-region information | Tooth, gingival, and mucosal tissue analysis; spectral representation learning and tissue segmentation | [Paper](https://www.mdpi.com/2076-3417/10/20/7246) · [Data / Project](https://sites.uef.fi/spectral/databases-software/odsi-db/) | **A**; university-hosted release/mirror links; CC BY-NC-SA 4.0 |

## Task Index

This index is a navigation aid, not a performance or popularity ranking. Task suitability still depends on the actual annotations in the downloaded version.

| Research Direction | Relevant Entries | Main Supervision / Evidence |
|---|---|---|
| Caries and radiographic finding detection | 01, 05–08, 10, 12, 15 | Lesion polygons/boxes or task-specific finding labels; photograph and X-ray modalities differ |
| Oral mucosal lesion and oral cancer analysis | 02–04, 37–38, 41 | Clinical photographs versus microscopic H&E tissue images; earlier SMART and SMART-OM may share source cases |
| Tooth segmentation and numbering | 05, 09, 11, 13–14, 19–23 | Hierarchical boxes, pixel/voxel masks, or surface-vertex instance/FDI labels |
| Periodontal bone assessment | 10, 13, 26 | Radiographic findings, bone-level/landmark annotations, or RGB–CBCT evidence of fenestration/dehiscence |
| Craniofacial landmarks and skeletal maturation | 16–17 | Cephalometric coordinates; maturation labels specifically documented for Aariz |
| Fine CBCT anatomy, pulp, and canal segmentation | 18–21, 40 | Dense/sparse volume labels, small canals, and pulp structures; Maxillo is a predecessor of ToothFairy |
| Orthodontic surface geometry and alignment | 23–25 | Surface instances, landmarks, target poses, and pre-/post-treatment pairs |
| Report generation and image–text retrieval | 27–29 | Expert reports or clinical records paired with IOS, photographs, or CBCT |
| Dental VLM evaluation | 31–32 | Image-grounded benchmark questions and reference answers |
| Dental language and multimodal training resources | 33, 35–36 | Gated training files or text QA; entry 36 contains correctness-labeled model responses |
| Cross-modality and spectral representation learning | 22, 26, 30, 39 | Multiple imaging types, paired acquisitions, generated views, or wavelength-resolved measurements |

## Version and Evaluation Notes

1. **Public access is not full-paper reproducibility.** Paper totals, downloadable training subsets, hidden test inputs, hidden answers, extra annotations, and derived instruction data may have different release conditions. PRAD, Bite2Text, ToothFairy, and MMOral illustrate these distinctions.
2. **Preserve patient-level separation.** Keep photographs, patches, augmented copies, upper/lower scans, repeated records, slices, and generated views from the same patient or source acquisition in the same split where identifiers allow. Otherwise, apparently strong results can reflect overlap between training and evaluation.
3. **Check source-family overlap.** Teeth3DS aliases are grouped here. ToothFairy derivatives inherit cases, starting with the earlier Maxillo release. The earlier SMART release and SMART-OM should not be presumed independent. DENTEX and HierarchicalDet refer to the same source data. TED and the periapical-lesion panoramic dataset are raw sources for MMOral-derived resources; reusing them can overlap with a benchmark's source images.
4. **Use the annotation definition, not the filename extension.** Pixel masks, lesion boxes, semantic labels, tooth identities, clinical diagnoses, reports, and target transformations supervise different tasks. IOS meshes do not reveal internal tooth roots, and X-rays saved as RGB files remain X-rays.
5. **Record the acquired version.** ToothFairy4 has expanded beyond its paper cohort; Pulpy3D has different paper/portal counts; PRAD++ is distinct from the documented PRAD-10K subset. Record repository revision, file manifest, split, and license when building an experiment.
6. **Inspect data-specific terms.** Noncommercial licenses, no-derivatives conditions, redistribution restrictions, credentialing, and signed agreements vary across entries. A permissive model or code license does not override the dataset's terms.
7. **Read availability at its evidence level.** This document consolidates the earlier guide and later checks; it is not a fresh end-to-end download audit of all 41 entries. No controlled-access applications were submitted and no complete archives were downloaded for this catalog. PKU and dental_QA retain the October 23 public-access finding after unsuccessful automated rechecks; MMDental's public deposit is supported by its publisher's Data Records statement. OralCorpus is listed only as a gated repository with limited public metadata.
8. **Pre-update CSV coverage check, October, 2026.** All 15 original dataset rows were already represented, including Teeth3DS+ within entry 23's family. The original ToothFairy and SMART-OM notes additionally named Maxillo and the earlier SMART release. Their official account/download routes were checked and they are now entries 40 and 41. References to PRAD++, MM-PRAD, and deprecated DNS/UFBA variants were not treated as newly verified A/B releases.

## Sources and Acknowledgments

**Local source material:** [Original dental dataset guide](<C:/US/DentalPaper/Oral_Dental公开数据集分类与选型指南.md>), [Consolidated dental papers and datasets](<C:/US/DentalPaper/2023-2026_Oral_Dental论文与数据集总表.md>), [October 23 data-availability audit](<C:/US/DentalPaper/论文精读/Omni与ECCV2026_数据公开和下载核查_2026-10-23.md>), and the original 15 rows and notes preserved in [Dental dataset metadata](<C:/US/DentalPaper/dental_dataset/datasets.csv>). The 31 unambiguously A/B entries in the original 34-entry guide are retained; eight resources from later/related notes and two historical releases identified in the CSV notes are included. Main-table identifiers are local to this catalog; existing identifiers were preserved when entries 40 and 41 were added.

This document **only** adopts their category-based navigation, concise resource tables, and paper/data/code links, with an explicit distinction between public files and registration/application access.

Dataset facts and access conditions are attributed to the linked primary publications, release records, and author/project pages. Please cite the original dataset publication and follow the terms of the acquired version.

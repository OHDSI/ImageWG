# OHDSI 2026 Global Symposium Tutorial (Imaging WG)

### Bringing FAIR to Imaging Research with the Medical Imaging OMOP Extension

| | |
|---|---|
| **Date** | Monday, October 20, 2026 |
| **Time** | 08:00–12:00 |
| **Environment** | Google Colab (no local install) |
| **Slide** | [TBD] |



## Repository structure

```
OHDSI2026-Tutorial/
├── README.md
└── notebooks/
    ├── 01_DICOM_to_MI-CDM_ETL.ipynb      # Hands-on I
    └── 02_Image_Derived_Features.ipynb   # Hands-on II
```

## Notebooks

Both notebooks follow the ETL of the ImageWG [Medical Imaging Extension Conventions](https://github.com/OHDSI/ImageWG/wiki/Medical-Imaging-Extension-Conventions) [1]. Each section is labelled with the wiki flow-chart step it implements.

| Notebook | Wiki steps | What you build | Runtime | Open |
|---|---|---|---|---|
| **01. From DICOM archive to MI-CDM** | 1–6 | Index 100 Chest X-ray files, extract and characterize DICOM headers, load the DICOM vocabulary, and ETL into `PERSON`, `PROCEDURE_OCCURRENCE`, `IMAGE_OCCURRENCE` and `MEASUREMENT` (each DICOM attribute row linked to its series by `measurement_event_id`); data-quality checks, an imaging search query (with a *your turn* cell for your own criteria), and save the database and the DICOM files to Google Drive for notebook 02 | CPU is fine (~5 min incl. download) | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dr-you-group/OHDSI2026-Tutorial/blob/main/notebooks/01_DICOM_to_MI-CDM_ETL.ipynb) |
| **02. Image-derived features with provenance** | 7–11 | Load the notebook 01 output from Google Drive, run TorchXRayVision classification (3 imaging findings) and segmentation (cardiothoracic ratio and two widths in mm), map the features to standard and custom concepts, load the values into `MEASUREMENT` and link them through `IMAGE_FEATURE` (findings, `alg_system`, `alg_datetime`), trace values back to their images and DICOM attributes, run data-quality checks, and download the OMOP CDM + MI-CDM database | T4 GPU recommended | [![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/dr-you-group/OHDSI2026-Tutorial/blob/main/notebooks/02_Image_Derived_Features.ipynb) |

## Running in Google Colab

1. **Open a notebook** — any of these works:
   - Click an **Open in Colab** badge above.
   - In Colab: **File → Open notebook → GitHub**, enter `dr-you-group/OHDSI2026-Tutorial`, and pick the notebook.
   - Download the `.ipynb` and use **File → Upload notebook**.
2. **Sign in** with a Google account and choose **File → Save a copy in Drive** to keep your changes.
3. **Choose a runtime** — for notebook 02: **Runtime → Change runtime type → T4 GPU**.
4. **Run all** — **Runtime → Run all**. Notebook 01 downloads the data and the vocabulary itself.
5. **Notebook 01 → notebook 02** — the last section of notebook 01 saves the database and the DICOM files to your Google Drive (`MyDrive/micdm_tutorial/`), and the *Setup* section of notebook 02 loads them. If they are not there, the catch-up cell rebuilds the notebook 01 database automatically, so you can start with notebook 02 if you fell behind.
6. **Take the database home** — the last code cell of notebook 02 downloads `omop_micdm.db` (notebooks 01 + 02 in one SQLite file, without the ETL work tables). Open it in [SQLite Viewer](https://sqliteviewer.app/); the browser may name the file `omop_micdm (2).db`.

## Resources

| | |
|---|---|
| **Format** | Follow the ImageWG wiki ETL flow chart step by step [1] |
| **Data** | RSNA Pneumonia Detection Challenge 2018 — a 100-file CR subset fetched in Colab [2] |
| **Model** | TorchXRayVision [3]: DenseNet-121 (classification), PSPNet (chest segmentation) |
| **ETL Reference** | [DICOM2OMOP](https://github.com/paulnagy/DICOM2OMOP): DICOM vocabulary staging files and demonstration notebooks [4] |

## References

1. Medical Imaging Extension Conventions. (n.d.). GitHub. Retrieved September 29, 2026, from https://github.com/OHDSI/ImageWG/wiki/Medical-Imaging-Extension-Conventions
2. Anouk Stein, MD, Carol Wu, Chris Carr, George Shih, Jamie Dulkowski, kalpathy, Leon Chen, Luciano Prevedello, Marc Kohli, MD, Mark McDonald, Peter, Phil Culliton, Safwan Halabi MD, and Tian Xia. RSNA Pneumonia Detection Challenge. https://www.kaggle.com/competitions/rsna-pneumonia-detection-challenge, 2018. Kaggle.
3. Cohen, J. P., Viviano, J. D., Bertin, P., Morrison, P., Torabian, P., Guarrera, M., Lungren, M. P., Chaudhari, A., Brooks, R., Hashir, M., & Bertrand, H. (2021). TorchXRayVision: A library of chest X-ray datasets and models (arXiv:2111.00595). arXiv. https://doi.org/10.48550/arXiv.2111.00595
4. Nagy, P. (n.d.). DICOM2OMOP. GitHub. Retrieved October 16, 2026, from https://github.com/paulnagy/DICOM2OMOP

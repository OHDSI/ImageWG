# OHDSI Medical Imaging Working Group

> Extending the OMOP Common Data Model to integrate medical imaging data for reproducible, multimodal observational research.

The group, formed in 2021, brings together imaging informaticians, clinical researchers, and observational health scientists. We developed the **Medical Imaging Common Data Model (MI-CDM)**, a structural extension of OMOP CDM introducing two new tables (`Image_occurrence`, `Image_feature`) to represent imaging studies, acquisition metadata, and derived features while preserving linkage to clinical data.

---

## Quick Links

| Resource | Description |
|---|---|
| [Website](https://ohdsi.github.io/ImageWG/) | Our web page |
| [GitHub Repository](https://github.com/OHDSI/ImageWG/) | Source code, issues, and proposals |
| [2026 OKR](https://www.ohdsi.org/wp-content/uploads/2026/03/Imaging-2026.pdf) | Working group objectives and key results |
| [References](https://github.com/OHDSI/ImageWG/wiki/References-to-relevant-journal-articles) | Relevant journal articles |
| [DICOM2OMOP Demo](https://github.com/paulnagy/DICOM2OMOP) | Implementation demonstration |

---

## Implementation & Contribution (Issues)

We use GitHub Issues as a central space for defining implementation conventions, discussing edge cases, and sharing practical guidance for MI-CDM.

Issues are structured following a Themis-style approach, serving as a lightweight implementation guide that includes:
- ETL conventions for mapping imaging data into OMOP CDM
- Rules for handling real-world variability in DICOM metadata
- Frequently encountered issues and their recommended resolutions
- Example-driven discussions based on practical deployment scenarios

Rather than a static specification, this evolving collection of issues functions as a community-driven FAQ and rulebook, supporting consistent and reproducible implementation of MI-CDM across institutions.

---

## Join the Working Group

Meetings are held **every 2 weeks on Wednesdays** — alternating between **7 PM ET** and **7 AM ET**.

| Step | Action | Link |
|---|---|---|
| 1 | Sign up for an OHDSI MS Teams account | [Register here](https://forms.office.com/Pages/ResponsePage.aspx?id=lAAPoyCRq0q6TOVQkCOy1ZyG6Ud_r2tKuS0HcGnqiQZUQ05MOU9BSzEwOThZVjNQVVFGTDNZRENONiQlQCN0PWcu) |
| 2 | Join the Imaging channel (select "Image" in the form) | [Register here](https://forms.office.com/Pages/ResponsePage.aspx?id=lAAPoyCRq0q6TOVQkCOy1ZyG6Ud_r2tKuS0HcGnqiQZUOVJFUzBFWE1aSVlLN0ozR01MUVQ4T0RGNyQlQCN0PWcu) |

---

## About MI-CDM

Building on the Radiology Common Data Model (R-CDM) by Park et al. (2022), MI-CDM expands imaging data representation beyond radiology to support diverse imaging domains including brain MRI (ADNI), CT lung nodules, and more. It incorporates DICOM standard vocabulary into OMOP and is evaluating additional terminologies such as RadLex.

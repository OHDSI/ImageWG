# Medical Imaging Working Group

The OHDSI Medical Imaging Working Group, formed in 2021, brings together imaging informaticians, clinical researchers, and observational health scientists to extend the OMOP Common Data Model (CDM) for medical imaging research. The group aims to bridge the gap between electronic health record (EHR) data and medical imaging data, enabling integrated and reproducible multimodal observational studies.

To support this, the group developed the Medical Imaging Common Data Model (MI-CDM), a structural extension of the OMOP CDM that introduces two new tables—Image_occurrence and Image_feature—to represent imaging studies, acquisition metadata, and derived imaging features, while preserving provenance and linkage to clinical data. This work builds upon earlier efforts such as the Radiology Common Data Model (R-CDM), expanding beyond radiology to support diverse imaging domains.

Building on this structural foundation, the group has explored semantic standardization through incorporation of the DICOM standard into the OMOP vocabulary, enabling consistent representation of imaging acquisition parameters and metadata. Additional imaging-specific terminologies, such as RadLex, are under consideration for future integration.

The development has been guided by key clinical use cases, including longitudinal tracking of imaging findings such as lung nodules. Important attributes include CT acquisition parameters and imaging phenotypes such as nodule diameter, location, density, and shape. A prototype implementation based on CT lung nodules was developed and demonstrated at the 2023 Society of Imaging Informatics in Medicine (SIIM) Hackathon.

More recent efforts have extended these concepts to pilot implementations using real-world and research datasets, including brain MRI data (e.g., ADNI), demonstrating the feasibility of integrating imaging metadata with clinical data for scalable multimodal research within the OMOP framework.

Please check our [Page](https://ohdsi.github.io/ImageWG/index.html) for more information.
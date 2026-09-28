# Rulex Flow for Unsupervised Quality-of-Life Clustering in Autoimmune Liver Diseases

This repository contains the Rulex flow used in the study:
_"Machine Learning Identifies Quality-of-Life Clusters in Autoimmune Liver Disease."_

Further methodological and application details can be found in the published paper, which presents the results obtained from a cohort of patients recruited across 12 international centers.

## Overview

The flow implements the full analytical pipeline used to identify and characterize quality-of-life (QoL)–based phenotypes among patients with autoimmune liver diseases (AILDs).
It includes the following main stages:

### Data Import

The data used in this study originate from two previously published investigations [1], [2].
These datasets are available for research purposes.
For access and further information, please contact:

- Elisa Merelli – e.merelli1@campus.unimib.it
- Alessio Gerussi – alessio.gerussi@unimib.it

### Data Preparation and Cleaning

Data from multiple sources and questionnaires are harmonized, checked for consistency, and preprocessed to ensure suitability for unsupervised learning.

### Initial Clustering

K-means clustering is performed on the responses from nine validated HRQoL questionnaires.
The optimal number of clusters is determined through internal validation metrics and stability assessment.

### Cluster Aggregation

Similar clusters are merged based on multidimensional similarity criteria, reducing their number and improving interpretability.

### Cluster Analysis

Each cluster is characterized from demographic, clinical, and QoL perspectives to reveal distinct patient profiles that transcend traditional diagnostic categories.

### Rule Extraction

A set of interpretable rules (ruleset) is automatically derived, describing the key QoL dimensions defining each cluster and supporting phenotype interpretation.

### Feature Ranking

Variables are ranked according to their contribution to cluster differentiation, highlighting the most influential HRQoL aspects.

## Repository Structure

- **`QoL_main.rfl`** — main Rulex flow implementing the full analytical pipeline described above.
- **`modules/`** — folder containing the six Rulex modules (subflows) invoked by the main flow:
  - `AdjustSmallClusters.rfl`
  - `AggregateClust.rfl`
  - `Clustering_Optimize_K.rfl`
  - `K_Fold.rfl`
  - `randlndexClust.rfl`
  - `reduceDimension.rfl`
- **`input_variables.pdf`** — list of the 121 HRQoL variables required to reproduce the clustering procedure (patient-level data cannot be shared; see *Data Import* above for access requests).
- **`QoL_pipeline.pdf`** — schematic representation of the pipeline and its main components.

## Platform and License

All analyses were performed using the Rulex Platform ([www.rulex.ai](https://www.rulex.ai)).

To reproduce the analyses, users can request a trial or academic license directly from Rulex.
For licensing and technical inquiries, please contact:

Damiano Verda – damiano.verda@rulex.ai

## References

[1] R. J. A. L. M. Snijders et al., "Health-related quality of life is impaired in people with autoimmune hepatitis: Results of a multicentre cross-sectional study within the European Reference Network", Hepatology, Feb. 2025, doi: 10.1097/HEP.0000000000001271.

[2] N. Uhlenbusch et al., "Improving quality of life in patients with rare autoimmune liver diseases by structured peer-delivered support (Q.RARE.LI): study protocol for a transnational effectiveness-implementation hybrid trial", BMC Psychiatry, vol. 23, no. 1, p. 193, Mar. 2023, doi: 10.1186/s12888-023-04669-0.

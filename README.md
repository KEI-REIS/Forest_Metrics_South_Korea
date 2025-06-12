# Forest Patch Metrics (South Korea)

This repository contains a spatial dataset of forest landscape metrics derived from land cover classification in South Korea. The data is stored in a GeoPackage file (`Forest_patch_metrics.gpkg`) and includes a set of spatial configuration and information-theoretic indices used to quantify forest structure, composition, and fragmentation.

## 🔍 Overview

The database includes the following classes of landscape metrics:

### 1. Spatial Configuration Metrics
- **Aggregation Index (AI)**: Measures spatial clustering by comparing observed adjacency to a theoretical maximum. Higher values indicate more cohesive forest patches.
- **Class Area (CA)**: Total area of forest patches in a given land cover class.
- **Total Core Area (TCA)**: Interior area of forest patches, excluding edge zones. Indicator of ecological stability.
- **Total Edge (TE)**: Total boundary length between forest patches and adjacent land cover types.

### 2. Information Theory–Based Metrics
- **Marginal Entropy (ENT or H(x))**: Quantifies the thematic diversity of land cover classes based on their distribution.
- **Relative Mutual Information (RMI)**: Normalized mutual information that reflects spatial dependence across land cover classes.

## 📦 File Contents

| File                        | Description                                     |
|-----------------------------|-------------------------------------------------|
| `Forest_patch_metrics.gpkg` | GeoPackage containing spatial forest metrics   |
| `.gitattributes`            | Git LFS configuration                          |

## 📐 Metric Definitions

| Metric | Abbreviation | Definition                                                                 | Unit     | Formula                                | Range         |
|--------|--------------|---------------------------------------------------------------------------|----------|----------------------------------------|---------------|
| Aggregation Index         | AI         | Degree of adjacency among similar patches                         | %        | AI = (g_ii / max_g_ii) × 100           | 0 ≤ AI ≤ 100  |
| Class Area                | CA         | Total area of patches in class *i*                                | km²      | CA = sum(AREA(patch_ij))              | CA > 0        |
| Total Core Area           | TCA        | Sum of core (non-edge) areas in class *i*                         | km²      | TCA = sum(a_ij_core) / 10,000         | TCA ≥ 0       |
| Total Edge                | TE         | Total edge length of class *i* with others                        | meters   | TE = sum(e_ik)                         | TE ≥ 0        |
| Marginal Entropy          | ENT or H(x)| Class diversity index                                             | bits     | H(x) = –∑p_i * log₂(p_i)               | ENT ≥ 0       |
| Relative Mutual Information | RMI or RelMutInf | Spatial dependence normalized by entropy       | unitless | RMI = I(x, y) / H(x)                   | 0 ≤ RMI ≤ 1   |

## 📍 Use Case

This dataset is intended for:
- Spatial ecological analysis
- Landscape fragmentation studies
- Environmental impact assessments
- Habitat suitability modeling

## 📝 Citation

If you use this dataset in your research, please cite it as:

> KEI-REIS (2025). *Forest Patch Metrics (South Korea)*. GitHub Repository: [https://github.com/KEI-REIS/Forest_Metrics_South_Korea](https://github.com/KEI-REIS/Forest_Metrics_South_Korea)

## 📌 Notes

- All metrics follow standard landscape ecology conventions.
- Data are derived from South Korea’s national land cover classification datasets.

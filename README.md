# DarkJargon-SOK

Artifact for the paper **“SoK: Ten Years of Dark Jargon Detection and Interpretation from an NLP Perspective.”**

This repository contains the literature corpus, screening records, taxonomies, and derived summaries used in the paper. It does **not** redistribute the full text of the surveyed publications or restricted dark-web datasets.

## Artifact overview
The systematic search covered six scholarly databases:
- ACM Digital Library
- ACL Anthology
- IEEE Xplore
- ScienceDirect
- SpringerLink
- DBLP

No publication-date restriction was applied. The 2015–2025 period in the paper title is the publication span observed in the final corpus.

The database search produced 865 records, of which 847 remained after deduplication. Screening retained 15 contributions. Backward and forward snowballing screened 41 additional unique candidates and retained 9. The final corpus therefore contains **24 contributions: 16 approach papers and 8 resource contributions**.

> **Camera-ready note:** Add the exact date or date range on which each database was searched: **26.11.2025** - **21.04.2026** (updated).

## Repository contents

### Primary corpus files
| File | Description |
|---|---|
| `1. core_nlppapers-darkjargon.csv` | Bibliographic records for the 16 papers that propose or evaluate dark-jargon approaches. |
| `2. datasets_resources.csv` | Bibliographic records for the 8 dataset and lexical-resource contributions. |
| `paperretrieval_fullresults.CSV` | Records collected from the initial database searches before final screening. |
| `paperretrieval_fullsearch_dedup.CSV` | Deduplicated database-search records with screening information. |
| `paperretrieval_snowballing_dedup.csv` | Deduplicated records considered during backward and forward snowballing. |

### Analysis and taxonomy files
| File | Description |
|---|---|
| `Approach_taxonomy.csv` | Classification of approach papers by objective, jargon type, model family, supervision, and evaluation strategy. |
| `evaluation_overview.csv` | Evaluation setups and measures reported by the approach papers. |
| `resources.csv` | Resources used by the surveyed approaches. |
| `resources_taxonomy.csv` | Comparison of resource properties and coverage. |
| `publication_overview.csv` | Summary of publication venues and contribution types. |
| `database_distribution.csv` | Counts of included contributions by retrieval source. |
| `terms_overview.csv` | Terminology and definitions used in the surveyed literature. |
| `terms_distribution.csv` | Frequency summary of terminology used across the corpus. |
| `years_distribution.csv` | Publication-year distribution of the final corpus. |
| `legend.txt` | Codes used in the taxonomy files. |

## Search query

The following query was adapted to the syntax supported by each database:

```text
"dark jargon"
OR
(("jargon" OR "slang" OR "argot" OR "euphemism*")
 AND
 ("dark web" OR "dark net" OR "darkweb" OR "darknet" OR "underground")
 AND
 ("language model*" OR "natural language processing"))
```

During query development, related terms—including *coded language*, *code word*, *cant*, *dog whistle*, *semantic shift*, and *obfuscation*—were tested. They produced substantially more unrelated sociolinguistic or coarse-classification results. Snowballing was used to reduce terminology-dependent recall limitations.

## Eligibility and screening

Records were excluded when they:

1. were not written in English;
2. lacked accessible full text;
3. duplicated another publication;
4. had no dark-web connection;
5. did not use dark-web textual data;
6. focused on non-textual modalities;
7. did not involve NLP or language modelling;
8. addressed only coarse classification, such as website classification; or
9. were surveys or literature reviews.

The retrieval files document screening decisions. When more than one exclusion criterion applied, one primary reason was assigned for counting purposes.

Studies based only on surface-web data were outside the review scope because the paper focuses on linguistic practices in dark-web environments. Surface-web sources used as comparison corpora did not automatically cause exclusion.

## Taxonomy legend

### Objectives

- `O1`: term-level detection
- `O2`: post-level detection
- `O3`: interpretation or grounding
- `O4`: analysis or reasoning

### Jargon types

- `T1`: slang
- `T2`: euphemisms or indirect references
- `T3`: obfuscations or variants
- `T4`: contextual semantic shift

### Model families

- `M1`: lexicons or rules
- `M2`: probabilistic models
- `M3`: embeddings
- `M4`: classifiers
- `M5`: contextual language models
- `M6`: graph or syntactic models
- `M7`: unsupervised or clustering methods
- `M8`: causal or autoregressive large language models
- `M9`: mathematical or statistical measures

### Supervision

- `S1`: unsupervised
- `S2`: weak or distant supervision
- `S3`: supervised
- `S4`: semi-supervised or self-supervised

### Evaluation

- `E1`: token- or span-level metrics
- `E2`: post- or sentence-level metrics
- `E3`: ranking or discovery metrics
- `E4`: human or qualitative analysis
- `E5`: diagnostic or probing evaluation

## Relationship to the paper

The files support the paper as follows:

| Paper component | Supporting files |
|---|---|
| Corpus construction and study-selection flow | `paperretrieval_fullresults.CSV`, `paperretrieval_fullsearch_dedup.CSV`, `paperretrieval_snowballing_dedup.csv` |
| Included approaches and resources | `1. core_nlppapers-darkjargon.csv`, `2. datasets_resources.csv` |
| Approach taxonomy and cross-RQ synthesis | `Approach_taxonomy.csv`, `evaluation_overview.csv` |
| Resource reuse, coverage, and bias analysis | `resources.csv`, `resources_taxonomy.csv` |
| Terminology analysis | `terms_overview.csv`, `terms_distribution.csv` |
| Publication and temporal distributions | `publication_overview.csv`, `database_distribution.csv`, `years_distribution.csv` |



## Limitations

- The corpus is systematically collected under the stated criteria; it is not claimed to contain every publication that could be described as coded-language research
- Search recall depends on database indexing and terminology
- The accessible-full-text criterion may introduce availability bias
- Resource descriptions depend on information reported by the original authors
- Several underlying datasets are restricted, sensitive, or cannot legally be redistributed
- Taxonomy assignments involve expert interpretation. Ambiguous cases were resolved through full-text inspection and discussion

## Ethical and legal considerations

This artifact contains literature metadata and analytical annotations. It does not contain newly collected dark-web content, personal data extracted from dark-web platforms, or copies of restricted datasets. Users should consult the original publications and respect their licenses, access restrictions, and ethical conditions.

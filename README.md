# Tracing Innovation Pathways — Thematic & Network Analysis

This repository contains the qualitative analysis workflow supporting the manuscript  
**“Tracing Innovation Pathways”** :
Assom,  L.; Larsson,  A.; Chiolerio,  A. Tracing Innovation Pathways. Preprints 2025, 2025122547. https://doi.org/10.20944/preprints202512.2547.v1

The goal of this work is to explore how *intermediate innovation steps* (including failures, partial results, and experimental decisions) can be traced, analysed, and valued as cumulative contributions to innovation.

The repository focuses on:

- Thematic analysis of interviews and questionnaires collected within an EU-funded research consortium

The manuscript focuses on:
- Network-based exploration of relationships between codes, themes, and narratives
- A proof-of-concept analytical pipeline for tracing innovation pathways bottom-up (knowledge-graph based on blockchain)
- Conceptual grounding for graph-based and information-theoretic approaches to innovation value (Fisher-Shannon entropy)


---

## Manuscript Context

The manuscript investigates limitations of conventional innovation assessment (e.g. ex-ante / ex-post metrics and TRLs) and proposes an *in-itinere* approach to tracing innovation as it unfolds.

Key contributions described in the paper:

1. **Empirical insights**  
   Qualitative data from researchers involved in an EU consortium, highlighting perceptions of innovation, failure, governance, and latent value in intermediate results.

2. **Prototype instantiation**  
   A proof-of-concept model representing innovation as a directed graph of inputs, processes, and outputs, enabling backward and forward tracing of contributions.

3. **Conceptual abstraction**  
   A framework for interpreting innovation value as a function of network topology (global diversity and local coherence), rather than purely monetary or patent-based metrics.

This notebook implements the empirical analysis layer that informs both the prototype and conceptual framework.

---

## Notebook Overview — `Thematic analysis.ipynb`

The notebook performs a **hybrid deductive/inductive thematic analysis** combined with **network analysis**.

### Purpose

- Extract themes from coded qualitative data
- Inspect stability and diversity of themes
- Explore relationships between:
  - sentences ↔ codes
  - codes ↔ classes
  - codes ↔ themes
- Identify narrative structures and central concepts
- Support retrieval of sentences underpinning each theme

---

## Data Requirements

Input data is expected as Excel or Google Sheets files:

- One sheet per respondent
- Each row corresponds to a *tokenised sentence or paragraph*
- Each row includes:
  - respondent ID
  - sentence text
  - inductively assigned codes (comma-separated)
  - optionally: predefined *Classes* (macro-areas)

### Typical Columns

| respondent | sentence | codes | classes |
|------------|----------|-------|---------|

---

## Method Summary

### 1. Coding Strategy

- **Deductive layer (Classes):**  
  Used to ensure coverage of predefined macro-areas (e.g., innovation definitions, governance, tools, data formats).

- **Inductive layer (Codes):**  
  Generated iteratively from respondent answers and refined through constant comparison.

Codes can be merged or coalesced across iterations depending on desired granularity.

---

### 2. Theme Extraction

Themes are derived inductively from clusters of codes.

In this study, nine themes emerged:

- Perception  
- Opportunity  
- Insight  
- Current Situation  
- Uncertainty  
- Assets  
- Appropriate Language  
- Critics  
- Disadvantages  

Theme diversity is quantified using the **coefficient of unlikeability** (probability that two randomly selected instances of theme-codes associations will be in different categories), showing high heterogeneity across responses.

Theme robustness is inspected using the **mutual information** and **correlation** : values closed to zero across almost all pairs of themes indicate non-redundant and distinct thematic coverage. 

---

### 3. Network Analysis

The notebook constructs bipartite and projected graphs to explore:

- Code–sentence relationships
- Code–theme relationships
- Code–class relationships

Community detection and centrality measures are applied to:

- Identify dominant narratives
- Reveal structural connections between themes
- Highlight bridging concepts (e.g., governance, authorship, traceability)

Boolean operations on code sets (e.g., *Opportunities AND Disadvantages*) are used to surface trade-offs and tensions in participant perspectives.

---

## Key Empirical Insights

The analysis supports several findings discussed in the manuscript:

- **Failures are treated as innovation assets**, providing actionable knowledge for future experiments.
- Intermediate steps carry *latent value* even when they do not lead to immediate success.
- Researchers expressed strong interest in:
  - backward traceability of experiments
  - integration of heterogeneous data
  - visualisation of innovation pathways
- Regular tracing (bi-weekly to monthly) was considered feasible.
- Major concerns include administrative overhead, information overload, and governance of IP and attribution.
- Innovation is perceived both as:
  - a *horizontal* recombination of distant fields
  - a *vertical* discontinuity driven by unexpected breakthroughs

These insights directly informed the design of the proof-of-concept innovation graph and the proposed information-theoretic interpretation of value.

---

## Intended Use

This repository is meant to support:

- Replication of the thematic/network analysis protocol
- Adaptation to other research consortia or innovation contexts
- Early-stage prototyping of tools for tracing innovation pathways
- Methodological transfer to studies of R&D processes, knowledge graphs, and innovation governance

It is exploratory by design.

---

## How to Run

1. Prepare your spreadsheet data on excel/google sheets.
2. Update file paths in `Thematic analysis.ipynb`.
3. Run the notebook sequentially to:
   - load data
   - build networks
   - compute theme distributions
   - perform community detection
   - visualise narrative structures

---

## License

All contents of this repository are licensed under:
Creative Commons Attribution 4.0 (CC BY 4.0).

You are free to share and adapt with attribution.

---

## Citation

If you use this material, please cite the manuscript:

Assom,  L.; Larsson,  A.; Chiolerio,  A. Tracing Innovation Pathways. Preprints 2025, 2025122547. https://doi.org/10.20944/preprints202512.2547.v1


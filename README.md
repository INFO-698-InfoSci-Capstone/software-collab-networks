# Scientific Collaboration Networks on Software

[![License: GPL v3](https://img.shields.io/badge/License-GPLv3-blue.svg)](https://www.gnu.org/licenses/gpl-3.0)

---

## Table of Contents

- [Overview](#overview)  
- [Methodology](#methodology)  
- [Data Processing](#data-processing)  
- [Network Analyses](#network-analyses)  
  - [Software–Author Collaboration](#software–author-collaboration)  
  - [Language–Software Collaboration](#language–software-collaboration)  
  - [Contrast in Software–Language Usage](#contrast-in-software–language-usage)  
  - [Software–Year Mention Analysis](#software–year-mention-analysis)  
  - [Software–Country Mention Analysis](#software–country-mention-analysis)  
- [Conclusion](#conclusion)  
- [iShowcase Poster](#ishowcase-poster)  
- [Directory Structure](#directory-structure)  
- [License](#license)

---

## Overview

Scientific software underpins modern phylogenetic research, yet we know surprisingly little about **who** uses **what**, and **why**. This study leverages **197,677** full-text articles (1990–2024) to answer:

- **Who uses which phylogenetic tools, and where?**  
- **How do geographic, linguistic, and genealogical factors shape software adoption?**  
- **What network structures emerge among authors and tools?**

Key tools include **MEGA, NDE, BEAST, RAxML, MrBayes, TNT**, and many others. We demonstrate that software choice is not only a technical decision but also a **social construct**, influencing career trajectories and the diffusion of innovation.

---

## Methodology

1. **Define Research Questions**  
   Investigate clustering of software use across location, language, and academic lineages.  
2. **Collect Data**  
   - Retrieved 197,677 articles from **Constellate** (JSTOR + Portico) with the query  
     ```
     phylogenetic OR systematics OR Cladistic analysis
     ```  
   - Covered all languages, 1990–2024, document type = article.  
3. **Extract Software Mentions**  
   - Employed a dictionary+regex approach (CZ method) to detect mentions of tools like WinClada, RAxML, TNT, etc.  
   - Captured sentence contexts for manual validation.  
4. **Merge with OpenAlex**  
   - Mapped DOIs to OpenAlex records to pull author IDs, affiliations, countries, and institutions.  
5. **Analyze Patterns**  
   - Built bipartite author–software, language–software, and country–software networks.  
   - Applied network‐analysis metrics and fixed-effects regressions to study adoption, career impacts, and innovation outcomes.

---

## Data Processing

- **Source**: Constellate full texts & OpenAlex metadata  
- **Filtering**: Keep only articles with detected software mentions  
- **Metadata extraction**:  
  - **DOI →** author IDs, country, institution  
  - **Article →** language, year, software list  
- **Edge list**:  
  | author_id | DOI | software | year | language | country |

---

## Network Analyses

### Software–Author Collaboration

Visualizes ~5,000 papers as a bipartite network of **authors (black nodes)** and **software tools (colored)**.

- **Central hubs**: MEGA, BEAST, RAxML  
- **Peripheral**: DELTA, WinClada, Hennig86  
- **Insight**: Tight clusters around certain tools reflect mentorship lineages and departmental practices.

### Language–Software Collaboration

Bipartite graph linking **publication languages** to **software tools**.

- **Dominant**: English, Spanish  
- **Exclusives**: Some tools appear only in specific languages  
- **Cross‐language**: Tools like MEGA, NDE span multiple language communities  

### Contrast in Software–Language Usage

Dual‐panel bar chart:

- **Main panel**: Top tools by relative frequency (NDE, MEGA, IQ-TREE, PAUP) across languages  
- **Zoom panel**: Rarely used tools (Mesquite, MacClade, Phylip, etc.)  

Also includes an interactive treemap of usage frequencies.

### Software–Year Mention Analysis

Chord-style circular network from 1990–2022:

- **Early adopters**: NDE, MEGA (thick edges in 1990s)  
- **2000s peak**: PAUP, MrBayes  
- **Recent**: RAxML, TNT, IQ-TREE show growing relevance  

### Software–Country Mention Analysis

Global network of **countries (blue)** ↔ **software (orange)**:

- **Global hubs**: US, CN, FR, DE with heavy MEGA & NDE use  
- **Regional preferences**: TNT, PAST, DELTA in specific continents  
- **Peripheral**: Legacy tools used sporadically  

---

## Conclusion

Software choice in phylogenetics reflects **social** and **geographic** structures:

- **Global staples**: MEGA, NDE in almost every region  
- **Language effects**: English dominance, with secondary niches  
- **Temporal shifts**: From parsimony to Bayesian/likelihood frameworks  
- **Network clustering**: Mentorship and hiring pipelines reinforce tool communities  

To foster innovation and inclusion, we must consider beyond pure technical capability who uses which tools, where, and why.

---


## Directory Structure

## File Organization

    analysis/
    |
    ├── logs/
    │   └── log.md          # log of any progress or relevant information
    |
    ├── figures/            # location of the figures produced for the manuscript
    |
    ├── data/
    |   ├── rawData/        # data obtained from elsewhere
    │   └── derivedData/    # data generated from rawData/ and scripts.*
    |   
    └── supplementaryMaterials/
        ├── supplementaryFigures/     
        |                   # supplementary figures for the main manuscript
        └── supplementaryTables/      
                            # supplementary tables for the main manuscript 
    
    R/Python/etc.           # scripts to run in the following order (also see associated README.md)
        └── script.*        # hypothetical script used to wrangle the raw data, produce figures, analyses, and supplementary materials

        


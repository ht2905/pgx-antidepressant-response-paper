# CYP2D6 and CYP2C19 Polymorphisms as Predictors of Antidepressant Response

**Precision Pharmacogenomics for Major Depressive Disorder (MDD)**

This repository contains the complete Quarto project, literature synthesis files, and rendered publication-ready manuscript for a scientific review on psychiatric pharmacogenomics (PGx). The manuscript was prepared for the Genetics course (BT313IU) at International University – Vietnam National University, Ho Chi Minh City (VNU-HCM), formatted with the Elsevier journal template.

---

## Quick Access

If you are a researcher, clinician, or student who only wants to read the finished review, **you do not need to install or run any software**:

- **Read the full manuscript:** Download or open [`pgx_antidepressant_response_article.pdf`](./pgx_antidepressant_response_article.pdf) directly from this repository.
- **Assignment cover page:** Available at [`cover_page_for_assignments.pdf`](./cover_page_for_assignments.pdf).

---

## Scientific Overview

Major Depressive Disorder (MDD) affects hundreds of millions of people globally, yet standard antidepressant selection remains largely trial-and-error. Approximately 30% of patients fail to achieve symptom remission even after multiple therapeutic trials (as observed in the STAR*D trial), leading to Treatment-Resistant Depression (TRD), prolonged suffering, and elevated risks of adverse drug reactions (ADRs).

This paper synthesizes clinical and mechanistic evidence demonstrating how genetic variation in Phase I hepatic cytochrome P450 enzymes—specifically ***CYP2D6*** and ***CYP2C19***—dictates antidepressant clearance, steady-state blood concentrations, and clinical outcomes for Selective Serotonin Reuptake Inhibitors (SSRIs) and Tricyclic Antidepressants (TCAs).

### Core Concepts Covered

- **Metabolic Phenotypes:** How inherited diplotypes translate into functional activity scores and metabolic categories:
    - Ultrarapid Metabolizer (UM)
    - Rapid Metabolizer (RM, primarily *CYP2C19*)
    - Normal Metabolizer (NM)
    - Intermediate Metabolizer (IM)
    - Poor Metabolizer (PM)
- **Clinical Guidelines:** Translating genotype data into prescribing actions based on evidence-based consensus recommendations from the Clinical Pharmacogenetics Implementation Consortium (CPIC) and Dutch Pharmacogenetics Working Group (DPWG).
- **Differential Drug Selection:** Why UMs should be switched to non-CYP2D6 / non-CYP2C19 pathways (e.g., bupropion, vilazodone, desvenlafaxine) rather than escalating doses.
- **Dose Adjustment Protocols:** Specific 50% dose reductions recommended for *CYP2C19* PMs on escitalopram, citalopram, or sertraline to prevent toxicity (including QT prolongation).
- **Application in TRD:** Distinguishing genuine pharmacodynamic drug resistance from hidden pharmacokinetic failure (e.g., rapid clearance causing subtherapeutic drug exposure, or poor metabolism causing severe side-effects).
- **Implementation Hurdles & Horizons:** Current barriers in cost, multi-gene complexity, and physician training, alongside technological integrations via Electronic Health Record (EHR) clinical decision support and Polygenic Risk Scores (PRS).

---

## Repository Contents

| File / Directory | Description |
|---|---|
| [`pgx_antidepressant_response_article.pdf`](./pgx_antidepressant_response_article.pdf) | Rendered publication-ready review article formatted in Elsevier 5p layout. |
| [`pgx_antidepressant_response_article.qmd`](./pgx_antidepressant_response_article.qmd) | Main Quarto manuscript source file containing text, citations, and metadata. |
| [`bibliography.bib`](./bibliography.bib) | BibTeX bibliography containing all cited clinical literature and guidelines. |
| [`preamble.tex`](./preamble.tex) | LaTeX preamble specifying custom packages, table wrapping, and link settings. |
| [`_quarto.yml`](./_quarto.yml) | Quarto project configuration file. |
| [`photos/`](./photos/) | High-resolution figure assets (e.g., global *CYP2D6* duplication distribution map). |
| [`cover_page_for_assignments.pdf`](./cover_page_for_assignments.pdf) | Coursework submission title and cover sheet. |
| [`pgx_antidepressant_response_article.Rproj`](./pgx_antidepressant_response_article.Rproj) | RStudio project file for streamlined workspace loading and environment binding. |
| [`renv.lock`](./renv.lock) & [`renv/`](./renv/) | R package dependency lockfile ensuring reproducible package installations. |

---

## How to Build or Modify the Paper

This section provides clear, step-by-step instructions for wet-lab scientists or researchers who want to inspect the source code, modify text, or re-render the PDF.

### Prerequisites

To compile the Quarto manuscript into the Elsevier-formatted PDF, ensure you have the following installed on your computer (Windows, macOS, or Linux):

1. **R (version 4.2 or higher):** Download from [CRAN](https://cran.r-project.org/).
2. **RStudio Desktop (recommended):** Download from [Posit](https://posit.co/download/rstudio-desktop/).
3. **Quarto CLI (version 1.3 or higher):** Usually bundled with modern RStudio versions, or downloadable from [quarto.org](https://quarto.org/docs/get-started/).
4. **A LaTeX distribution for PDF rendering:**
    - If you do not have LaTeX installed, Quarto makes this easy through TinyTeX:
      ```bash
      quarto install tinytex
      ```
    - Alternatively, from inside R:
      ```r
      tinytex::install_tinytex()
      ```

---

### Method A: Using RStudio Desktop (Recommended for Wet-Lab Researchers)

1. **Clone or Download the Repository:**
    - Clone using Git:
      ```bash
      git clone https://github.com/ht2905/pgx-antidepressant-response-paper.git
      ```
    - Or click **Code -> Download ZIP** on GitHub and unpack the archive on your local computer.

2. **Open the Project:**
    - Double-click the [`pgx_antidepressant_response_article.Rproj`](./pgx_antidepressant_response_article.Rproj) file. This opens RStudio and automatically sets your working directory.

3. **Restore Required R Packages:**
    - In the RStudio **Console** tab, run:
      ```r
      install.packages("renv")
      renv::restore()
      ```
    - When prompted to confirm package installation, type `y` and press **Enter**. This installs the exact packages tracked in [`renv.lock`](./renv.lock) (such as `knitr`, `rmarkdown`, `tinytex`, and `yaml`) into a self-contained project library without altering your system R libraries.

4. **Install the Elsevier Quarto Journal Template:**
    - In RStudio's **Terminal** tab (next to the Console tab), run:
      ```bash
      quarto add quarto-journals/elsevier
      ```
    - Type `Y` to agree to trust the extension and accept default settings.

5. **Render the PDF:**
    - Open [`pgx_antidepressant_response_article.qmd`](./pgx_antidepressant_response_article.qmd) from the Files pane.
    - Click the **Render** button at the top of the editor pane (or press `Ctrl+Shift+K` on Windows/Linux, `Cmd+Shift+K` on macOS).
    - The compiled PDF will generate in the project folder and open in the preview pane.

---

### Method B: Using the Command Line (Terminal / Bash)

1. **Clone the repository:**
    ```bash
    git clone https://github.com/ht2905/pgx-antidepressant-response-paper.git
    cd pgx-antidepressant-response-paper
    ```

2. **Restore project dependencies:**
    ```bash
    Rscript -e "if (!requireNamespace('renv', quietly = TRUE)) install.packages('renv'); renv::restore()"
    ```

3. **Add the Elsevier Quarto extension:**
    ```bash
    quarto add quarto-journals/elsevier --no-prompt
    ```

4. **Render the document:**
    ```bash
    quarto render pgx_antidepressant_response_article.qmd
    ```

---

## Troubleshooting Common Issues

- **Error: "LaTeX failed to compile pgx_antidepressant_response_article.tex"**
    - The Elsevier PDF format requires LaTeX tools. Ensure TinyTeX is installed by running:
      ```bash
      quarto install tinytex
      ```
      Or from inside R:
      ```r
      install.packages("tinytex")
      tinytex::install_tinytex()
      ```
- **Error: "Unknown format: elsevier-pdf"**
    - You need the Elsevier journal extension. In your terminal or RStudio Terminal tab, run:
      ```bash
      quarto add quarto-journals/elsevier
      ```
- **R package compilation warnings on older OS versions:**
    - If `renv::restore()` asks to compile packages from source and fails due to missing C/C++ build tools (e.g. `Rtools` on Windows or `build-essential` on Ubuntu), install binary versions or install [Rtools](https://cran.r-project.org/bin/windows/Rtools/) for your R version.

---

## Academic & Course Context

- **Course:** Genetics (BT313IU)
- **Program:** School of Biotechnology, International University – VNU-HCM
- **Instructor:** MSc. Hang T. Tong
- **Corresponding Author:** Tran Quoc Hoang ([tranquochoang@protonmail.com](mailto:tranquochoang@protonmail.com))

### Author Contributions (CRediT Taxonomy)

- **Tran Quoc Hoang:** Conceptualization, Methodology, Project Administration, Software (Quarto/LaTeX compilation), Investigation, Writing – Original Draft (*Section 3.2: Application in Therapy*), Writing – Review & Editing.
- **Nguyen Hoang Thanh Ngan:** Investigation, Writing – Original Draft (*Section 3.1: Genetics in Etiology and Diagnosis*), Writing – Review & Editing.
- **Pham Gia Han:** Investigation, Methodology, Writing – Original Draft (*Section 1: Introduction* and *Section 2: Materials & Methods*), Writing – Review & Editing.
- **Pham Ngo Phuong Thao:** Investigation, Writing – Original Draft (*Section 3.3: Clinical Challenges and Future Directions*), Writing – Review & Editing.
- **Nguyen Hoang Tuong Vy:** Data Curation, Visualization, Presentation Slide Preparation, Writing – Review & Editing.
- **Nguyen Le Ngoc Vy:** Data Curation, Visualization, Presentation Slide Preparation, Writing – Review & Editing.

### Competing Interests

The authors declare that they have no known competing financial interests or personal relationships that could have appeared to influence the work reported in this paper.

---

## Citation & License

If you reference or use this review or Quarto setup in your work, please cite:

```bibtex
@article{tran2025cyp2d6pgx,
  title   = {CYP2D6 and CYP2C19 Polymorphisms as Predictors of Antidepressant Response},
  author  = {Tran, Quoc Hoang and Nguyen, Hoang Thanh Ngan and Pham, Gia Han and Pham, Ngo Phuong Thao and Nguyen, Hoang Tuong Vy and Nguyen, Le Ngoc Vy},
  journal = {Genetics Review (BT313IU), International University - VNU-HCM},
  year    = {2025},
  url     = {https://github.com/ht2905/pgx-antidepressant-response-paper}
}
```

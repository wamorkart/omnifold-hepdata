# OmniFold Publication Ecosystem

**Standardizing the publication, preservation, and reuse of ML-based unfolding results**

This project is an effort to define **how machine-learning–based unfolding results (in particular OmniFold)** should be published in a way that is reusable, and compatible with **HEPData**.

Modern unfolding methods produce *per-event weights and trained models*, rather than fixed binned histograms. While this enables flexibility and reinterpretation, it also raises new challenges for publication, reproducibility, and long-term usability. Our goal is to try and define a coherent set of specifications, tools, and reference implementations to address those challenges.

---

<!-- ## Motivation

Classical unfolding methods rely on fixed binning, which makes results difficult to reuse once published. New observables, alternative binning choices, or reinterpretations cannot be performed without rerunning the unfolding.

In contrast, machine-learning–based methods such as **OmniFold** produce **per-event unfolded weights**, allowing arbitrary observables to be computed *after publication*. However, the community currently lacks standards for:
- Publishing per-event unfolding weights
- Distributing trained models and metadata
- Ensuring compatibility with HEPData

--- -->

## Scope

We want to define:
- **What should be published**
- **How should the published weights be structured**
- **How they integrate with HEPData**
- **How users can consume and reinterpret results**

<!-- The goal is not to mandate a single analysis workflow, but to provide **minimal, experiment-agnostic standards and reference tools** that make ML-based unfolding results usable beyond the original publication. -->

---

## Ecosystem Overview

<!-- Publishing an OmniFold result typically involves multiple layers, from raw per-event weights to derived observables and validation. This ecosystem is organized into the following sub-components.

--- -->

## Sub-components

### 1. Data & Metadata Specification  
<!-- **Foundational layer** -->

Defines a schema for publishing OmniFold outputs, including:
- Event-level weights (nominal and systematic)
- Iteration structure (e.g. step-1 / step-2)
- Dataset selections
- Normalization
---

### 2. Per-Event Weights Archive  
<!-- **Primary scientific artifact** -->

Standardized publication of:
- Per-event OmniFold weights
<!-- - Iteration history
- Event identifiers -->
- Minimal associated metadata

<!-- > Histograms are derived products — per-event weights are the fundamental result. -->
<!-- 
📦 **Repository**: `omnifold-weights`  
📄 **Audience**: experiments, phenomenologists

--- -->

### 3. Model & Training Artifacts  
<!-- **Reproducibility layer (optional)** -->

Optional publication of:
- Trained neural network checkpoints
- Architecture definitions
- Training configurations
- Feature preprocessing details

<!-- Supports different reproducibility levels, from *weights-only* to *full model release*.

📦 **Repository**: `omnifold-models`  
📄 **Audience**: ML researchers, method developers

--- -->

### 4. Observable Definitions  
<!-- **Semantic layer** -->

Defines unfolded observables, including:
- Physics definitions
- Phase space restrictions
- Binning (when applicable)
- Reference implementations

<!-- 📦 **Repository**: `omnifold-observables`  
📄 **Audience**: analysts, reinterpreters

--- -->

### 5. Analysis & Reinterpretation Toolkit  
**User-facing layer**

Tools to:
- Load published weights (locally or from HEPData)
- Apply weights to events
- Compute arbitrary observables
- Propagate statistical and systematic uncertainties
- Produce publication-quality plots

Enables reinterpretation **without rerunning the unfolding**.

<!-- 📦 **Repository**: `omnifold-analysis`  
📄 **Audience**: phenomenologists, ML researchers, experimental re-analyses

--- -->

### 6. Validation  
<!-- **Trust layer** -->

Provides standardized validation procedures, including:
- Closure tests
<!-- - Stability across iterations -->
- Normalization checks
- Consistency tests

Ensures published results are scientifically robust and reviewable.

<!-- 📦 **Repository**: `omnifold-validation`  
📄 **Audience**: reviewers, collaborations, HEPData

--- -->

### 7. HEPData Integration Layer  
<!-- **Glue layer** -->

Merge OmniFold outputs with HEPData infrastructure:
- Mapping OmniFold results to HEPData records
- Submission templates and guidelines
- Metadata conventions
- Validation steps

<!-- 📦 **Repository**: `omnifold-hepdata`  
📄 **Audience**: HEPData curators, publishers

--- -->

### 8. Examples & Reference Implementations  
<!-- **Pedagogical layer** -->

End-to-end examples using public datasets demonstrating:
- How to publish OmniFold outputs
- How to upload to HEPData
- How to reproduce published observables
- How to compute new observables post-publication
<!-- 
📦 **Repository**: `omnifold-examples`  
📄 **Audience**: new users, students, GSoC contributors

--- -->
<!-- 
## Design Principles

- **Experiment-agnostic**
- **HEPData-compatible**
- **Reproducible by construction**
- **Post-publication reinterpretability**
- **Clear separation of data, models, and analysis**

---

## Intended Audience

- Experimental collaborations publishing unfolding results
- Phenomenologists reusing unfolded data
- Machine learning researchers developing new methods
- HEPData curators and infrastructure developers

---

## Governance and Contributions

This ecosystem is designed to evolve collaboratively with:
- Experimental collaborations
- CERN-HSF
- HEPData
- The broader ML + HEP community

Contributions, feedback, and new use cases are welcome.

--- -->

## References

- OmniFold: A Method to Simultaneously Unfold All Observables  
  https://arxiv.org/abs/1911.09107

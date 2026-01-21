# OmniFold Publication Ecosystem

**Standardizing the publication, preservation, and reuse of ML-based unfolding results**

This project is an effort to define **how machine-learning–based unfolding results (in particular OmniFold)** should be published in a way that is reusable, and compatible with **HEPData**.

Modern unfolding methods produce *per-event weights and trained models*, rather than fixed binned histograms. While this enables flexibility and reinterpretation, it also raises new challenges for publication, reproducibility, and long-term usability. Our goal is to try and define a coherent set of specifications, tools, and reference implementations to address those challenges.

---


## Scope

We want to define:
- **What should be published**
- **How should the published weights be structured**
- **How they integrate with HEPData**
- **How users can consume and reinterpret results**


---

## Ecosystem Overview


## Sub-components

### 1. Data & Metadata Specification  
<!-- **Foundational layer** -->

Defines a schema for publishing OmniFold outputs, including:
- Event-level weights (nominal and systematic)
- Iteration structure (e.g. step-1 / step-2)
- Dataset selections
- Normalization
---

### 2. Per-Event Weights   

Standardized publication of:
- Per-event OmniFold weights
- Minimal associated metadata

### 3. Model & Training Details  

Optional publication of:
- Trained neural network checkpoints
- Architecture definitions
- Training configurations
- Feature preprocessing details


### 4. Observable Definitions  

Defines unfolded observables, including:
- Physics definitions
- Phase space restrictions
- Binning (when applicable)
- Reference implementations


### 5. Analysis & Reinterpretation   
**User-facing layer**

Tools to:
- Load published weights (locally or from HEPData)
- Apply weights to events
- Compute arbitrary observables
- Propagate statistical and systematic uncertainties
- Produce publication-quality plots

Enables reinterpretation **without rerunning the unfolding**.


### 6. Validation  

Provides standardized validation procedures, including:
- Closure tests
- Normalization checks
- Consistency tests

Ensures published results are scientifically robust and reviewable.


### 7. HEPData Integration Layer  

Merge OmniFold outputs with HEPData infrastructure:
- Mapping OmniFold results to HEPData records
- Submission templates and guidelines
- Metadata conventions
- Validation steps


### 8. Examples & Reference Implementations  

End-to-end examples using public datasets demonstrating:
- How to publish OmniFold outputs
- How to upload to HEPData
- How to reproduce published observables
- How to compute new observables post-publication


## References

- OmniFold: A Method to Simultaneously Unfold All Observables  
  https://arxiv.org/abs/1911.09107

- Tools for unbinned unfolding (RooUnfold-based Omnifold framework + standalone Omnifold package available through PyPI)
  https://arxiv.org/abs/2503.09720

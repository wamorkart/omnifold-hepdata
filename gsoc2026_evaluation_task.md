# GSoC 2026 Evaluation Task: OmniFold Publication Tools

## Background

The [OmniFold algorithm](https://arxiv.org/abs/1911.09107) is a machine-learning-based unfolding method used in high-energy physics experiments. Unlike traditional unfolding, it produces **per-event weights** rather than binned histograms, enabling flexible reinterpretation of results.

The existing [OmniFold Python package](https://github.com/hep-lbdl/OmniFold) handles *running* the algorithm, but stops there. There is currently no standard for how the resulting weights should be stored, documented, or shared with the community. This GSoC project aims to fill that gap.

---

## What We Provide

Three HDF5 files containing pre-calculated OmniFold weights for pseudo-data, that mimics a real ATLAS measurement:

- `multifold.h5` — the nominal result, based on MG5 simulation
- `multifold_sherpa.h5` — an alternative generator (Sherpa), treated as a systematic uncertainty
- `multifold_nonDY.h5` — an alternative sample composition (includes EW Zjj/VBF and diboson), treated as another systematic uncertainty

These files can be downloaded from this [Zenodo link](https://zenodo.org/records/11507450). Be sure to work with the files under `files/pseudodata`.

---

## Your Task

### Part 1 – Exploration and Gap Analysis 

Load and inspect all three files. Then write a short document (one page is fine) addressing:

- What columns are present, and which are weights vs. observables vs. metadata?
- What information would a physicist need to *reuse* these weights that is **not** currently present in the files?
- What challenges do you anticipate in standardizing this kind of output across different experiments or analyses?

<!-- > This is the most important part of the task. We want to see that you understand the problem space before designing a solution. -->

### Part 2 – Metadata Schema Design 

Design a YAML metadata file that would accompany the nominal weight file and fill in the gaps you identified in Part 1. It should capture at minimum:

- What dataset this is and how it was generated
- Which systematic variations are present in the files
- Any normalization or event selection information

Then write a short justification (a few paragraphs) explaining:

- Why you structured it the way you did
- What you chose to include vs. leave out and why
- How you would expect a user who didn't run the original analysis to interact with this file

> You do not need to implement this in code — we are evaluating your design thinking.

### Part 3 – Coding Exercise

Write a single self-contained Python function that computes a weighted histogram of an observable. You can choose a sensible binning. Add plotting functionality to this function as well.

Include tests (using pytest or simple assertions) that verify the function behaves correctly — think about what the most important edge cases are and explain your choices briefly in a comment.

---

## Deliverable

A GitHub repository containing:

- `gap_analysis.md` 
- `metadata.yaml` and `schema_design.md` 
- `weighted_histogram.py` 



---
You do not need a physics background. We are primarily evaluating software design thinking!
---

*Questions? Email [tanvi.wamorkar@cern.ch](mailto:tanvi.wamorkar@cern.ch) and [nachman@stanford.edu](mailto:nachman@stanford.edu) with "gsoc26" in the subject line.*

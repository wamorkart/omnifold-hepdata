# omnifold-hepdata


**Standardized publication of OmniFold models, weights, and per-event unfolded results**

`omnifold-hepdata` is a public-facing, experiment-agnostic framework for publishing, sharing, and reusing OmniFold-based unfolding results. It provides a standardized structure for distributing trained neural networks, per-event OmniFold weights, and derived unfolded observables in a way that is compatible with [HEPData](https://www.hepdata.net/) and supports long-term reproducibility and reinterpretation.



## Repository Structure

```text
omnifold-hepdata/
├── data-format/          # Specification of the standardized data schema
├── weights/              # Per-event OmniFold weights and metadata
├── models/               # Trained neural network checkpoints and configs
├── observables/          # Definitions of unfolded observables
├── analysis/             # Plug-and-play analysis and plotting tools
├── examples/             # End-to-end worked examples with public datasets
├── validation/           # Closure tests and consistency checks
└── docs/                 # Documentation and usage guides


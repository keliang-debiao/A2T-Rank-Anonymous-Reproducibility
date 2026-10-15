A2T-Rank Anonymous Reproducibility Package
This repository contains the anonymous implementation, configuration files, data interfaces, command-line utilities, verification scripts, and tests for A2T-Rank. It is organized to support training, evaluation, controlled component removal, robustness checks, calibration, statistical analysis, prediction export, and release validation.
Repository Contents
.github/workflows/
Continuous-integration workflow for installing the package, running the test suite, checking reference-record integrity, scanning release text, and validating the release layout.
configs/
YAML configuration files defining the main A2T-Rank setting together with baseline, component-removal, and robustness settings. The main configuration specifies the visual backbones, adaptation settings, model dimensions, loss coefficients, data paths, optimization settings, fold structure, seeds, and output location.
data/
Data-interface documentation and metadata files. This directory includes the canonical manifest schema, source registry, and external-exclusion table. Third-party image data and annotations are not redistributed in this repository.
scripts/
Repository-level utilities for launching seed and cross-validation jobs, aggregating exported predictions, auditing anonymity, verifying reference-record structure, and checking release text for restricted terms.
src/a2t_rank/
Python source code for the A2T-Rank package, including:
- models/: A2T-Rank model definition, visual-stream components, baseline models, LoRA adaptation, and feature adapters.
- data/: annotation normalization, manifest preparation, image transformations, grouped split construction, dataset classes, and data-audit utilities.
- cli/: command-line entry points for data preparation, split construction, training, baseline training, prediction, evaluation, calibration, robustness assessment, statistical analysis, efficiency measurement, faithfulness analysis, external auditing, and release validation.
- Core modules for prompt construction, prompt-bank management, loss computation, calibration, prediction export, metrics, training control, configuration loading, and general utilities.
reference_records/
Structured reference-record files, status metadata, expected-range specifications, split-count records, and scripts used to validate their format and consistency. These files are kept separate from runtime outputs.
artifacts/
Documented output location for checkpoints, predictions, runtime logs, calibration files, metrics, statistical summaries, and audit materials generated during execution. Runtime-generated files are not included in the repository.
tests/
Unit tests covering core model behavior, calibration utilities, grouped split construction, and reference-record validation.
Model Components Included
The implementation contains a dual visual-stream design with a CLIP vision encoder and a ConvNeXt structural encoder. The package also includes visual adaptation layers, prompt-conditioned attribute queries, cross-attention fusion, style-specific and style-invariant factor branches, attribute prediction heads, reliability estimation, dynamic attribute aggregation, score and uncertainty heads, and the associated multi-term training objectives.
Data and Runtime Materials
The repository does not contain third-party datasets, pretrained checkpoints, per-image predictions, or machine-specific runtime logs. The provided data utilities define how official annotations and local image directories are converted into the canonical manifest used by the training and evaluation commands.
Package Validation Materials
The package includes automated tests, a continuous-integration workflow, release-layout validation, and utilities for checking anonymity and reference-record consistency.

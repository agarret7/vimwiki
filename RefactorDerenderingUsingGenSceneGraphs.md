# Motivation

High-level summary: we want the Derendering repo to be useable by others.

Allows us to reuse and simplify the infrastructure created for NeurIPS, in the
[tutorial sequence](SceneGraphInferenceTutorialSequence.md). This code reduction will help Nishad, Ben, and others to assist in inference engineering. Thus it's especially important to focus on
making shareable code, by removing dead pieces of code, simplifying core pieces
of infrastructure, and documenting the remaining functionality thoroughly.

# Context

The Derendering repository is made up of 3 main components:

1. Data pipeline (data generation, method/baseline execution, evaluation)
2. Visualization suite
3. Modeling/inference code

The primary considerations in the refactor (in order of importance) are:

* Pruning dead code, via an active selection of pieces of code to be integrated
  in a new repository. This is mostly relevant for (1) and (3)
* Removing Python dependencies by replacing command-line calls to
  RVizScenePublisher and wrappers with GenSceneGraphs calls to
  `overlaySceneGraph`. This is relevant for (2).
* Documenting the repository and its code.

There may be minimal rewriting of the actual infrastructure, but we can mostly
use a functional subset of the Derendering repo.

Special consideration should be paid to keeping the modeling and inference code
modular (self-contained)

# Deliverables

1. [ ] Push-button Makefile that runs entire pipeline
2. [ ] Running data generation pipeline calls the following:
    1. [ ] Generate YCB-Video dataset from raw data
    2. [ ] Generate YCB-InHouse dataset from raw data
    3. [ ] Generate YCB-Synthetic dataset
3. [ ] Running `run_methods.jl` generates
4. [ ] Running 

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
  in a new repository. This is mostly relevant for (1) and (3).
* Removing Python dependencies by replacing command-line calls to
  RVizScenePublisher and wrappers with GenSceneGraphs calls to
  `overlaySceneGraph`. This is relevant for (2).
* Documenting the repository and its code.

There may be minimal rewriting of the actual infrastructure, but we can mostly
use a functional subset of the Derendering repo. Special consideration should
be paid to keeping the modeling and inference code modular, so that we can very
easily make a Jupyter notebook version.

Looking ahead, if there is cross compatability for `.jl` files to be read as
Jupyter notebooks (maybe with cells defined by comments), we will want to use
that, and then define the tutorial sequence through a set of self-contained
`model.jl`/`infer.jl` pairs, so that we can run any single sequence as part of
the overall infrastructure, or read it as an almost completely self-contained
notebook/document for others.

# Deliverables

1. [ ] *README.md* containing a summary of the infrastructure
2. [ ] Push-button Makefile that runs entire pipeline
    1. [ ] Running data generation pipeline reruns the following:
        1. [ ] Download raw YCB-Video dataset and convert to canonical dataset format
        2. [ ] Generate YCB-Synthetic dataset
    2. [ ] Running data download pipeline reruns the following:
        1. [ ] Download converted YCB-Video dataset
        2. [ ] Download YCB-InHouse dataset
        3. [ ] Download YCB-Synthetic dataset
    4. [ ] Downloads YCB-Video raw data and YCB-InHouse prepared data
    5. [ ] Running `run_methods.jl` produces inference/baseline output and visualization
    6. [ ] Running `run_evaluation.jl` produces 
3. [ ] Simple generation of results

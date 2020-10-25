# Motivation

High-level summary: we want the Derendering repo to be easily useable by others.

Allows us to reuse and simplify the infrastructure created for NeurIPS, in the
[tutorial sequence](SceneGraphInferenceTutorialSequence.md). This code
reduction will help Nishad, Ben, and others to assist in inference engineering.
Thus it's especially important to focus on making shareable code, by removing
dead pieces of code, simplifying core pieces of infrastructure, and documenting
the remaining functionality such that it can be understood by the rest of the
team.

# Context

The Derendering repository is made up of 3 main components:

1. Data pipeline (data generation, method/baseline execution, evaluation)
2. Visualization suite
3. Modeling/inference code

The primary considerations in the refactor (in order of importance) are:

* Pruning dead code, via an active selection of pieces of code to be integrated
  in a brand-new repository. This is mostly relevant for (1) and (3).
* Removing Python dependencies by replacing command-line calls to
  RVizScenePublisher and wrappers, with GenSceneGraphs calls to
  `overlaySceneGraph`. This is relevant for (2).
* Documenting the repository and its code. (Do this by making a list of 
  concrete documentation goals, and soliciting feedback from others).

There may be minimal rewriting of the actual infrastructure, but we can mostly
use a copy of a functional subset of the Derendering repo. Special
consideration should be paid to keeping the modeling and inference code
modular, so that we can very easily plug-and-play different versions.

Looking ahead, if there is cross compatability for `.jl` files to be read as
Jupyter notebooks (eg. with cells delimited by special comments), we will want
to use that, and then define the tutorial sequence through a set of
self-contained `model.jl`/`infer.jl` pairs, so that we can run any single
sequence as part of the overall infrastructure, or read it as an almost
completely self-contained notebook/document for others.

# Deliverables

Each of these deliverables includes an implicit creation of documentation
describing in explicit detail how each input can be generated.

1. [X] Nishad runs push-button Makefile that runs entire pipeline
    1. [X] Nishad runs data generation pipeline, running the following:
        1. [X] Convert raw YCB-Video to canonical format
        2. [X] Generating YCB-Synthetic dataset
    2. [X] Nishad runs data download pipeline:
        1. [X] Nishad downloads converted YCB-Video dataset
        2. [X] Nishad downloads YCB-InHouse dataset
        3. [X] Nishad downloads YCB-Synthetic dataset
    3. [X] Prior from simple dynamic model, visualized over a simulated scene
    4. [X] Nishad able to recreate prior from simple dynamic model
    5. [X] Nishad able to rerun inference for a simple synthetic scene.
    6. [X] Nishad running `run_methods.jl` pipeline
    7. [X] Nishad running `run_evaluation.jl` produces raw evaluation JSONs
2. [X] Documentation
    1. [X] *README.md* containing a summary of the file format (mostly summarizing [this](https://docs.google.com/document/d/1Hb6dmcatRCZpUXJI3ImoNVos_J4IffrMxbiwPsCtft0/edit#heading=h.7rmiigac9sxb))
    3. [X] *README.md* containing core functionality for Makefile
3. [ ] (optional? also still a little vague) Streamlined one-button
       infrastructure for making new YCB-InHouse videos. Otherwise, we at least
       should do the dataset conversion when generating data, instead of
       maintaining the raw `.bag` files as part of the data, and the data
       conversion script as part of Derendering. Since the PCG GPU box is not
       available in AZ for capturing new YCB-InHouse videos, we still have some
       tech debt next time we want to create videos. This could be a good
       opportunity to finally make the data generation pipeline reproducible
       and maintained as part of the repository. Probably should separate this
       point out to a new goal.

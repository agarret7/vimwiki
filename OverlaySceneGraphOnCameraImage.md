# Motivation

Integrating the visualization used to render SceneGraphs over images as a set
of bounding boxes and contact planes. Focused on producing camera-ready
visualizations of scenegraphs, which will be/has been useful for promoting the
work to an outside audience, as well as providing crucial
[Infrastructure for SceneGraph Inference Engineering](InfrastructureForSceneGraphEngineering.md).

## Links

* [Working Branch](https://github.com/probcomp/GenSceneGraphs.jl/tree/20200805-agarret7-scenegraph-integration-2d-vis)
* [GitHub Issue](https://github.com/probcomp/GenSceneGraphs.jl/issues/183)
* [GitHub Pull Request](https://github.com/probcomp/GenSceneGraphs.jl/pull/188)

# Deliverables

1. [ ] Final code is documented, and pushed to a branch of GenSceneGraphs.jl.
2. [ ] A pull request exists for the final code, and all reviews are passed.
3. [X] The following unit tests are implemented and working.
    1. [X] Render a line
    2. [X] Render a line in 3D
    3. [X] Render a box
    4. [X] Render a SceneGraph over a synthetic scene
    5. [X] Render a video of a SceneGraph over a synthetic scene
    6. [X] Render 10 aggregated scenegraphs over a synthetic scene

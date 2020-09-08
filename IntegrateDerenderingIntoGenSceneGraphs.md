# Motivation

We've run into a few challenges with scene graph inference, as can be seen
in the [Post-NeurIPS Plans](Post-NeurIPSPlans.md#Increase). Nishad, Ben, and others can help in inference
engineering, but we need to bring the work from the isolated Derendering repo
into the broader codebase for the team. This will also serve to simplify and
solidify the existing codebase, helping us to further extend and deepen its
functionality through a refactor.

Many of these desired goals will require a further digestion of the current
work into a [sequence of tutorials](SceneGraphInferenceTutorialSequence.md). This is crucially a _tutorial_ sequence,
rather than a sequence of examples, specifically because this integration will
allow _other people_ to reuse and modify these examples for their own purposes.

The bulk of the next month will be focused on carefully documenting and
refactoring the visualization components from the SceneGraphs project.

# Links

* [Derendering Repo](https://github.com/probcomp/Derendering.git)
* [GenSceneGraphs.jl Repo](https://github.com/probcomp/GenSceneGraphs.jl)

# Subgoals

1. [ ] [Overlay SceneGraphs on Camera Image](OverlaySceneGraphOnCameraImage.md)
2. [X] [Realtime ROS RViz Visualization](RealtimeROSRVizVisualization.md) (suspended, see link)

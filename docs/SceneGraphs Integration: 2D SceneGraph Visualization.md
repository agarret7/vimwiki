## Motivation

Integrating the visualization used to render SceneGraphs over images as a set of bounding boxes and contact planes. Focused on producing camera-ready visualizations of scenegraphs, which will be/has been useful for promoting the work to an outside audience, as well as providing crucial inference debugging infrastructure.

## Deliverables

Code is documented, and pushed to a branch of GenSceneGraphs.jl. A pull request is submitted to Ben. The following unit tests are implemented and demonstrated to work on both overlaying an image and rendering the contact edges through graphviz: Render a line Render a line in 3D Render a box Render a SceneGraph over a synthetic scene Render a video of a SceneGraph over a synthetic scene Render 10 distinct scenegraphs over the first frame of a synthetic scene

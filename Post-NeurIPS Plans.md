# Housecleaning

## Motivation
Ensure reliability and ease of execution of full pipeline. Extend “one-click”
to data generation/preparation.

## Deliverables
Running make with a non-existent data directory obtains all 3 datasets (test by
making/downloading two experiments from each), runs all methods (test by
running INFER and DI+EH on each), and generates appropriate metric data.

# Improved visualization

## Motivation
Inference has become sufficiently complex that in order to proceed debugging we
need a deeper hook into visualizing the inner loop of inference. Needed in
order to demonstrate our inference procedure to the broader team and external
audiences.

## Deliverables
“run_inference.jl”, generates the standard output JSON and final visualization
(where time represents video frames), and also generates a visualization of
inference on a single video frame (where time represents eg. iterations of the
rejuvenation kernel).

## Increase reliability of structure inference

## Motivation
Encountered [“posterior leakage” bug](https://youtu.be/Rzs-lIufTMw.md) where probability of proper structure is
often 100% correct at beginning of sequence, but slowly decreases over multiple
frames. The rate of this decrease is sensitive to prob_structure_change, which
is a model parameter.

## Deliverables
Stable and reliable inference over structure in synthetic scenes, given ground
truth poses. Mostly stable inference over structure in real world scenes with 

## Increase reliability of parameter inference

## Motivation
Encountered [belief/obs decoupling” bug](https://youtu.be/TTRRez01g1Y) where
under RobustNoisyPoseLikelihood, beliefs can decouple from observation. Vikash
has requested some confirmation of this phenomenon.

## Deliverables
Beliefs stably filter out flicker, even when flicker occurs for multiple
frames, meaning beliefs return to tracking the observation when the observation
is not flickering.

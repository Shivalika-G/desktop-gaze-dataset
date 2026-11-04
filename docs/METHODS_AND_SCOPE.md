# Dataset methods

## Collection overview

The combined export covers 150 participant identifiers, P001–P150, across four distinct batches. It contains 4,452,141 indexed task observations and 699,805 indexed calibration observations, giving 5,151,946 indexed observations in total. One repeated batch upload is counted once.

An indexed observation is a row in a measurement CSV. The task and calibration branches retain their separate row coverage. The aggregate overview, participant summary and downloadable tables provide the counts behind the charts.

## Calibration and activities

The calibration inventory contains seven distance-stage labels, ten head-pose stage labels, five screen-brightness labels and fourteen mapping stage labels. The mapping coordinates read from P038 contain thirteen unique positions, including the repeated centre reference. Distance values describe instructed nominal conditions, and screen colours describe displayed brightness patterns.

The task explorer illustrates five games, twelve image stimuli and three video stimuli from the collection GUI. Its animations explain the participant actions. The recorded observations are available separately through the participant data explorer.

## Individual observation sections

P038 and P039 provide numerical sections for A1–A7 and a centre-mapping reference. Task sections begin at the earliest logged event for the selected activity identifier and extend up to twelve seconds, bounded by that activity identifier's final logged event. Image and video sections use the first corresponding stimulus identifier. The mapping section follows the centre-anchor recording.

Numeric observation values preserve their source units. Section time is expressed relative to the selected section origin. The plot and slider use the exported timestamps, with display tolerances described in the data dictionary.

## Combining batches

Participant records are combined across disjoint identifier sets. Repeated uploads are identified before aggregation. Percentages are computed from combined counts and their corresponding denominators. Numeric means and sample standard deviations are pooled using valid sample counts, group means and within-group deviations. Each field retains its own row coverage.

## Proposed workshop case study

The planned comparison uses a screen-centre baseline and the same regularized regression family trained with either instructed mapping references or interaction-derived candidate references. Both approaches are evaluated on identical held-out instructed targets, using participant-disjoint splits and whole-presentation grouping. Development data supports model selection and the selection of abstention rules.

The page distinguishes displayed target coordinates, cursor coordinates, click events and webcam observations. This supports inspection of what reference was used and which observations contribute to an evaluation.

## Individual media examples

Two linked walkthrough pages reserve space for selected screen clips, matching webcam clips, a portrait and an aligned CSV. They display clear placeholders until approved assets are configured. The main explorer already includes numerical observation sections.

The original research files remain separate from this publication package. Private filesystem paths are omitted from the published numerical exports.

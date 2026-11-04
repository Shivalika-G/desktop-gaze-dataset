# Two subject examples to add later

The main page now has two deliberately empty media cards. Their links work immediately:

- subjects/example-a.html — calibration and bubble-search walkthrough
- subjects/example-b.html — dragging and video-viewing walkthrough

They are labelled media placeholders and do not imply that a real participant is shown. The numerical P038/P039 sections in the main data explorer remain real and independent of these reserved cards.

## Recommended content for each example

| Asset | Recommended excerpt | Why it helps |
|---|---|---|
| Webcam image | One reviewed still, optional | Shows the capture appearance without requiring video playback |
| Calibration | One complete instructed-target presentation with its records | Explains the instructed reference and known screen position |
| Screen clip | A short reviewed task section, about 10 to 20 seconds | Shows exactly what was presented and how the participant acted |
| Webcam clip | Matching time interval for that screen clip | Shows the observation used by the pipeline |
| Aligned event CSV | Timestamps, target coordinates, cursor coordinates, click events and flags | Connects displayed stimulus, recorded action and observation |
| One caption | Task, participant code and what the example demonstrates | Explains the evidence without claiming unverified attention or fixation |

For Example A, calibration plus A4 bubble search connects directly to the proposed click-reference case study. For Example B, A5 dragging or A7 video viewing shows a different interaction type. Include a visible quality limitation if it is useful and accurately documented. Do not select examples to imply performance or representativeness.

## Exact suggested files

Inside media/examples/example-a/ place approved files such as:

- portrait.jpg
- screen.mp4
- webcam.mp4
- events.csv

Use the same names inside media/examples/example-b/ for the second example. These names are suggested; the site reads the paths in assets/examples-config.js. Actual clips/images are intentionally absent, so there are no broken automatic requests for these names.

If you want to show calibration and a task in one clip, preserve an explicit source time map; do not imply a continuous session if footage was spliced. Simpler first release: use one uninterrupted task interval per example, with the calibration record described or linked separately.

## Configure one example

Edit assets/examples-config.js. For the example-a object, set an actual participant_id only after selecting that participant, then fill paths and mark each reviewed asset approved:

```javascript
participant_id: 'P038',
portrait: {src:'media/examples/example-a/portrait.jpg', approved:true, alt:'Reviewed webcam still'},
screen: {src:'media/examples/example-a/screen.mp4', approved:true, caption:'A4 screen excerpt'},
webcam: {src:'media/examples/example-a/webcam.mp4', approved:true, caption:'Matching webcam excerpt'},
events: {src:'media/examples/example-a/events.csv', approved:true, caption:'Aligned observations and events'},
alignment_verified: false,
screen_zero_s: 0,
webcam_zero_s: 0
```

Keep paths relative to the repository root. An empty src or approved:false leaves the labelled placeholder. The recommended screen field is a video; the separate portrait field provides the still image. If a screen video is configured, the landing card retains its generic preview image and the real video plays on the walkthrough page.

When a participant_id is configured, the numerical-data link opens that ID in the main explorer if it exists in the inventory. Unrecognized IDs do not manufacture records.

## Align the two clips

The walkthrough includes an Align views button. It stays disabled until both clips are attached and alignment_verified:true. screen_zero_s and webcam_zero_s must correspond to the same real session instant in their respective clips. Verify offsets from timestamps and identifiable events. The button then seeks the webcam clip to screen_current_time - screen_zero_s + webcam_zero_s. Native playback remains independent; this is an offset-based alignment control, not a validated frame-perfect replay engine. Leave alignment unverified where drift, seeking or editing makes a single offset insufficient.

## Share these with me later

You can share the complete subject folder, or provide the short screen/webcam clips, relevant calibration/task logs, frame-timestamp CSVs and aligned table. Specify which images and clips may appear on the reviewer page. Keep personal names and private desktop content out of public assets. No website rebuild is required after adding the actual files and updating examples-config.js.

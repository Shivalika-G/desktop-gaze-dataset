# Editor handoff

Goal: explain the Desktop Gaze Dataset through brief captions, actual examples and purposeful interaction.

Keep the page in this order:
1. Setup image and exact title: Desktop Gaze Dataset.
2. Dataset overview: participants, recorded conditions, activities and linked streams.
3. Protocol: selectable calibration conditions and activity demonstrations.
4. Activity flow: five games, images, video and responses.
5. Example gallery: paired preview, processing preview, calibration thumbnails and interactive records.

Do not add data-download controls, raw table browsers, local file uploads or study-specific proposal text.

## Add or replace an example

Edit assets/examples-config.js. Each entry needs a unique id, title, short caption and data object. Its data contains:
- events: round, time_s, target_x, target_y, webcam_offset_ms, screen and webcam image paths.
- pipeline: three {label,src} objects for matching Stage 0/1/2 frames.
- eyes: left/right {label,src} objects from that frame.
- calibration: selected {label,src} thumbnails.
- sections: {id,title,rows}; each row uses t_s, frame_idx, image_gray_mean, cursor_x, cursor_y and time_diff_abs_ms. Keep missing values null and time sorted.

The current default data object is window.EXAMPLE_DATA in assets/example-data.js. For more examples, load another reviewed JS display-data file before examples-config.js and reference its object in another entry. Keep all image paths relative to the repository root. The gallery adapts to the list. The activity thumbnails use the first example's activities array ({id,title,src}).

## Add videos later

The current paired view is an event-snapshot viewer. Prepare matching screen/webcam excerpts, roughly 10–20 seconds each, together with original source filenames and exact clip offsets. Add video playback only after verifying alignment. Do not turn snapshots into a pseudo-recording or assume start times match.

The existing A1 illustration must retain the source order: top right, bottom left, bottom right, top left, middle left, middle right, top centre, centre. Circle for 2 seconds, square until a valid click, then a 0.5-second pause.

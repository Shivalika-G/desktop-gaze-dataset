# Adding participant faces or screen clips

The included individual panels already show real numerical results for P038 and P039. The supplied results archive has no face photographs, webcam videos or screen videos, so no real face or video is bundled.

## Publish a reviewed portrait

1. Put a display-cleared image at `media/P038.jpg` (or another filename).
2. Edit `assets/media-config.js`, inside the P038 object:

```javascript
portrait: {src:'media/P038.jpg', alt:'Approved participant example', approved:true}
```

Repeat for P039. Use relative paths. Avoid participant names, demographics, health information or private desktop content in images, filenames or captions unless explicitly approved for this publication.

## Publish a clip

Encode a short reviewed excerpt in a web-compatible format, typically MP4 with H.264 video. Put it in `media/`. In the appropriate participant's `clips` object add, for example:

```javascript
A4: {
  src:'media/P038_A4.mp4',
  approved:true,
  alignment_verified:false,
  observation_zero_video_s:0,
  caption:'Screen excerpt from P038'
}
```

The A4 key connects the clip to that participant's A4 section. Other keys are A1, A2, A3, A5, A6, A7 and mapping. The configured clip appears when its section is selected. With alignment_verified false, it is an independent media preview.

## Verify alignment before enabling shared scrubbing

`t_s=0` is the beginning of the EXPORTED numerical section, not necessarily the clip or original recording start. Set `observation_zero_video_s` to the actual time in the clip corresponding to this section origin. Verify several identifiable events against timestamp/frame alignment evidence before setting `alignment_verified:true`. Do not infer this offset from nominal FPS.

When alignment is verified, moving the observation slider also seeks the clip to `observation_zero_video_s + t_s`. The observation Play control advances observation time and seeks the clip; it is a visual scrubber, not a guarantee of frame-perfect audiovisual playback. Native video controls play media independently. This implementation assumes a verified constant time offset; re-encoded variable-timing clips or drift require more detailed mapping before using this mode.

The section plots show screen-matching time difference or image intensity. They are not gaze predictions. Cursor and target values stay separate in exported CSVs. No face media is required to use them.

## Local review only

Each participant panel includes a local file picker. Choose an image or video to preview it on your own computer. The file stays local, is not uploaded, is not saved into the repository and is not automatically synchronized. Use the media configuration and a reviewed file in media/ to publish it.

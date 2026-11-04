# Desktop Gaze Dataset Introduction

A buildless website for GitHub Pages with an interactive protocol explorer, aggregate statistics for 150 participants, individual observation sections, downloadable CSVs and an expandable examples gallery.

## New P002 walkthrough

Open subjects/example.html?id=P002 through the Examples gallery. Includes 12 calibration thumbnails, 13 clickable mapping positions, 7 activity snapshots, 4 A4 event-linked screen/webcam pairs, one matching frame through Stages 0–2, eye crops and 8 numerical sections. Continuous recordings are not bundled. See docs/ADDING_VIDEOS.md for adding clips.

## Preview

Extract the ZIP and open index.html in a modern browser. The website loads its data snapshot directly and needs no installation, server or API key.

## Publish

1. Create a GitHub repository, for example desktop-gaze-dataset.
2. Upload this folder's contents to the repository root. Keep index.html at the top level alongside assets/, data/, docs/, subjects/ and media/.
3. Include the empty .nojekyll file. If your file browser hides it, create it with GitHub's Add file command.
4. Open Settings → Pages → Deploy from a branch → main → /(root) → Save.
5. Wait for deployment and share the URL GitHub displays.

When replacing an earlier website version, use this package as the complete publication folder. Remove previous files that are absent from this package so older exports are not left at their former URLs. Your original research files can remain on your own storage.

## Included data

- 150 unique participant identifiers, P001 through P150.
- 4,452,141 indexed task observations.
- 699,805 indexed calibration observations.
- 5,151,946 indexed observations in total.
- Four distinct batch exports, with one repeated upload counted once.
- Real numerical sections for P002, P038 and P039.
- Eleven published table families, including the participant summary.

Observation counts refer to measurement CSV rows. Each coverage measure retains its own denominator. Source values in the published numerical fields are preserved.

## Add or replace examples

Each object in assets/examples-config.js creates a gallery card and a walkthrough at subjects/example.html?id=YOUR_ID. Add any number of objects with unique IDs; remove an object to remove its card. Media areas show placeholders until files are configured.

Read docs/SUBJECT_EXAMPLE_CHECKLIST.md, put selected files in media/examples/, and edit assets/examples-config.js. Suggested files per example are portrait.jpg, screen.mp4, webcam.mp4 and events.csv. Each asset has its own path and display flag. The optional media hooks inside the numerical cards use assets/media-config.js.

Editor handoff: docs/EDITOR_GUIDE.md. Collection-code overview: docs/COLLECTION_CODE_OVERVIEW.md.

## Edit the page

| Content | File |
|---|---|
| Title, introduction and resource links | index.html |
| Colours and layout | assets/style.css |
| Protocol illustrations and chart interactions | assets/app.js |
| Example gallery and walkthrough configuration | assets/examples-config.js |
| Aggregate and participant snapshot | data/dataset.json and data/dataset.js |
| Individual CSV sections | data/subjects/ |
| Data definitions | docs/DATA_DICTIONARY.md and docs/data-dictionary.html |
| Methods | docs/METHODS_AND_SCOPE.md and docs/methods.html |

The JSON and JavaScript snapshots contain the same data. Keep them synchronized when replacing numerical exports. Charts, CSV previews and downloads use relative paths so repository project URLs work.

## Verification

The package includes tools/core.test.cjs. With Node.js available, run node --test tools/core.test.cjs. The website itself needs no Node.js installation. Desktop and narrow-screen layouts, walkthrough links, placeholder images, selectors and table navigation have been checked.

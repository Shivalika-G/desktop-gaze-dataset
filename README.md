# Desktop Gaze Dataset

A concise, visual GitHub Pages introduction. Sections: collection setup, dataset overview, interactive protocol, seven-activity flow and example gallery. No CSV files, download buttons, table browser or file-upload controls are included. Only selected display records and images are bundled.

## Open or publish

Open index.html to preview. Upload the package contents to the repository root, including .nojekyll. Enable GitHub Pages from the main branch and /(root). No installation or build is required.

When replacing an earlier site, remove old data/, subjects/ and unused assets from the publication repository so previous downloadable files are not left at their old addresses. Keep your original research archives separately.

## Edit

| Content | File |
|---|---|
| Title, overview, introduction and layout | index.html |
| Appearance and responsive styling | assets/style.css |
| Setup illustration | assets/setup.svg |
| Protocol illustrations | assets/protocol.js |
| Recorded calibration positions/counts | assets/protocol-data.js |
| Example list, labels and captions | assets/examples-config.js |
| Selected example images and measurements | assets/example-data.js and media/examples/ |
| Gallery interactions | assets/site.js |

The setup image is an illustration, not a photograph of the actual collection room. Replace its img source in index.html with an approved setup photograph when available. Keep the caption accurate.

P002 is one illustrative example, labelled Example 01. It does not define the dataset's identity. Add further entries with unique IDs in examples-config.js and corresponding display data.

The calibration defaults to the recorded inventory (7 distance, 10 pose, 5 brightness and 14 mapping stages). The optional Calibration source detail also exposes the supplied-code sequence; it does not change aggregate counts. Activity 1 includes all eight positions in source order. Other task demonstrations are schematic.

The public page has no data-export controls. Publicly displayed assets remain technically retrievable; do not include private source tables or full participant archives in this package.

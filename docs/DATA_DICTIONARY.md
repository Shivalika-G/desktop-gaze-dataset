# Data dictionary

## Aggregate counts

The combined export covers 150 participant identifiers across four distinct batches. Indexed observations are measurement-table rows. Task and calibration measurements have separate denominators.

| Field | Meaning |
|---|---|
| subjects_discovered | Participant identifiers indexed in the combined export |
| indexed_task_observations | Task measurement-table rows |
| indexed_calibration_observations | Calibration measurement-table rows |
| indexed_total_observations | Task plus calibration measurement-table rows |
| rows in coverage tables | Denominator for the corresponding measure and branch |
| true / false / unknown | Recorded categories for a coverage measure |
| true_pct_all | True count divided by all rows in the measure's denominator |
| true_pct_known | True count divided by true plus false |
| grouping_denominator | Row count represented by one grouping column within a branch |

## Participant summary

The participant summary contains each participant identifier and session identifier, task and calibration row counts, and face-detection counts with their corresponding denominators. The displayed percentages are computed from those counts.

## Short observation sections

Each CSV in data/subjects/ contains selected numeric observations for its participant and activity. Section times are relative to the selected excerpt origin.

| Field | Unit and interpretation |
|---|---|
| t_s | Seconds from the selected section origin |
| frame_idx | Source webcam or calibration video frame index |
| time_diff_abs_ms | Absolute webcam-to-screen match time difference, in milliseconds |
| face_detected | Source face-detection flag, 1 or 0 |
| image_gray_mean | Mean grayscale intensity of the processed webcam image, on a 0–255 scale |
| cursor_x / cursor_y | Cursor coordinates in pixels |
| target_x / target_y | Task target or instructed calibration coordinates in pixels |
| target_visible | Recorded calibration target-visibility flag |
| target_state_age_ms | Age of the task activity-state observation, in milliseconds |
| match_quality_flag | Source task matching category |

Blank CSV values correspond to null in JSON. The plots maintain gaps where a value is absent or where timestamps are separated by more than 0.25 seconds. The slider selects the nearest observation within 0.12 seconds, and nearby event captions use a 0.25-second display window. Red marks at the plot base correspond to face_detected=0. These tolerances describe the website display.

## Table families

The published tables contain aggregate and participant missingness, coverage flags, grouping counts, numeric statistics, recording timing, measurement-table inventory and a participant summary. Each table retains its field-specific coverage and denominators. The recording-time fields describe indexed timestamp spans and intervals.

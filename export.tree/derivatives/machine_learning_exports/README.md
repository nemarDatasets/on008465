# NeuralEcho MACS machine-learning exports

This derivative contains by-subject machine-learning arrays exported from the
NeuralEcho MACS EEG preprocessing workflow. It is intended for users who want to
train or benchmark decoding models without reloading EEGLAB `.set` files.

Directory layout:

```text
machine_learning_exports/
  basic_filter/
  stable/
  ml_conservative/
```

Each preprocessing version contains 30 subject folders (`S01` to `S30`) plus
top-level metadata files:

- `eeg.npy`: subject-level float32 EEG array, shaped `(trials, channels, time)`.
- `labels.csv`: trial-level labels aligned with `eeg.npy`.
- `labels.npz`: integer label arrays for NumPy/PyTorch/TensorFlow.
- `channels.csv`: retained channel labels and coordinate metadata.
- `times.npy`: epoch time axis in milliseconds.
- `metadata.json`: subject-level shape and sampling metadata.
- `all_subjects_labels.csv`: concatenated trial labels.
- `manifest.csv`: source export manifest.
- `classes.json`: class maps and event-code maps.
- `extraction_summary.json`: dataset-level summary.

Version summary:

- `basic_filter`: minimal preprocessing, intended to preserve signal morphology.
- `stable`: standard artifact attenuation and retained-run filtering for
  mechanistic analysis.
- `ml_conservative`: conservative machine-learning-oriented preprocessing with
  slow-wave preservation and no ASR burst correction.

The original BIDS-compatible EEG files remain in the dataset root. EEGLAB
preprocessing derivatives are stored separately under
`derivatives/eeglab_preprocessed/`.

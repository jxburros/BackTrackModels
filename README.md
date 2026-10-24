# BackTrackModels
Custom Models for BackTrack

Models trained at home from BackTrack's TRAIN tab, before they go into BackTrack's `weights/`
(where the release workflow picks them up) and Song Deck's bundled plugins.

| File here | Shipped as | Note F on 60 unseen rendered songs | Song Deck built-in |
| --- | --- | --- | --- |
| `surveil-drums-0.1.0.gguf` | `surveil-drums-0.2.0.gguf` (BackTrack 0.6.0, Song Deck 0.20.0) | 0.848 (released drums 0.1.0: 0.837) | 0.527 |
| `surveil-bass-0.1.0.gguf` | `surveil-bass-0.1.0.gguf` | 0.472 | 0.211 |
| `surveil-melody-0.1.0.gguf` | `surveil-melody-0.1.0.gguf` | 0.917 instrumental leads, 0.684 guide singer | 0.757, 0.372 |

The drums file here says `general.version` 0.1.0, a version BackTrack had already released for a
different drum model, so it ships as 0.2.0 with only that field changed. To avoid this next time,
set the TRAIN tab's model version (the pipeline's `model.version`) before the run. How they were
scored: BackTrack's `weights/README.md`.

# Training run 20261020-150014

**PROMOTED to runs/best: note F 0.661 (first model: nothing to beat)**

Model: `C:\Users\Admin\backtrack-training\runs-melody\20261020-150014\surveil-melody-0.1.0.gguf` (Surveil melody 0.1.0).
Previous best: none.

## Data

- Dataset `C:\Users\Admin\backtrack-training\sd-melody`: 400 songs (test 45, train 308, valid 47)
- ACE-Step performances: 0 takes on 0 songs
- Training: 30 epochs, best epoch 26, valid note F 0.745, device cuda, 0.3 min per epoch

## Separated test split, through the binary (training.evaluate)

Note F (a note counts when it starts within ±50 ms at the same pitch) on the melody separated from the mix (what Song Deck sends).

| | this run |
|---|---:|
| **note F** | 0.661 |
| precision | 0.745 |
| recall | 0.594 |
| items | 41 |

The Song Deck column comes from Song Deck's own harness (next section), on the same songs and tolerance.

## Parity

PyTorch and the binary agree.

## Training history

| epoch | loss | valid note F | seconds |
|---:|---:|---:|---:|
| 1 | 0.7939 | 0.716 | 20 |
| 2 | 0.0636 | 0.722 | 19 |
| 3 | 0.0573 | 0.723 | 19 |
| 4 | 0.0564 | 0.722 | 20 |
| 5 | 0.0562 | 0.724 | 19 |
| 6 | 0.0550 | 0.716 | 19 |
| 7 | 0.0539 | 0.725 | 19 |
| 8 | 0.0533 | 0.726 | 19 |
| 9 | 0.0511 | 0.727 | 19 |
| 10 | 0.0504 | 0.735 | 19 |
| 11 | 0.0499 | 0.734 | 19 |
| 12 | 0.0507 | 0.730 | 19 |
| 13 | 0.0492 | 0.731 | 19 |
| 14 | 0.0503 | 0.734 | 19 |
| 15 | 0.0479 | 0.737 | 19 |
| 16 | 0.0485 | 0.735 | 19 |
| 17 | 0.0482 | 0.737 | 19 |
| 18 | 0.0472 | 0.739 | 19 |
| 19 | 0.0472 | 0.739 | 19 |
| 20 | 0.0478 | 0.744 | 19 |
| 21 | 0.0491 | 0.743 | 19 |
| 22 | 0.0473 | 0.744 | 19 |
| 23 | 0.0469 | 0.743 | 19 |
| 24 | 0.0474 | 0.745 | 19 |
| 25 | 0.0463 | 0.745 | 19 |
| 26 | 0.0455 | 0.745 | 19 |
| 27 | 0.0457 | 0.744 | 19 |
| 28 | 0.0461 | 0.742 | 19 |
| 29 | 0.0474 | 0.743 | 19 |
| 30 | 0.0459 | 0.743 | 19 |

## Steps

| step | status | minutes | notes |
|---|---|---:|---|
| render | done | 5.6 | 400 songs rendered, 0.8 s per song [log](render.log) |
| perform | done | 0.0 | skipped: dataset:perform has no --parts [log](perform.log) |
| train | done | 21.5 |  [log](train.log) |
| evaluate | done | 1.0 |  [log](evaluate.log) |
| parity | done | 0.1 |  [log](parity.log) |
| report | done | 0.0 |  [log](report.log) |

## Licence record (audio.sources)

- Song Deck dataset sd-melody (Song Deck 0.17.0, 2026-10-20T20:00:57.827Z): Rendered by Song Deck from its own compositions and instruments; record of instrument sources per song in songs[].stems[].instrument (sound bank licences: soundbank/CREDITS.txt)

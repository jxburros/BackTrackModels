# Training run 20261020-134608

**PROMOTED to runs/best: note F 0.452 (first model: nothing to beat)**

Model: `C:\Users\Admin\backtrack-training\runs-bass\20261020-134608\surveil-bass-0.1.0.gguf` (Surveil bass 0.1.0).
Previous best: none.

## Data

- Dataset `C:\Users\Admin\backtrack-training\sd-bass`: 400 songs (test 45, train 308, valid 47)
- ACE-Step performances: 0 takes on 0 songs
- Training: 30 epochs, best epoch 21, valid note F 0.685, device cuda, 0.3 min per epoch

## Separated test split, through the binary (training.evaluate)

Note F (a note counts when it starts within ±50 ms at the same pitch) on the bass separated from the mix (what Song Deck sends).

| | this run |
|---|---:|
| **note F** | 0.452 |
| precision | 0.474 |
| recall | 0.431 |
| items | 39 |

The Song Deck column comes from Song Deck's own harness (next section), on the same songs and tolerance.

## Parity

PyTorch and the binary agree.

## Training history

| epoch | loss | valid note F | seconds |
|---:|---:|---:|---:|
| 1 | 0.8104 | 0.549 | 19 |
| 2 | 0.0459 | 0.583 | 19 |
| 3 | 0.0429 | 0.562 | 19 |
| 4 | 0.0419 | 0.579 | 19 |
| 5 | 0.0404 | 0.569 | 19 |
| 6 | 0.0382 | 0.611 | 19 |
| 7 | 0.0393 | 0.614 | 19 |
| 8 | 0.0381 | 0.633 | 19 |
| 9 | 0.0376 | 0.645 | 19 |
| 10 | 0.0371 | 0.640 | 19 |
| 11 | 0.0369 | 0.628 | 19 |
| 12 | 0.0361 | 0.637 | 19 |
| 13 | 0.0357 | 0.651 | 19 |
| 14 | 0.0355 | 0.651 | 19 |
| 15 | 0.0360 | 0.669 | 19 |
| 16 | 0.0351 | 0.657 | 19 |
| 17 | 0.0347 | 0.676 | 19 |
| 18 | 0.0353 | 0.657 | 19 |
| 19 | 0.0352 | 0.655 | 19 |
| 20 | 0.0336 | 0.671 | 19 |
| 21 | 0.0346 | 0.685 | 19 |
| 22 | 0.0345 | 0.668 | 19 |
| 23 | 0.0343 | 0.682 | 19 |
| 24 | 0.0335 | 0.682 | 19 |
| 25 | 0.0336 | 0.683 | 18 |
| 26 | 0.0340 | 0.684 | 19 |
| 27 | 0.0333 | 0.681 | 19 |
| 28 | 0.0330 | 0.683 | 19 |
| 29 | 0.0337 | 0.681 | 19 |
| 30 | 0.0336 | 0.682 | 19 |

## Steps

| step | status | minutes | notes |
|---|---|---:|---|
| render | done | 0.0 |  [log](render.log) |
| perform | done | 0.0 | skipped: dataset:perform has no --parts [log](perform.log) |
| train | done | 12.8 |  [log](train.log) |
| evaluate | done | 1.0 |  [log](evaluate.log) |
| parity | done | 0.1 |  [log](parity.log) |
| report | done | 0.0 |  [log](report.log) |

## Licence record (audio.sources)

- Song Deck dataset sd-bass (Song Deck 0.17.0, 2026-10-20T18:32:08.228Z): Rendered by Song Deck from its own compositions and instruments; record of instrument sources per song in songs[].stems[].instrument (sound bank licences: soundbank/CREDITS.txt)

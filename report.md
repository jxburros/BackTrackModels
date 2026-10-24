# Training run 20261019-153649

**PROMOTED to runs/best: mean_class_f 0.812 (first model: nothing to beat)**

Model: `C:\Users\Admin\backtrack-training\runs\20261019-153649\surveil-drums-0.1.0.gguf` (Surveil drums 0.1.0).
Previous best: none.

## Data

- Dataset `C:\Users\Admin\backtrack-training\sd-drums`: 400 songs (test 45, train 308, valid 47)
- ACE-Step performances: 400 takes on 400 songs, mean agreement 0.22
- Performed audio in training: 186 of 357 takes, 8.0 of 365.8 min accepted (train 6.8, valid 0.4; agreement F ≥ 0.6, offset strength ≥ 0.2); rejected takes: weak_offset 72, no_window 99
- Training: 30 epochs, best epoch 25, valid mean class F 0.835, device cuda, 0.1 min per epoch

## Separated test split, through the binary (training.evaluate)

Onset F per class within ±50 ms on the drums separated from the mix (what Song Deck sends).

| class | this run | Song Deck built-in |
|---|---:|---:|
| kick | 0.986 | 0.774 |
| snare | 0.897 | 0.527 |
| toms | 0.794 | 0.122 |
| hihat_closed | 0.732 | 0.495 |
| hihat_open | 0.709 | 0.368 |
| crash | 0.877 | 0.188 |
| ride | 0.692 | 0.000 |
| **overall F** | 0.826 | 0.495 |
| **mean class F** | 0.812 | 0.354 |
| items | 38 | 38 |

The Song Deck column comes from Song Deck's own harness (next section), on the same songs and tolerance.

## Performed test windows (ACE-Step takes)

Scored only inside the windows whose agreement passed `--min-agreement` (ACE-Step does not play every note as written; outside those windows the labels are not trusted).

| class | this run |
|---|---:|
| kick | 0.769 |
| snare | – |
| toms | – |
| hihat_closed | 0.716 |
| hihat_open | 0.000 |
| crash | – |
| ride | – |
| **overall F** | 0.709 |
| **mean class F** | 0.495 |
| items | 21 |

Scored: accepted_windows_only True, items 21, accepted_minutes 0.8, minutes 21.5, min_agreement 0.6, min_offset_strength 0.2

## Song Deck's harness (npm run eval:datasets, --input separated)

Whole songs; this run's model served by `backtrack-surveil serve`. Its numbers can differ a little from training.evaluate's (Song Deck maps and clips notes its own way); compare within a column pair.

| class | Song Deck built-in | BackTrack (this run) |
|---|---:|---:|
| kick | 0.774 | 0.986 |
| snare | 0.527 | 0.897 |
| toms | 0.122 | 0.794 |
| hihat_closed | 0.495 | 0.732 |
| hihat_open | 0.368 | 0.709 |
| crash | 0.188 | 0.877 |
| ride | 0.000 | 0.692 |
| **overall F** | 0.495 | 0.826 |
| **mean class F** | 0.354 | 0.812 |
| items | 38 | 38 |

## Parity

PyTorch and the binary agree.

## Training history

| epoch | loss | valid mean class F | seconds |
|---:|---:|---:|---:|
| 1 | 0.1855 | 0.502 | 10 |
| 2 | 0.0755 | 0.620 | 9 |
| 3 | 0.0631 | 0.682 | 9 |
| 4 | 0.0581 | 0.764 | 9 |
| 5 | 0.0546 | 0.776 | 9 |
| 6 | 0.0536 | 0.761 | 9 |
| 7 | 0.0516 | 0.777 | 9 |
| 8 | 0.0511 | 0.812 | 9 |
| 9 | 0.0498 | 0.760 | 9 |
| 10 | 0.0492 | 0.798 | 9 |
| 11 | 0.0482 | 0.802 | 9 |
| 12 | 0.0481 | 0.802 | 9 |
| 13 | 0.0471 | 0.783 | 9 |
| 14 | 0.0468 | 0.805 | 9 |
| 15 | 0.0466 | 0.823 | 9 |
| 16 | 0.0463 | 0.821 | 9 |
| 17 | 0.0457 | 0.801 | 9 |
| 18 | 0.0455 | 0.815 | 9 |
| 19 | 0.0448 | 0.829 | 9 |
| 20 | 0.0441 | 0.822 | 9 |
| 21 | 0.0443 | 0.833 | 9 |
| 22 | 0.0441 | 0.826 | 9 |
| 23 | 0.0440 | 0.829 | 9 |
| 24 | 0.0433 | 0.828 | 9 |
| 25 | 0.0433 | 0.835 | 9 |
| 26 | 0.0433 | 0.830 | 9 |
| 27 | 0.0431 | 0.834 | 9 |
| 28 | 0.0433 | 0.831 | 9 |
| 29 | 0.0433 | 0.832 | 9 |
| 30 | 0.0432 | 0.832 | 9 |

## Steps

| step | status | minutes | notes |
|---|---|---:|---|
| render | done | 5.7 | 399 songs rendered, 0.8 s per song [log](render.log) |
| perform | done | 89.2 | 400 takes, 13 s per take; judged by backtrack-surveil=http://127.0.0.1:59548 [log](perform.log) |
| train | done | 14.6 |  [log](train.log) |
| evaluate | done | 2.4 |  [log](evaluate.log) |
| parity | done | 0.1 |  [log](parity.log) |
| report | done | 0.0 |  [log](report.log) |

## Licence record (audio.sources)

- ACE-Step performances of Song Deck renders (ace-step-api, acestep-v15-turbo), dataset sd-drums; licence checked by the owner 2026-10-18
- Song Deck dataset sd-drums (Song Deck 0.17.0, 2026-10-19T20:13:27.283Z): Rendered by Song Deck from its own compositions and instruments; record of instrument sources per song in songs[].stems[].instrument (sound bank licences: soundbank/CREDITS.txt)

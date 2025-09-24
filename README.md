# CSCI-166

## DQN on Breakout — Early vs Later (short run)

Watch how performance improves as training progresses:

| Episode | Model              | Preview                                      | Video |
|--------:|--------------------|----------------------------------------------|-------|
| Early   | Near-random        | <img src="videos/IMG_2523.jpeg" width="120"/> | [▶ Watch](https://github.com/ramonadamec/CSCI-166/blob/main/videos/early_breakout.mp4?raw=1) |
| Later   | Emerging strategy  | <img src="videos/IMG_2524.jpeg" width="120"/> | [▶ Watch](https://github.com/ramonadamec/CSCI-166/blob/main/videos/later_breakout.mp4?raw=1) |

> Videos and thumbnails are named to match the run (early/later).  
> If a browser can’t stream inline, the link will still open the file directly.

### Notes
- Env: `ALE/Breakout-v5`
- Preprocessing: SB3 `AtariWrapper` (reward clip, `noop_max=30`) → ImageToPyTorch → Frame stack (4) → FIRE reset  
- Model: DQN (84×84 grayscale, 4 frames; conv → 512 → `n_actions=4`)
- Quick-run config: `replay_start=1k`, `ε-decay=10k`, target sync every `500` frames
- Recording: evaluation mode, ~12s per video at 15 fps with a slight slow-down for clarity

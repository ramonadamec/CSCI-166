# DQN on Breakout — Early vs Later (short run)

Watch how performance improves as training progresses:

| Episode | Model              | Video |
|--------:|--------------------|-------|
| Early   | Near-random        | [▶ Watch](https://github.com/<USER>/<REPO>/raw/main/videos/early_breakout.webm) |
| Later   | Emerging strategy  | [▶ Watch](https://github.com/<USER>/<REPO>/raw/main/videos/later_breakout.webm) |

### Notes
- Env: `ALE/Breakout-v5`
- Preprocessing: SB3 `AtariWrapper` (reward clip, `noop_max=30`) → ImageToPyTorch → frame stack (4) → FIRE reset  
- Quick-run config: `replay_start=1k`, `ε`-decay `10k`, target sync `500`
- Recording: eval mode, ~12 s at 15 fps, slowed for clarity

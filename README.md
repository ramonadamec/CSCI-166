# DQN on Breakout — Early vs Later (short run)

Two short clips from adapting the Pong starter to **ALE/Breakout-v5**.

**Early (near-random):**  
<video src="videos/early_breakout.webm" controls width="480"></video>  
[▶ Download/View Early (mp4 backup)](videos/early_breakout.mp4)

**Later (emerging strategy):**  
<video src="videos/later_breakout.webm" controls width="480"></video>  
[▶ Download/View Later (mp4 backup)](videos/later_breakout.mp4)

### Notes
- Env: `ALE/Breakout-v5`
- Preprocessing: SB3 `AtariWrapper` (reward clip, `noop_max=30`) → ImageToPyTorch → Frame stack (4) → FIRE reset  
- Model: DQN (84×84 grayscale, 4 frames; conv → 512 → `n_actions=4`)
- Quick-run config: `replay_start=1k`, `ε-decay=10k`, target sync every `500` frames
- Recording: evaluation mode, ~12s per video at 15 fps with a slight slow-down for clarity

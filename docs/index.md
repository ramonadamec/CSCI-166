# DQN on Breakout — Early vs Later (inline viewer)

Watch how performance improves as training progresses:

| Episode | Model              | Preview                                   | Video |
|--------:|--------------------|-------------------------------------------|-------|
| <a id="early"></a>Early   | Near-random        | <img src="/videos/IMG_2523.jpeg" width="160"/> | <video controls width="480"><source src="/videos/early_breakout.mp4" type="video/mp4"><source src="/videos/early_breakout.webm" type="video/webm">Your browser doesn’t support embedded video. <a href="/videos/early_breakout.mp4">Download MP4</a>.</video> |
| <a id="later"></a>Later   | Emerging strategy  | <img src="/videos/IMG_2524.jpeg" width="160"/> | <video controls width="480"><source src="/videos/later_breakout.mp4" type="video/mp4"><source src="/videos/later_breakout.webm" type="video/webm">Your browser doesn’t support embedded video. <a href="/videos/later_breakout.mp4">Download MP4</a>.</video> |

---

### Notes
- Env: `ALE/Breakout-v5`
- Preprocessing: SB3 `AtariWrapper` (reward clip, `noop_max=30`) → ImageToPyTorch → Frame stack (4) → FIRE reset  
- Model: DQN (84×84 grayscale, 4 frames; conv → 512 → `n_actions=4`)  
- Quick-run config: `replay_start=1k`, `ε-decay=10k`, target sync every `500` frames  

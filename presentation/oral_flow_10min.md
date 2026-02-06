# 10-Minute Oral Flow Guide

Use this as a speaking script map for `main.pdf` (17 slides).

## Timing Plan (Total = 10:00)

| Slide | Title | Target time | Cumulative |
|---|---|---:|---:|
| 1 | Title | 0:20 | 0:20 |
| 2 | Project Context | 0:35 | 0:55 |
| 3 | Roadmap (10 minutes) | 0:20 | 1:15 |
| 4 | Dataset Structure | 0:45 | 2:00 |
| 5 | Preprocessing Pipeline | 0:40 | 2:40 |
| 6 | Trajectory Exploration Before Training | 0:45 | 3:25 |
| 7 | Why LSTM for This Task? | 0:45 | 4:10 |
| 8 | Final Architecture and Training Setup | 0:40 | 4:50 |
| 9 | Planned Ablations | 0:35 | 5:25 |
| 10 | Evaluation Protocol | 0:30 | 5:55 |
| 11 | Practical Issues During Development | 0:40 | 6:35 |
| 12 | Exploding Gradients and Fix | 0:40 | 7:15 |
| 13 | Runs R1 and R2 | 0:40 | 7:55 |
| 14 | Runs R3 and R4 | 0:45 | 8:40 |
| 15 | Quantitative Summary and Interpretation | 0:40 | 9:20 |
| 16 | Conclusion | 0:25 | 9:45 |
| 17 | Next Steps | 0:15 | 10:00 |

## Per-Slide Speaking Cues

1. **Title**
   - One sentence: task + goal + key outcome teaser.

2. **Project Context**
   - Say what is classified (trajectory-level class, not timestep label).
   - Mention course constraint (LSTM project in UE5).

3. **Roadmap**
   - Preview: data -> model -> experiments -> issues -> results -> conclusion.

4. **Dataset Structure**
   - Emphasize balanced classes and tensor shape `(256,150,20)`.
   - One sentence on feature groups (pose/velocity/hole pose).

5. **Preprocessing Pipeline**
   - State split and seed quickly.
   - Stress train-only statistics for normalization.

6. **Trajectory Exploration**
   - Left: spatial behavior; right: temporal dynamics.
   - Key message: classes show separability patterns.

7. **Why LSTM**
   - Link directly to course: sequence dependencies + RNN training issues.
   - Mention gates as stability/memory mechanism.

8. **Final Architecture**
   - Read only 4 essentials: 2-layer LSTM, hidden 64, dropout 0.2, Adam.
   - Skip literal hyperparameter reading if short on time.

9. **Planned Ablations**
   - Explain this is controlled experimentation, not random tuning.
   - Point to progression R1 -> R4.

10. **Evaluation Protocol**
    - Clarify internal test size and external teacher test as final benchmark.

11. **Practical Issues**
    - Point to two curves as “what went wrong”.
    - Transition line: “Then we handled gradient instability directly.”

12. **Exploding Gradients**
    - Show spikes first, then clipping fix in one line.

13. **Runs R1/R2**
    - Contrast baseline vs first strong improvement.

14. **Runs R3/R4**
    - Contrast regularization gain (R3) vs stability gain (R4).

15. **Quantitative Summary**
    - Give only two takeaways: “dropout helps generalization”, “clipping stabilizes training”.

16. **Conclusion**
    - Repeat one final message: methodical ablation enabled explainable gains.

17. **Next Steps**
    - End with external test + feature-influence analysis.

## Fast Recovery Rules (if you are behind time)

- If behind by ~30 seconds: compress slides 8 and 10 to one sentence each.
- If behind by ~60 seconds: skip detailed commentary on slide 13 and go straight to slide 14+15.
- Never skip slide 15 (summary) or slide 17 (close).

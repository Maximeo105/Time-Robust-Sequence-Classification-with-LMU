# Time-Robust-Sequence-Classification-with-LMU
Inter-event interval + content; LMU vs LSTM baseline

Goal : Compare a continuous-time Legendre Memory Unit (LMU) againts an LSTM on a 48-class task where labels depend on both event content and inter-event intervals. 

We test: 
1. Convergence speed (number of epochs needed to reach a low val loss)
2. Generalization to different sampling (train on one frame duration range, evaluate on a shifted range with the same total lenght)

Highlights:
Synthetic dataset with controlled gaps (gap_a, gap_b, gap_c) and fixed event order.
Variable frame durations [dt_min, dt_max]; total frames vary per sequence but not the total duration
Two models use the same per-step CNN features; LSTM addionally gets fed the cumulative time 

# Time-Robust-Sequence-Classification-with-LMU

## Overview

This project compares a Legendre Memory Units (LMU) againts a LSTM on a temporal sequence classification task where labels depend on both event content (images) and inter-event timing intervals (on the order of seconds) 

key contribution : LMUs process continuous-time inputs accurately with small datasets and remain stable under change to timing discretization (dt), whereas LSTMs are less accurate and doesn't remain stable under different dt. 
This can help artificial intelligence agents to better predict where to direct their attention or interpret inputs based of real word timing. 

## Motivation

Standard RNNs (including LSTMs) struggle with irregular sampling because they assume fixed timesteps. LMUs, based on the Legendre Delay Network, naturally handle variable dt through continuous-time state updates. 

## Task
- **Input**: Sequence of images (circles/squares) separated by variable gaps of time
- **Output**: 48-class classification based on gap durations (binned into ranges)
- **Challenge**: Models must integrate elapsed time, not just frame count

## Results
- LMU maintains accuracy across different sampling rates (5-20 Hz -> 2.5-10 Hz, 10-40 Hz) where the LSTM accuracy drops significantly under the same shifts. 
- LMU optimal accuracy is reached with fewer epochs compared to the LSTM
- LMU accuracy is better than the LSTM on both sample size (250-500) holding around 60% accuracy on both size, whereas the LSTM is around 20% and 40% for each setting respectively. 


This prototype was developed with assistance from generative AI for rapid prototyping. 
Core algorithms and experimental design are orignal work. 

## References
- Voelker & Eliasmtih (2018). *Legendre Memory Units*

## Related Work
This self-directed project builds on my honours thesis work on temporal sequence encoding with Bidirectional Associative Memory (Ouimet, 2024). 

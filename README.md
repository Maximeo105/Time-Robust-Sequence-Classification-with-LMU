# Time-Robust-Sequence-Classification-with-LMU

## Overview

This self directed project compares a Legendre Memory Units (LMU) againts a LSTM on a temporal sequence classification task where labels depend on both event content (images) and inter-event timing intervals (on the order of seconds) 

key contribution : LMUs process continuous-time inputs accurately with small datasets and remain stable under change to timing discretization (dt), whereas LSTMs are less accurate and doesn't remain stable under different dt. 
This can help artificial intelligence agents to better predict where to direct their attention or interpret inputs based of real word timing. 

## Motivation

The human brain doesn't rely on constant, regular inputs; yet it effortlessly processes timing information across wildly varying conditions: 
- Robustness to sampling changes: A gamer whose FPS drops from 60 to 45 doesn't suddenly lose the ability to play. Their brain adapts to the new temporal resolution without catastrophic performance loss.
- Timing as contextual information: When someone knocks on your door, the interval pattern alone can tell you whether it's the familiar mailman or an unknown visitor; no visual information needed.
- Timing for predictive action: Catching a football doesn't require tracking the ball every millisecond. You estimate timing, look away, reposition and readjust; integrating sparse temporal samples into fluid actions.
- Learned temporal models: In competitive games, players internalize opponent behavior patterns. A shooter player might know they have about 2 seconds before an enemy re-peeks a corner, allowing strategic repositioning based purely on learned timing.
  
Standard RNNs (including LSTMs) struggle with irregular sampling because they assume fixed timesteps. LMUs, based on the Legendre Delay Network, naturally handle variable dt through continuous-time state updates more closely matching how biological systems process time.
Thus, we test the ability of such network to distinguish inputs based only on timing informations. 

## Task
- **Input**: Sequence of images (circles/squares) separated by variable gaps of time
- **Output**: 48-class classification based on gap durations (binned into ranges)
- **Challenge**: Models must integrate elapsed time, not just frame count

## Results
- LMU maintains accuracy across different sampling rates (5-20 Hz -> 2.5-10 Hz, 10-40 Hz) where the LSTM accuracy drops significantly under the same shifts. 
- LMU optimal accuracy is reached with fewer epochs compared to the LSTM
- LMU accuracy is better than the LSTM on both sample size (250-500) holding around 60% accuracy on both size, whereas the LSTM is around 20% and 40% for each setting respectively. 


This prototype was developed with assistance from generative AI for rapid prototyping. 
Experimental designs are original work. 

## References
- Voelker & Eliasmith (2018). *Legendre Memory Units*
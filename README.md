# radio-adblock
Adblocker for FM radio

training step:

with labeled audio recordings from sdr tuned to radio station:
1. compute features (mel-spectrum? chroma features? NMF?)
2. train model on features w/ to learn 'radio' / 'music' / 'noise'
3. incorporate prior knowledge:
   - radio advertisements usually last 10, 15, 30, or 60 seconds
   - advertisements should be identical, so try to come up with features that match across repetitions of advertisement (subsequence DTW?)

operation step:

with input audio stream from sdr tuned to radio station:
1. gather observations, using feature extractors
2. model current state and transitions using e.g. Hidden Markov Model
3. play audio stream, but if ad currently playing, suppress audio (or replace with your own music)

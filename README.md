# essentia2keras
load audio features analyzed via essentia to train neural network for wavetable generation

this is intended to receive a .yaml file resultant from analyzing an audio file via timbreSpaceAnalysis (https://github.com/nvssynthesis/timbreSpaceAnalysis).
essentia2keras uses the .yaml file to train a neural network, mapping pitch, loudness, and timbral features onto modified spectra.
essentia2keras creates a .h5 neural network file.
the intended use of the network is to be used to synthesize wavetables in realtime using wtianns~ (https://github.com/nvssynthesis/wtianns), a pd external.

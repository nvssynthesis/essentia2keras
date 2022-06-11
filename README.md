# essentia2keras
load audio features analyzed via essentia to train neural network for wavetable generation

this is intended to receive a .yaml file resultant from analyzing an audio file via timbreSpaceAnalysis (https://github.com/nvssynthesis/timbreSpaceAnalysis).
essentia2keras uses the .yaml file to train a neural network, mapping pitch, loudness, and timbral features onto modified spectra.
essentia2keras creates a .h5 neural network file.
the intended use of the network is to be used to synthesize wavetables in realtime using wtianns~ (https://github.com/nvssynthesis/wtianns), a pd external.

in order to use the network with wtianns~, you must also convert it to a shared object file using keras2c (https://github.com/f0uriest/keras2c)
keras2c will create a .h file and 2 .c files; you need to compile the network file (the one that's not test_suite.c) 
if you have keras2c, you can compile using 
cc -bundle -undefined suppress -flat_namespace -o (name_of_network).so (path to network c file) (path to keras2c/include/libkeras2c.a). 
for the time being, make sure to name the network the same name as the network file output by essentia2keras.

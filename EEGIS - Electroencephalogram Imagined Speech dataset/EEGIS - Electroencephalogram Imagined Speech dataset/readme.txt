EEGIS - Electroencephalogram Imagined Speech dataset


Contributors: Edgar Lara Arellano, Andras Takacs, Juvenal Rodríguez-Reséndiz.
Institution: Universidad Autónoma de Querétaro.


This Dataset contains Imagined Speech EEG signals.

The signals were recorded from 10 participants while they have to imagine saying 8 different Spanish words plus a rest sta:
- 'Sí'
- 'No'
- 'Baño'-
- 'Hambre'
- 'Sed'
- 'Ayuda'
- 'Dolor'
- 'Gracias'
plus a rest state.

The words translated are 'Yes', 'No', 'Bath', 'Hunger', 'Thirst', 'Help', 'Pain', 'Thank you'.

The EEG signals were recorded using the Emotiv EPOC+ device, equipped with 14 channels and operated at a sampling rate of 128 Hz.
The data consist of chunk records of 1 second each, for that reason, data has a shape of 14 channels and 128 samples (128 Hz x 1 second) for each recording.

Also, each chunk was filtered into five frequency bands: delta, theta, alpha, beta and gamma.


Therefore, the dataset has 6 folders (raw data plus five frequency folders) where each folder contains nine folders (one corresponding to each class) where each folder have its corresponding CSV files.

Class folders encoding:
 - class_0 : rest state
 - class_1 : Ayuda
 - class_2 : Baño
 - class_3 : Dolor
 - class_4 : Gracias
 - class_5 : Hambre
 - class_6 : No
 - class_7 : Sed
 - class_8 : Sí


The inclusion criteria were:
• be right-handed
• not taking any medicine that affects the nervous system
• age between 20-30 years
• not to be a smoker
• indistinct gender
• not to drink alcohol
• not to use drugs
• not having epileptic seizures

Steps:
1. The Emotiv EPOC+ was properly placed.
2. Subject needs to be calm and eyes closed.
3. Subject hears a "beep", consequently, keep empty minds for 10 seconds.
4. Subject hear a random word from the eight words menu, consequently, imagine saying that word for 10 seconds.
5. Steps 3-4 repeat until complete 120 seconds (2 minutes), then rest for a few seconds.
6. Step 5 repeat 5 times for each subject.
7. From each recording, for every 10 seconds associated to each class the first 2 seconds were removed preserving only 8 seconds for each state (1024 frames).
8. Each 1024 frames window were converted into 128 frames chunks with an overlap of 48 frames.
9. Each chunk was filtered into five frequency bands (delta, theta, alpha, beta, gamma) using a 4th order Butterworth band-pass filter, where the cut-offs frequencies were (.5,4), (4,8), (8,13), (13,30), (30,40) Hz.
10. Finally, the chunks were saved into CSV files.
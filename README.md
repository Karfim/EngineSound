# Real-time Automotive Engine Sound Simulation with Deep Neural Network

This is the repository providing the synthesized engine sound for comparison. In addition, the database and the code will also be released in the future. 


## Brief introduction

Our method includes a sample-based method, a procedural method, and a hybrid method combining the sample-based and procedural methods. 
* Sample-based method: We choose a 1-second signal of idle engine sound for synthesis. The signal is first pitch-shifted by the ratio between current RPM and the idle RPM. Next, we compute the FFT of this pitch-shifted signal. Finally, the FFT is converted to signal again and summed up with previous signal by griffin-lim overlap-and-add. The step of signal&rarr;FFT&rarr;signal is to smooth the signal and remove the clicking between each frame.

* Procedural method: We employ a simple neural network to predict the amplitude on F_0, 2F_0 and 3F_0 of each frame. Next, we reconstruct the FFT of a frame, where all values are zeros except for F_0, 2F_0 and 3F_0. Finally, the FFT is converted to signal again and summed up with previous signal by griffin-lim overlap-and-add.

* hybrid method: We combine the FFT of sample-based method and procedural method by replacing the amplitude of sample-based method with that of the procedural method on F_0, 2F_0 and 3F_0. Finally, the FFT is converted to signal again and summed up with previous signal by griffin-lim overlap-and-add.

## Results

All sound files can be found in results/. (The github markdown can only play videos so that we convert all wave files to .mp4.)

The original engine sound is: 

https://user-images.githubusercontent.com/30238824/162548763-8d4d3847-cf96-4a42-b6a3-1464cdf6fa24.mp4

The spectrogram of the orignal engine sound is: 

### Sample-based method

First, this is the idle engine sound that we used for sample-based method: 

https://user-images.githubusercontent.com/30238824/162548488-35e24d09-d172-43c8-af70-f918f2c8a8c5.mp4

By pitch-shifting this signal and applying the griffin-lim overlap-and-add, we can obtain a engine sound like that:

https://user-images.githubusercontent.com/30238824/162548638-6bfb55b3-7091-4a1b-9fb7-4c810b473851.mp4

And the spectrogram of the sample-based engine sound is: 



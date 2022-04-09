# Real-time Automotive Engine Sound Simulation with Deep Neural Network

This is the repository providing the synthesized engine sound for comparison. In addition, the database and the code will also be released in the future. 


## Brief introduction

Our method includes a sample-based method, a procedural method, and a hybrid method combining the sample-based and procedural methods. 
* Sample-based method: We choose a 1-second signal of idle engine sound for synthesis. The signal is first pitch-shifted by the ratio between current RPM and the idle RPM. Next, we compute the FFT of this pitch-shifted signal. Finally, the FFT is converted to signal again and summed up with previous signal with overlap-and-add. The step of signal&rarr;FFT&rarr;signal is to smooth the signal and remove the clicking between each frame.

* Procedural method: We employ a simple neural network to predict the amplitude on F_0, 2F_0 and 3F_0 of each frame. Next, we reconstruct the FFT of a frame, where all values are zeros except for F_0, 2F_0 and 3F_0. Finally, the FFT is converted to signal again and summed up with previous signal with overlap-and-add.

* hybrid method: Directly sum up the FFT of sample-based method and procedural method. Finally, the FFT is converted to signal again and summed up with previous signal with overlap-and-add.

## Results

### Sample-based method

results/idlenoise.mp4






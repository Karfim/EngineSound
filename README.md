# Real-time Automotive Engine Sound Simulation with Deep Neural Network

This is the repository providing the synthesized engine sound for comparison. In addition, the database and the code will also be released in the future. 


## Brief introduction

Our method includes a sample-based method, a procedural method, and a hybrid method combining the sample-based and procedural methods. 
* Sample-based method: We choose a 1-second signal of idle engine sound for synthesis. The signal is first pitch-shifted by the ratio between current RPM and the idle RPM. Next, we compute the STFT of this pitch-shifted signal. Finally, the STFT is converted to signal again and summed up with previous signal with overlap-and-add. The step of signal$$STFT$\rightarrow$signal is to smooth the signal and remove the clicking between each frame.

	<img src="https://render.githubusercontent.com/render/math?math=\rightarrow">

* Procedural method
* hybrid method

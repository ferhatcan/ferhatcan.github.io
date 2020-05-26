---
title: "Master Thesis - Paper reviews 02"
paper_name: "Perceptual Losses for Real-Time Style Transfer and Super-Resolution"
paper_tag: sr
date:   2020-05-20 07:24:00 +0300
---

## Perceptual Losses for Real-Time Style Transfer and Super-Resolution

[Paper](https://arxiv.org/pdf/1603.08155.pdf)

- Losses calculated from VGG network layers
- To calculate losses, both Generated image's & HR image's response outputs calculated at different layers of VGG. (this network weights are freeze)

<p align="center">
  <img src="images\Perceptual_loss_SR.png">
</p>
<p align="center">
  <em> Fig.1: General Architecture</em>
</p>

- For SR, input image is resized by reciprocal scale(1/s). Input size should be 3x(288/s)x(288/s)
- Output size is 3x288x288

- Input HR image random cropped with size 3x288x288
- Degradation function(bucubic downsampling) applied to each HR patch.

- *No pooling Layer In this design*
- *For Upsampling convolutional layers with fractional stride is used*

- There are 5 residual blocks. Each blocks consist of simple convolutional, batch Normalization, and Relu blocks. In figure 1, sample residual block can be seen.

<p align="center">
  <img src="images\Arch_perceptual_loss.png">
</p>
<p align="center">
  <em> Fig.2: residual block design</em>
</p>

- Some residual blocks is followed by convolutional layer with 1/2 stride. (It equals to x2 upscale) There should be $log_2s$ number of the fractional convolution layer totally.

- There are 2 type loss function exists: Feature reconstruction loss (FRL) & Style reconstruction loss (SRL). In SR, only FRL is used.

- FRL is calculated mean square error between HR image's and generated image's relu2_2 responses.

<p align="center">
  <img src="images\FRL.png">
</p>
<p align="center">
  <em> Fig.3: Feature reconstruction loss (FRL)</em>
</p>

- SRL is calculated as stated in figure 4 and 5.


<p align="center">
  <img  src="images\SRL_p1.png">
</p>
<p align="center">
  <em> Fig.4: Style reconstruction loss- Gram matrix calculation</em>
</p>
<p align="center">
  <img src="images\SRL_p2.png">
</p>
<p align="center">
  <em> Fig.5: Style reconstruction loss</em>
</p>

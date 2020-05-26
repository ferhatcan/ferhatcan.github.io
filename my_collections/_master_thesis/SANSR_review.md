---
title: "Master Thesis - Paper reviews 04"
post_name:  "SANSR is reviewed."
date:   2020-05-23 07:24:00 +0300
---

## Second-order Attention Network for Single Image Super-Resolution

- Contributions:
  - Adding second order Attention to learn feature interdependencies
  - (It is very similar to RCAN that is used to first order Attention)

  <p align="center">
    <img src="images\SANSR_algorithm.png">
  </p>
  <p align="center">
    <em> Fig.1: SANSR blocks</em>
  </p>

Core parts of the system design:
  1. **Shallow feature extraction** <br/>
    A basic convolution network is used to extract shallow features.

  2. **Deep feature extraction**<br/>
      * *Region-Level Non-Local Network(**RL-NL**)*<br/>
          Non-Local Neural Network is used
      * *Share Source Residual Group(**SSRG**)*
          * Local Source Residual Attention Group(**LSRAG**)
              * Residual blocks
              * Second Order Channel Attention(**SOCA**)
          * Share Source Skip Connection(**SSC**)

  3. **Upscale**<br/>
      ESPCNN upscaling method is used. It uses 2 convolution layer to extract features and image is scaled with phase shift method. (This should be reviewed too)
  4. **Reconstruction**<br/>
      Reconstruction of RGB image from upscale network.


<p align="center">
  <img src="images\SANPage 1.png">
</p>
<p align="center">
  <em> Fig.2: SSRG-part1</em>
</p>
<p align="center">
  <img src="images\SANPage 2.png">
</p>
<p align="center">
  <em> Fig.3: SSRG-part2</em>
</p><p align="center">
  <img src="images\SANPage 3.png">
</p>
<p align="center">
  <em> Fig.4: SSRG-part3</em>
</p>

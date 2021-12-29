# Digital-Beam-Forming-for-spaceborne-Reflector-SAR
This notebook reproduces the results of this paper published in the Proceedings of the 6th European Radar Conference: 

[A novel Digital Beam-Forming Concept for spaceborne Reflector SAR Systems](https://ieeexplore.ieee.org/abstract/document/5306998)

The model used to generate data for demonstrating the results of the paper was taken from this book by Bu-Chin Wang:

[Digital Signal Processing Techniques and Applications in Radar Signal Image Processing](https://www.wiley.com/en-us/Digital+Signal+Processing+Techniques+and+Applications+in+Radar+Image+Processing-p-9780470377826)


---

## Algorithm
<figure>
    <center>
      <img src="images/algorithmic_flow.png"  />
    </center>
</figure> 

The flow breaks down into two main stages: data synthesis then processing. 

In the synthesis stage, the goal is to generate the raw data that a SAR with a linear antenna array and parabolic reflector dish would receive along all channels. First, a symmetric chirp signal is generated to model the initial pulse the radar transmits to begin imaging the ground. The signal is normalized for how it would really be transmitted on the ground given the structure of the radar and reflector. The gain pattern of this structure is not isotropic (meaning spherical) and so it is necessary to adjust the amplitude of the signal depending on how the signal is physically projected on the ground.  The paper refers to this as the 'individual complex channel pattern'. Then, an artificial environment of a point reflector is constructed.

In the processing stage, the received signal is range compressed to select channels that are significant. Then conjugate field matching is applied to create a cohesive image.

---
## Results
### Local LFM Pulse
<figure>
    <center>
      <img src="images/lfm.png"  />
    </center>
</figure> 

### Local LFM Pulse with thermal noise
<figure>
    <center>
      <img src="images/noisy.png" />
    </center>
</figure> 

### Point reflector model simulation along a single channel
<figure>
    <center>
      <img src="images/target_channel.png" />
    </center>
</figure> 

### Synthesized terrain image of point target
<figure>
    <center>
      <img src="images/target_image.png"  />
    </center>
</figure> 

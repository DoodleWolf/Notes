# Neural Radiance Fields for View Synthesis

## 1 Introduction
**View Synthesis** - create a new perspective from a given set of pictures of the same subject

Represent a static scene as a 5D function (aahh 5D is the output)
- inputs: static scene?
- outputs: $(\theta,\phi,x,y,z)$
	- $\theta,\phi$ is the radiance emmited in each direction
	- $x,y,z$ is the point in space

Process (of a single viewpoint):
1. take "camera ray" pictures through scene to get 3D points
2. use the points and 2D (?) viewing direction as input to neural network to get set of colors and densities
3. use classical volume rendering techniques (?) to turn colors and densities into a 2D image

- naturally differentiable (? from clasical volume rendering) => gradient descent to optimize (?) => minimize error from generated images to observed => network that predicts a good model of the scene

Process (overall pipeline):
![[Pasted image 20210202203805.png]]

Propositions:
- hierarchical sampling procedure (to reduce number of queries(?) to do the model)
- 5D => positional encoding (enables multilayer perceptron to represent higher frequency functions)

Technical Contributions:
![[Pasted image 20210202204423.png]]
![[Pasted image 20210202204432.png

## 2 Related Work

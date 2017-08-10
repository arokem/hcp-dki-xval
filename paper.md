
# Title title title


## Introduction

### The Human Connectome Project dMRI data-set

Diffusion MRI (dMRI) measurements provide detailed information about human brain
connectivity and microstructure *in vivo*. HCP is measuring high-quality
multi-modal MRI data from 1,200 individuals and making these data publicly
available [@VanEssen2012]. It has already made measurements from
approximately 900 subjects available through Amazon's Simple Storage Service
(S3).

### What model should we use to explain the data?

Evaluating diffusion MRI models by cross-validation [@Rokem2015PLoS].

#### Diffusion Tensor Imaging (DTI)

Approximates diffusion in every voxel as a Gaussian distribution
[@Basser1994-hg]

(@eq-dti)  $S(\theta, b) = S_0 e^{\theta^T \mathbf{Q} \theta}$

where $\theta$ is XXX and $b$ is XXX

DKI is an extension of DTI that accounts for non-Gaussian behavior in complex
tissue, with many barriers to the diffusion process (cell membranes,
myelin sheaths, etc.) [@Jensen2005-vr]


(@eq-dti-qform) $\mathbf{D} = \begin{pmatrix} \sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\ \sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\ \sigma_{zx} & \sigma_{zy} & \sigma_{zz} \\ \end{pmatrix}$


As seen in equation (@eq-dti) and in equation (@eq-dti-qform) XXX

(@eq-dki)  $S(\theta, b)=S_{0}e^{-bD(\theta)+\frac{1}{6}b^{2}D(\theta)^{2}K(\theta)}$

(@eq-md) $D(\theta)=\sum_{i=1}^{3}\sum_{j=1}^{3}\theta_{i}\theta_{j}Q_{ij}$

(@eq-mk) $K(\theta)=\frac{MD^{2}}{D(\theta)^{2}}\sum_{i=1}^{3}\sum_{j=1}^{3}\sum_{k=1}^{3} \sum_{l=1}^{3}\theta_{i}\theta_{j}\theta_{k}\theta_{l}W_{ijkl}$


## References


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

Approximates diffusion in every voxel as a Gaussian distribution [@Basser1994-hg]

\begin{equation}
S(\theta, b) = S_0 e^{\theta^T \mathbf{Q} \theta}
\end{equation}

where $$b$$ is the b-value [XXX explain],  $$S_0$$ is the signal in the absence of diffusion gradient sensitization ($$b=0$$). $$\mathbf{Q}$$ is a positive-definite quadratic form:

\begin{equation}
$\mathbf{D} = \begin{pmatrix} \sigma_{xx} & \sigma_{xy} & \sigma_{xz} \\
                              \sigma_{yx} & \sigma_{yy} & \sigma_{yz} \\
				                      \sigma_{zx} & \sigma_{zy} & \sigma_{zz} \\
\end{pmatrix} $
\end{equation}


#### Diffusion Kurtosis imaging (DKI).

DKI is an extension of DTI that accounts for non-Gaussian behavior in complex tissue, with many barriers to the diffusion process (cell membranes,
myelin sheaths, etc.) [@Jensen2005-vr]

$S(\theta, b)=S_{0}e^{-bD(\theta)+\frac{1}{6}b^{2}D(\theta)^{2}K(\theta)}$

$D(\theta)=\sum_{i=1}^{3}\sum_{j=1}^{3}\theta_{i}\theta_{j}Q_{ij}$

$K(\theta)=\frac{MD^{2}}{D(\theta)^{2}}\sum_{i=1}^{3}\sum_{j=1}^{3}\sum_{k=1}^{3} \sum_{l=1}^{3}\theta_{i}\theta_{j}\theta_{k}\theta_{l}W_{ijkl}$

$\mathbf{W}$ is a rank 4 tensor (3-by-3-by-3-by-3 matrix).

## References

#image super Resolution
The CRFAN (Cascaded Residual Feature Attention Network) architecture consists of four main components: an initial feature extraction module that uses a shallow convolutional layer to project the low-resolution input into deep feature space; a multi-level progressive upsampling pipeline built with Cascaded Residual Refinement Blocks (CRRBs) that enhance and refine features at each stage while gradually increasing spatial resolution; an attention-based fusion module using a Residual Attention Block (RAB) that applies channel and spatial attention to emphasize informative regions and suppress noise; and a final reconstruction layer that generates the high-resolution output with improved textures, sharp edges, and recovered high-frequency details.
1. Initial Feature Extraction

The input LR image is first passed through a shallow feature extraction layer.

This typically consists of a 3×3 convolution to project the RGB space into a deeper feature space.

Output features serve as the base for subsequent refinement.
2. Multi-Level Progressive Upsampling with CRRBs

The network uses Cascaded Residual Refinement Blocks (CRRBs) to gradually enhance feature quality across multiple stages.

Each CRRB includes:

Residual convolutional layers

Channel-wise feature refinement

Skip connections for stable gradient flow

At each stage, the resolution is increased using:

Sub-pixel convolution (PixelShuffle) or

Transposed convolution

This progressive approach helps the model recover textures step-by-step rather than in a single jump.
3. Attention-Based Feature Fusion (RAB)

The model uses a Residual Attention Block (RAB) to recalibrate feature responses.

RAB includes:

Channel Attention (CA)

Spatial Attention (SA)

Residual connection

This allows the model to:

Highlight informative regions

Suppress irrelevant noise

Combine multi-level features efficiently
4. Final Reconstruction Layer

After upsampling and attention-based fusion, the final HR image is reconstructed using a 3×3 convolution layer, producing:

High-frequency enhancement

Sharper edges

Realistic textures with minimal artifacts

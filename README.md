# Vec2Face: Scaling Face Dataset Generation with Loosely Constrained Vectors

This paper studies how to synthesize face images that allow for effective training of face recognition models, in response to legal constraints in this field. 
To synthesize such training data, identity generation and facial attribute augmentation are two useful strategies to increase inter-class separability and increase intra-class variations, two beneficial factors widely acknowledged by the community. However, existing works 1) are typically limited in generating well separable different identities and 2) either neglect or use a separate editing model for attribute augmentation. 

In this work, we propose Vec2Face, a single model that only uses a vector as input and can flexibly generate and control face images and their attributes. Composed of a modified masked autoencoder and an image decoder, Vec2Face is supervised by face image reconstruction and can be conveniently used in inference. Specifically, using vectors with low similarities among themselves as inputs, Vec2Face generates well-separable identities; randomly perturbing an input vector within a reasonable range allows Vec2Face to generate faces of the same identity but with robust variations in face attributes; it is also possible to generate images with designated attribute by adjusting vector values with a gradient descent based method. Therefore, high inter-class separability and intra-class variations are achieved using a single model. 

Vec2Face allows us to efficiently synthesize as many as 
200K identities with 10 million images without observing the accuracy saturation.
Face recognition models trained with the resulting datasets achieve the state-of-the-art performance, with the accuracy on CALFW test set being the first higher than the same-scale real dataset.

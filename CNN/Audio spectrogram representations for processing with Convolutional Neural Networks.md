
## Audio spectrogram representations for
processing with Convolutional Neural Networks

### URL https://arxiv.org/pdf/1706.09559.pdf

### Gist
- Paper focuses on how to feed CNN's audio focusing particularly on spectrograms for generating audio using
neural networks for style transfer

### Explorations and notes:
- Wavenets:- Encountered before. To be worked summariised in a future document. But essentially a very deep convolutional neural net geared towards TTS. Major diffrentiating factor is use of end to end learning.
- Style Transfer: CNN's work a lot with images. Quoting paper: 
> the question naturally arises as to whether the image nets
> would be useful for audio style transfer representing audio spectrogram images. We ran some
> experiments with the pre-trained VGG-19 network, with the goal of superimposing “style”
> or textural features from one spectrogram on the “content” or structural features of another.
- However images are fed in 3-channels. A big challenge with audio. Feeding an entire spectogram of audio is also a challenging task.
> Convolutional neural networks designed for images use 2D convolution kernels that share
weights across both the x and the y dimensions. This is based in part on the notion of
translational invariance, which means that an image feature or object is the same no matter
where it is in the image. For sonic objects in the linear-frequency sonogram, this is true
when objects are shifted in the x dimension (time), but not when they are shifted in the y
dimension (frequency). Audio objects consist of energy across the frequency dimension, and as
a sound is raised in pitch, its representation not only shifts up, but changes in spatial extent.
A log frequency representation may go some way to addressing this issue, but the non-local
distribution of energy across frequency of an audio object might still be problematic for 2D
convolution kernels. Sound images also present other challenges compared to visual images
> for example, sound objects are “transparent” so that multiple objects can have energy at
the same frequency, where a given pixel in a visual image almost always corresponds to only
one object. In addition, audio objects are non-locally distributed over a spectrogram whereas
visual objects tend to be comprised of neighboring pixels in an image

## A really Intresting approach
[https://dmitryulyanov.github.io/audio-texture-synthesis-and-style-transfer ]
- Dmitry Ulyanov Ulyanov and Lebedev [2016] reports in a blog posting about using convolutional
neural networks in a different way for audio style transfer. He uses spectrograms, but
instead of representing the frequency bins as the y dimension in an image, he considers the
different frequencies as existing at the same point in a 1D representation as stack of “channels”
in the same way the 3 channels for red, green, and blue are stacked at each point in a 2D visual
image. As in image applications, the convolution kernel spans the entire channel dimension;
there is no small shared-weight convolution kernel that shifts along the channel dimension as
it does in the spatial dimensions. The number of audio channels, typically 256 or 512, is much
greater than the 3 channels used for color images, and the vertical dimension is reduced to one.




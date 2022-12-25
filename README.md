# AIISC

This repo contains the work I've been doing as part of my research internship @ AIISC, UofSC, on large scale object discovery from images with text attention using `Stable Diffusion`.

I worked on creating synthetic annotated image data from `Stable Diffusion`, using captions in the `Flickr30k` dataset as text prompt.
A major challenge was creating high-quality annotations for thousands of images efficiently; we managed to achieve this by using `DAAM`, a technique that can create word-wise attention maps for words in the text prompt. This can be further converted to bounding boxes for all instances of the word in the image, leading to high-grade annotations without much human effort!

Please feel free to suggest any changes that might be helpful in improving the repo or the codebase, and hope you like it :)


# Large-Scale Text Based Object Discovery using Stable Diffusion

Object Detection has been one of the most key topics of research in Computer Vision in the last decade. Though Object Detection models have enjoyed great success in various real-life domains, they are data-hungry and require large-scale annotated datasets for training, which is often unfeasible given the human effort needed for data collection and manual labeling. Extending the object detection task to a large number of classes (~20k) would therefore require the use of methods for synthetic annotated image data generation.

In this work, we aim to build a large-scale image dataset annotated with bounding boxes for instances of ~20k objects using synthetic methods. We adopt the following approach :

- We collect image captions from datasets like [MS-COCO](https://cocodataset.org), [Flickr30k](https://shannon.cs.illinois.edu/DenotationGraph/), [Conceptual Captions](https://ai.google.com/research/ConceptualCaptions/) and [Visual Genome](http://visualgenome.org) and use `stable-diffusion-v2` to generate images for the captions.

- We leverage [DAAM](https://arxiv.org/abs/2210.04885) (Tang et al.), a method which produces attention maps for each word of a caption, and we convert the maps so produced into bounding boxes using a combination of contour detection and Otsu's threshold.

- Our approach is able to generate high-quality synthetic image annotations for a large number of object classes (~20k), comparable to state-of-the-art baseline models like [Detic](https://arxiv.org/abs/2201.02605) (Zhou et al.).

Some details about the repo :

- The `data` folder contains a .json file containing a total of ~150k Flickr30k captions

- The Jupyter Notebook in `src` contains the implementation for the synthetic annotated data generation pipeline, which can be used to facilitate the creation of large-scale, high-quality bounding box annotations with minimal human effort. 

- The `results` folder contains a `final` folder demonstrating results for a small subset of `Flickr30k` captions, as well as the output for a sample caption : `A little girl wearing a pink dress standing in a wooden cabin`.

Upcoming :

- We aim to extend this approach to produce instance segmentations for various objects.
- Use of `Min-Max Suppression` to remove the small point-sized bbox annotations produced.

Hope you find this work useful ;)

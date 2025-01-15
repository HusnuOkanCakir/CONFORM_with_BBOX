# **Improving Spatial Arrangement in CONFORM using Bounding Boxes**



><p align="center">

>Contributors: Okan Çakır, Özgür Temmuz Çelik, Mahan Ahmadvand, Kerem Güra

></p>
>
> Text-to-image generation is an emerging topic in
Machine Learning and Natural Language Processing. One critical aspect of evaluating generated
images is the correct placement of objects according to the given prompt. This paper investigates
two models: Layout Predictor
and CONFORM (Meral et al., 2023). By combining the strengths of these models, we propose a
novel approach that improves object placement
accuracy in generated images of CONFORM. Preliminary results demonstrate that our model significantly improves alignment between textual descriptions and visual outputs.




Our approach combines the strengths of the Layout Predictor and CONFORM. We generate the bounding boxes for each object in the prompt using the Layout Predictor for accurate spatial arrangements. Afterwards, we use these bounding boxes to place objects within the frame accurately. This novel solution allows us to solve the misplacement issue of objects in the original model of CONFORM.
</p>

## Description

Overview: Given a prompt, we extract the bounding box coordinates for each object in the prompt, which consider their relative positions in the frame. Using these bounding boxes, the original attention aggregation in CONFORM is adjusted to apply a mask to the pixel region corresponding to the bounding box. As a result, the object placement is improved compared to the original model. The other aspects of CONFORM such as the contrastive loss and attention processing remain the same.
</p>

## Setup

### Environment
The necessary libraries are installed within the notebook.ipynb file. Running it on Google Colab will be sufficient to test out the model.

### Hugging Face Diffusers Library
The code also relies on Hugging Face's [diffusers](https://github.com/huggingface/diffusers) library for downloading the Stable Diffusion v1.5 model. 


## Usage
Please download these 2 folders (that contain the pretrained models) and place them in the same folder with the notebook:

https://drive.google.com/drive/folders/1CpFydL4Z1COWD-HnJ_gmBqNNFNb0Ti3C?usp=sharing

https://drive.google.com/drive/folders/1yWLrGolB3SUd-6v4C_KFqU2ZzUvArbLR?usp=sharing


The Jupyter notebook: notebook.ipynb can be used to generate an image from any prompt. The token indices for the objects should be arranged manually.

The Jupyter notebook: notebook_SPRel_caclulation.ipynb can be used to calculate the SPRel prcision for the generated images for evaluation purposes.

## Acknowledgments
We would like to thank Enis Simsar for his assistance and guidance throughout the project.

## 3D-Aware Face Swapping<br><sub>Official PyTorch implementation of the CVPR 2023 paper</sub>

![Teaser image](images/teaser.png)

**3D-Aware Face Swapping**<br>
Yixuan Li, Chao Ma, Yichao Yan, Wenhan Zhu, Xiaokang Yang<br>

Abstract: *Face swapping is an important research topic in computer vision with wide applications in entertainment and privacy protection. Existing methods directly learn to swap 2D facial images, taking no account of the geometric information of human faces. In the presence of large pose variance between the source and the target faces, there always exist undesirable artifacts on the swapped face. In this paper, we present a novel 3D-aware face swapping method that generates high-fidelity and multi-view-consistent swapped faces from single-view source and target images. To achieve this, we take advantage of the strong geometry and texture prior of 3D human faces, where the 2D faces are projected into the latent space of a 3D generative model. By disentangling the identity and attribute features in the latent space, we succeed in swapping faces in a 3D-aware manner, being robust to pose variations while transferring fine-grained facial details. Extensive experiments demonstrate the superiority of our 3D-aware face swapping framework in terms of visual quality, identity similarity, and multi-view consistency. Project page: https://lyx0208.github.io/3dSwap*

## Requirements

* See [environment.yaml](./environment.yaml) for python dependencies.  You can use the following commands with Anaconda to create and activate your Python environment:
  - `conda env create -f environment.yaml`
  - `conda activate 3dSwap`

## Datasets preparation
* We preprocess the images from the original FFHQ and CelebA-HD dataset with the data preprocessing code from **[EG3D](https://github.com/NVlabs/eg3d)**, including re-cropping the images and extracting according camera poses.

  - To test on CelebA-HD dataset, please down our preprocessed data from [here](https://drive.google.com/drive/folders/1p8LPK23ZTSztZ2noPiz-XWcefvqe-f0r?usp=sharing).

  - To test on your own images, please refer to the data preprocessing file of EG3D [here](https://github.com/NVlabs/eg3d/blob/main/dataset_preprocessing/ffhq/preprocess_in_the_wild.py).

## Inference
Download our pretrained model from [here](https://drive.google.com/drive/folders/1rlZRO-pjKFedmx6-3QdSxxThN_jXA6Pb?usp=sharing). Put model_ir_se50.pth under the "models" folder and other files under the "checkpoints" folder.

Then run:

```.bash
python run_3dSwap.py
```

If you only want to perform the 3D GAN inversion without face swapping, run:

```.bash
python run_inversion.py
```


## Citation

```
@InProceedings{Li_2023_CVPR,
    author    = {Li, Yixuan and Ma, Chao and Yan, Yichao and Zhu, Wenhan and Yang, Xiaokang},
    title     = {3D-Aware Face Swapping},
    booktitle = {Proceedings of the IEEE/CVF Conference on Computer Vision and Pattern Recognition (CVPR)},
    month     = {June},
    year      = {2023},
    pages     = {12705-12714}
}
```

## Acknowledgements
* Our code is developed base on: 
    - https://github.com/NVlabs/eg3d

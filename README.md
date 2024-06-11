# Robust CLIP Image Generation

## Motivation
In this minimalist notebook, we generate images from a given text prompt by traversing through the gradients of [Robust CLIP (ICML 2024, Schlarman et al.)](https://arxiv.org/pdf/2402.12336) **without a generative model**. Generating images from the gradients of a classifier is by no means a novel idea (see, for example, [this paper](https://proceedings.neurips.cc/paper_files/paper/2019/file/6f2268bd1d3d3ebaabb04d6b5d099425-Paper.pdf)). Several approaches have used CLIP to synthesize/search for an image that is similar to a prompt (e.g., [CLIPig](https://github.com/defgsus/clipig)). However, its gradients are not suitable for generation since CLIP's image encoder is sensitive to small imperceptible perturbations and adversarial attacks. As such, a naive gradient descent may result in semantically poor images that have high CLIP similarity scores. To alleviate this issue, CLIPig augments samples with noise, random rotations, etc. Contrary to this, robust classifiers have *perceptually-aligned gradients* and perform better at generative tasks, as shown by [Srinivas et al.](https://arxiv.org/pdf/2305.19101) This motivated me to check how well Robust CLIP would work in **straightforward** settings (i.e., without the need to introduce tricky augmentations).

## Results
The results are random and not cherry picked. 
![image](https://github.com/realfolkcode/clip-robust-gen/assets/64730991/e45f6b1b-02e9-4f19-9479-d618181906f5)

## Contribution
I welcome everyone who wishes to contribute. The main object of interest is experiments with different guidance schedulers and normalizations. If you have something to show or share, please do so in [Discussions](https://github.com/realfolkcode/clip-robust-gen/discussions).

## Acknowledgements
- [Robust CLIP](https://github.com/chs20/RobustVLM)
- [Open CLIP](https://github.com/mlfoundations/open_clip)
- [CLIPig](https://github.com/defgsus/clipig)

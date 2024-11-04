# SegLLM: Multi-round Reasoning Segmentation

We present SegLLM, a novel multi-round interactive segmentation model that leverages conversational memory of both visual and textual outputs to reason over previously segmented objects and past interactions, effectively interpreting complex user intentions.

<p align="center"> 
  <img width="1301" alt="demo" src=./assets/demo.gif align="center" >
</p>

> [**SegLLM: Multi-round Reasoning Segmentation**](http://arxiv.org/abs/2410.18923)            
> [XuDong Wang*](https://frank-xwang.github.io/), Shaolun Zhang*, [Shufan Li*](https://homepage.jackli.org/), [Konstantinos Kallidromitis](https://tech-ai.panasonic.com/en/researcher_introduction/048/), Kehan Li, Yusuke Kato, Kazuki Kozuka, [Trevor Darrell](https://people.eecs.berkeley.edu/~trevor/)       
> UC Berkeley, UCLA, Panasonic AI Research, Stanford            
> Preprint         

[[`project page`](https://berkeley-hipie.github.io/segllm.github.io/)] [[`arxiv`](https://arxiv.org/pdf/2410.18923)] [[`bibtex`](#citation)]             


## Updates
- 11/03/2024 Initial commit: release model inference codes and Gradio demo.

## Installation
See [installation instructions](./INSTALL.md).

## Inference

<p align="center"> 
  <img width="1301" alt="pipeline" src=./assets/architecture.png align="center" >
</p>

Launch the Gradio demo:
```
CUDA_VISIBLE_DEVICES=0 ./scripts/inference/launch_gradio_demo.sh
```
Launch inference via command line:
```
CUDA_VISIBLE_DEVICES=0 ./scripts/inference/launch_cli_demo.sh
```
Consider trying the example images and conversations in `inference_images`.


## Citation
If you find our work inspiring or use our codebase in your research, please consider giving a star ⭐ and a citation.
```
@article{wang2024segllm,
  title={SegLLM: Multi-round Reasoning Segmentation},
  author={Wang, XuDong and Zhang, Shaolun and Li, Shufan and Kallidromitis, Konstantinos and Li, Kehan and Kato, Yusuke and Kozuka, Kazuki and Darrell, Trevor},
  journal={arXiv preprint arXiv:2410.18923},
  year={2024}
}
```

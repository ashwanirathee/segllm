# SegLLM: Multi-round Reasoning Segmentation

SegLLM is a multi-round interactive segmenter that reasons over previously segmented objects and past interactions to interpret complex user intentions.


<p align="center">
    [<a href="https://berkeley-hipie.github.io/segllm.github.io/">Project Page</a>]
    [<a href="https://arxiv.org/pdf/2410.18923">Arxiv</a>]
</p>

<p align="center"> 
  <img width="1301" alt="demo" src=./assets/demo.gif align="center" >
</p>

<p align="center"> 
  <img width="1301" alt="pipeline" src=./assets/architecture.png align="center" >
</p>

## Installation
See [installation instructions](./INSTALL.md).

## Inference
Launch the Gradio demo:
```
CUDA_VISIBLE_DEVICES=0 ./scripts/inference/launch_gradio_demo.sh
```
Launch inference via command line:
```
CUDA_VISIBLE_DEVICES=0 ./scripts/inference/launch_cli_demo.sh
```
Consider trying the example images and conversations in `inference_images`.
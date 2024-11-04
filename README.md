# SegLLM: Multi-round Reasoning Segmentation

This is the GitHub repo for SegLLM. We will release the code soon :-) . Stay tuned!

Project page: [Link](https://berkeley-hipie.github.io/segllm.github.io/)


![alt text](rr.gif)

# Model Architecture

![alt text](https://berkeley-hipie.github.io/segllm.github.io/segllm/architecture.png)

SegLLM performs multi-round interactive image reasoning segmentation, which involves understanding complex user queries and segment entities based on their relationships with other objects. There are two key designs in SegLLM that facilitate this goal: First, we implement a mask encoding scheme that reincorporates the reference mask information back into the input stream of the LLMs. This enables the LLMs to reason about segmented masks from previous rounds. Second, we develop a mask-aware decoding scheme that allows the mask decoder to generate new masks based on both the output from the LLMs and the historical memory of output masks. The model uses the last layer hidden states associated with the [REF] and [SEG] tokens to generate both the reference mask and the target mask, seamlessly integrating past and current segmentation results. More details can be found in our Paper.

## Installation
Create conda environment.
```
conda create --name segllm python=3.10
conda actiovate segllm
conda install pytorch torchvision torchaudio pytorch-cuda=12.4 -c pytorch -c nvidia
```

Install HIPIE segmentor and build deformable attention.
```
cd uninext-segm
pip3 install -e .

cd ./projects/HIPIE/hipie/models/deformable_detr/ops
bash make.sh
cd ../../maskdino/pixel_decoder/ops
bash make.sh
cd ../../../../../../..

mkdir -p projects/HIPIE/bert-base-uncased
cd projects/HIPIE/bert-base-uncased
wget -c https://huggingface.co/bert-base-uncased/resolve/main/config.json
wget -c https://huggingface.co/bert-base-uncased/resolve/main/vocab.txt
wget -c https://huggingface.co/bert-base-uncased/resolve/main/pytorch_model.bin
cd ../../../../
```
Install SegLLM dependencies.
```
pip install -e . --no-dependencies
pip install -r requirements.txt
```
Download the `r50_parts.pth` weights for HIPIE [here](https://drive.google.com/drive/folders/1HEmCCRaWv6CEkim-PY6Qv4jGtdKvw8VH), and place in `./pretrained_weights/hipie`.

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
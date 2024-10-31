# SegLLM: Multi-round Reasoning Segmentation

This is the GitHub repo for SegLLM. We will release the code soon :-) . Stay tuned!

Project page: [Link](https://berkeley-hipie.github.io/segllm.github.io/)


![alt text](rr.gif)

# Model Architecture

![alt text](https://berkeley-hipie.github.io/segllm.github.io/segllm/architecture.png)

SegLLM performs multi-round interactive image reasoning segmentation, which involves understanding complex user queries and segment entities based on their relationships with other objects. There are two key designs in SegLLM that facilitate this goal: First, we implement a mask encoding scheme that reincorporates the reference mask information back into the input stream of the LLMs. This enables the LLMs to reason about segmented masks from previous rounds. Second, we develop a mask-aware decoding scheme that allows the mask decoder to generate new masks based on both the output from the LLMs and the historical memory of output masks. The model uses the last layer hidden states associated with the [REF] and [SEG] tokens to generate both the reference mask and the target mask, seamlessly integrating past and current segmentation results. More details can be found in our Paper.

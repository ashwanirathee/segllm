## Directory Structure
The dataset folders should be organized as follows. The following sections provides details on how to download the images, annotations and conversations data.
```
segllm
  ├── images_folder
  ├── annotations_folder
  ├── conversations_folder
```

## Images
Donwload images using the following links.

MSCOCO
```
wget http://images.cocodataset.org/zips/train2017.zip
wget http://images.cocodataset.org/zips/train2014.zip
```

Reason Seg
```
gdown https://drive.google.com/drive/folders/125mewyg5Ao6tZ3ZdJ-1-E3n04LGVELqy --folder
```


The directory structue for `images_folder` should be organized as follows.
```
images_folder
  ├── coco
  │   └── train2014
  │   └── val2014
  │   └── test2014
  ├── reason_seg
  │   └── images
  │       └── train
  │       └── val
  │       └── test
```


## Conversations
Download the conversations data using git lfs.
```
git lfs install
git clone https://huggingface.co/datasets/Marlo-Z/SegLLM_dataset

mv SegLLM_dataset/conversations_folder ./
mv SegLLM_dataset/annotations_folder ./
rm -rf SegLLM_dataset
```
The directory structure for `conversations_folder` is downloaded from git clone.

## Annotations
You can download dataset annotations from the following links - [refCOCO](https://web.archive.org/web/20220413011718/https://bvisionweb1.cs.unc.edu/licheng/referit/data/refcoco.zip), [refCOCO+](https://web.archive.org/web/20220413011656/https://bvisionweb1.cs.unc.edu/licheng/referit/data/refcoco+.zip), [refCOCOg](https://web.archive.org/web/20220413012904/https://bvisionweb1.cs.unc.edu/licheng/referit/data/refcocog.zip), [ReasonSeg](https://github.com/dvlab-research/LISA#dataset), and [PACO-LVIS](https://github.com/facebookresearch/paco/tree/main#dataset-setup)

The directory structure for the `annotations_folder` should be organized as follows.
```
annotations_folder
  ├── paco_lvis
  │   └── annotations
  │       └── paco_lvis_v1_val.json
  ├── reason_seg
  │   └── annotations
  │       └── val
  │       └── test
  ├── refcoco
  │   └── instances.json
  ├── refcoco+
  │   └── instances.json
  ├── refcocog
  │   └── instances.json
```
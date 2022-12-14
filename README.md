# PySTformer: Pyramidal Spatio-Temporal Transformer for Anomaly Detection in Aerial and Surveillance Videos
This is the code for "PySTformer: Pyramidal Spatio-Temporal Transformer for Anomaly Detection in Aerial and Surveillance Videos".

 * [Project Page](https://vt-le.github.io/pystformer)
 * [Paper](https://arxiv.org)
 * [Video](https://www.youtube.com)
 
This codebase is implemented using [PyTorch](https://pytorch.org/).


## Setup
The code can be run under any environment with Python 3.7 and above.
(It may run with lower versions, but we have not tested it).

Install the required packages:

    pip install -r requirements.txt
  

## Training

Download `weights`, and put them in a folder `pretrained/`

| Dataset      | Link                                                                                   |
|--------------|----------------------------------------------------------------------------------------|
| UCSD Ped2    | [![Google drive](https://colab.research.google.com/assets/colab-badge.svg)](https://)  |
| CUHK Avenue  | [![Google drive](https://colab.research.google.com/assets/colab-badge.svg)](https://) |
| ShanghaiTech | [![Google drive](https://colab.research.google.com/assets/colab-badge.svg)](https://) |
 

After preparing a dataset, you can train a model by running:
    
    python train.py \
        --data_dir $DATASET_PATH \
        --base_folder $EXPERIMENT_PATH \
        --gin_configs configs/test_vrig.gin
 

## Configuration
 * We use [YAML](https://yaml.org/) for configuration.
 * We provide a couple preset configurations.
 * Please refer to `config.py` for documentation on what each configuration does.

 
## Datasets
A dataset is a directory with the following structure:

    dataset
        ├── train
        │   └── ${video_id}
        │   └── └── ${frame_id}.jpg
        ├── test
        │   ├── ${video_id}
        │   └── └── ${frame_id}.jpg
        └── dataset.mat

At a high level, a dataset is simply the following:
 * A collection of images (e.g., from a video).
 * XXX for each image.
 
In each video folder, we have a unique identifier for each image which we call `frame_id`, which is extracted from the 
video. An `frame_id` can be any string, but typically it is some alphanumeric string such as `0250`.


## Citing
If you find our work useful, please consider citing:
```BibTeX
@article{le2023pystformer
  author    = {Le, Viet-Tuan                
               and Kim, Yong-Guk},
  title     = {PySTformer: Pyramidal Spatio-Temporal Transformer for Anomaly Detection in Aerial and Surveillance Videos.},
  journal   = {Expert Systems with Applications},
  year      = {2023},
  publisher = {Elsevier}
}
```

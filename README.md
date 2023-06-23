# P5-shuffled
This project is mainly based on jeykigung's work
access their github repo through [P5 repo](https://github.com/jeykigung/P5.git)
> Paper link: https://arxiv.org/pdf/2203.13366.pdf


## Introduction
This project takes shashankrajput's commit in https://github.com/jeykigung/P5/pull/3. This repo is exactly same as P5 repo expcept that the data has shuffled item ids.

## Requirements:
- Python 3.9.7
- PyTorch 1.10.1
- transformers 4.2.1
- tqdm
- numpy
- sentencepiece
- pyyaml


## Usage

0. Clone this repo

    ```
    git clone https://github.com/menglin0320/P5-shuffled.git
    ```

1. Download preprocessed data from this [Google Drive link](https://drive.google.com/file/d/1wY0HEBDHH3jOaWxlmgvyN62LDy9mU_SW/view?usp=sharing), (The data in this link is shuffled beauty data, I didn't try to make sure the zero shot split still works since I'm not testing those tasks.) then put them into the *data* folder. If you would like to preprocess your own data, please follow the jupyter notebooks in the *preprocess* folder. Raw data can be downloaded from this [Google Drive link](https://drive.google.com/file/d/1uE-_wpGmIiRLxaIy8wItMspOf5xRNF2O/view?usp=sharing), then put them into the *raw_data* folder.

   
2. Download pretrained checkpoints into *snap* folder. If you would like to train your own P5 models, *snap* folder will also be used to store P5 checkpoints.


3. Pretrain with scripts in *scripts* folder, such as

    ```
    bash scripts/pretrain_P5_base_beauty.sh 4
    ```
   Here *4* means using 4 GPUs to conduct parallel pretraining.
    
4. Evaluate with example jupyter notebooks in the *notebooks* folder. Before testing, create a soft link of *data* folder to the *notebooks* folder by
   
   ```
   cd notebooks
   ln -s ../data .
   ```


## Pretrained Checkpoints
See [CHECKPOINTS.md](snap/CHECKPOINTS.md).

You can also explore P5 in Hugging Face Hub (https://huggingface.co/makitanikaze/P5).


## Citation

Please cite the following paper corresponding to the repository:
```
@inproceedings{geng2022recommendation,
  title={Recommendation as Language Processing (RLP): A Unified Pretrain, Personalized Prompt \& Predict Paradigm (P5)},
  author={Geng, Shijie and Liu, Shuchang and Fu, Zuohui and Ge, Yingqiang and Zhang, Yongfeng},
  booktitle={Proceedings of the Sixteenth ACM Conference on Recommender Systems},
  year={2022}
}
```

## Acknowledgements

[VL-T5](https://github.com/j-min/VL-T5), [PETER](https://github.com/lileipisces/PETER), [P5](https://github.com/jeykigung/P5.git) and [S3-Rec](https://github.com/aHuiWang/CIKM2020-S3Rec)

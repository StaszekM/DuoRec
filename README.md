# Notes by StaszekM:

For our assignment, we use only our own data, not any samples proposed by the authors



1. Put `file_cutoff.pkl` and `metadata_with_embeddings.pkl` inside `./artifacts`
2. Run `transform_artifacts.ipynb`
3. Rename the resulting CSVs to `rekomDataset.inter` and `rekomDataset.item`
4. Put these files to the directory as shown below

```
$ tree
.
├── rekomDataset
│   ├── rekomDataset.inter
│   └── rekomDataset.item

```

5. Run your training with:
6. 
```
$ python run_seq.py --dataset='rekomDataset' --train_batch_size=256 --lmd=0.1 --lmd_sem=0.1 --model='CL4SRec' --contrast='us_x' --sim='dot' --tau=1
```

# DuoRec
Code for WSDM 2022 paper, [Contrastive Learning for Representation Degeneration Problem in Sequential Recommendation](https://arxiv.org/abs/2110.05730).

# Usage

Download datasets from [RecSysDatasets](https://github.com/RUCAIBox/RecSysDatasets) or their [Google Drive](https://drive.google.com/drive/folders/1ahiLmzU7cGRPXf5qGMqtAChte2eYp9gI). And put the files in `./dataset/` like the following.

```
$ tree
.
├── Amazon_Beauty
│   ├── Amazon_Beauty.inter
│   └── Amazon_Beauty.item
├── Amazon_Clothing_Shoes_and_Jewelry
│   ├── Amazon_Clothing_Shoes_and_Jewelry.inter
│   └── Amazon_Clothing_Shoes_and_Jewelry.item
├── Amazon_Sports_and_Outdoors
│   ├── Amazon_Sports_and_Outdoors.inter
│   └── Amazon_Sports_and_Outdoors.item
├── ml-1m
│   ├── ml-1m.inter
│   ├── ml-1m.item
│   ├── ml-1m.user
│   └── README.md
└── yelp
    ├── README.md
    ├── yelp.inter
    ├── yelp.item
    └── yelp.user

```

Run `duorec.sh`.

# Cite

If you find this repo useful, please cite
```
@article{DuoRec,
  author    = {Ruihong Qiu and
               Zi Huang and
               Hongzhi Yin and
               Zijian Wang},
  title     = {Contrastive Learning for Representation Degeneration Problem in Sequential Recommendation},
  journal   = {CoRR},
  volume    = {abs/2110.05730},
  year      = {2021},
}
```

# MISC

We have also implemented `CL4SRec`, [Contrastive Learning for Sequential Recommendation](https://arxiv.org/abs/2010.14395). Change the `--model="DuoRec"` into `--model="CL4SRec"` in the `duorec.sh` file to run `CL4SRec`.

Our another sequential recommender model `MMInfoRec`, [Memory Augmented Multi-Instance Contrastive Predictive Coding for Sequential Recommendation](https://arxiv.org/abs/2109.00368) at ICDM 2021 is also available on GitHub, [MMInfoRec](https://github.com/RuihongQiu/MMInfoRec).

# Credit
This repo is based on [RecBole](https://github.com/RUCAIBox/RecBole).

# Prototype-guided Attribute-wise Interpretable Scheme for Clothing Matching

Code for paper [Prototype-guided Attribute-wise Interpretable Scheme for Clothing Matching](https://dl.acm.org/doi/10.1145/3331184.3331245).

## Dependencies

This project is implemented with

- Python 3.8

- Pytorch 1.6.0


## Data Preparation

The proposed PAICM is verified on the [FashionVC](https://xuemengsong.github.io/) dataset. You can download the origin FashionVC dataset from their provided links (Google Drive Link: https://drive.google.com/open?id=1lO7M-jSWb25yucaW2Jj-9j_c9NqquSVF or Baidu Netdisk Link: https://pan.baidu.com/s/1eS1vNNk with the password: ytu4).

To extract the feature, we provided the item attribute classifier ([checkpoint](https://pan.baidu.com/s/1EbmJIYosNVyQoBk-NNKX_Q) password: k29k) pre-trained on DeepFashion dataset to generate the attribute feature. The feature extraction code is in [fashionVCpredict.py]. The pre-trained attribute classifier can be also used on other fashion datasets.

To enhance the attribute feature, we also extracted the categoty and color labels from the meta textual and visual data of each item. The extracted categoty and color labels are provided in ./data/. The extraction tools are also provided in ./utils/.

Concat the attribute feature with the categoty and color labels by code [concat_category_color.py], and you can get the final input features.

By the way you can derictly download the final input features from [here]()

### Step by step instructions

If you have derictly downloaded the final input features, you can skip the following instructions.

- 1 Download the FashionVC dataset.

- 2 Change the path in the head of the fashionVCpredict.py

- 3 Extract the attribute feature with instruction: python fashionVCpredict.py

- 4 Change the path in the head of the concat_category_color.py

- 5 Concat all the feature with instruction: python concat_category_color.py

### Data format

--data-
      -
--checkpoints-

## Running command

- python paicm_pytorch.py

We also provided the pre-trained [checkpoint] for test.

## Citations

```
@inproceedings{HanSYWN19,
  author = {Xianjing Han and Xuemeng Song and Jianhua Yin and Yinglong Wang and Liqiang Nie},
  title = {Prototype-guided Attribute-wise Interpretable Scheme for Clothing Matching},
  booktitle = {Proceedings of the international ACM SIGIR Conference on Research and Development in Informaion Retrieval},
  pages = {785--794},
  year = {2019}
}
```

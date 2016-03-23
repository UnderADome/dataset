# dataset


## text-classification.7z

数据集是有8个分类的文本数据集，使用了结巴分词对每个文本分词，每个单词当作特征，再利用二元词串构造更多特征，然后去掉停用词，去掉出现次数太多和太少的特征，得到了19630个特征。取1998个样本用于训练，509个用于测试。基于词袋模型的思路将每个文本转换为向量，训练集和测试集分别转换为矩阵，并用python numpy模块将其保存为npy格式。

数据集共使用了19630个单词作为特征，特征值是词在文本中出现的次数。8个分类，分别是1、2、...、8。训练集共1998个样本，测试集共509个样本。

示例：
```
$ ls
test_data.npy  test_labels.npy  training_data.npy  training_labels.npy
$ ipython
>>> import numpy as np
>>> training_data = np.load("training_data.npy")
>>> training_data.shape
(1998, 19630)
>>> training_labels = np.load("training_labels.npy")
>>> training_labels
array([6, 6, 6, ..., 2, 2, 2])
>>> training_labels.shape
(1998,)
>>> test_data = np.load("test_data.npy")
>>> test_data.shape
(509, 19630)
>>> test_labels = np.load("test_labels.npy")
>>> test_labels.shape
(509,)
```

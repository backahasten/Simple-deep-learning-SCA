# Simple-deep-learning-SCA
Simple deep learning side channel attack. Experimental data set based on chipwhisperer.

自己的毕业设计，做一个纪念

使用了一些简单机器学习算法和一些简单的深度学习算法+特征提取算法，针对sbox out进行汉明重量的分类。

## 作者

backahasten   重庆邮电0xFA成员(已经毕业)   野生侧信道研究者

mail ：backahasten@qq.com

## 内容

[cw_template.py](https://github.com/backahasten/Simple-deep-learning-SCA/blob/master/cw_template.py)

由chipwhisperer官方提供的模板攻击代码，作为对照。

[fft_pca_mlp.py](https://github.com/backahasten/Simple-deep-learning-SCA/blob/master/fft_pca_mlp.py)

频域->pca降维->mlp分类

[lda.py](https://github.com/backahasten/Simple-deep-learning-SCA/blob/master/lda.py)

lda分类

[mlp.py](https://github.com/backahasten/Simple-deep-learning-SCA/blob/master/mlp.py)

时域mlp分类

[svm.py](https://github.com/backahasten/Simple-deep-learning-SCA/blob/master/svm.py)

使用SVM算法进行分类

[svm_search.py](https://github.com/backahasten/Simple-deep-learning-SCA/blob/master/svm_search.py)

用于搜索SVM最优参数

## 一些总结

传统的模板攻击的特征点选取方法，提取的所有点是同一个一维度特性，如果提取的特征点太多，没有带来信息量的增加，反而使得矩阵的条件数越来越大，矩阵中毒，无法求解。pca降维，在数学上意义上比较好，无论是频域还是时域实际效果还是比较好的。

这个是一个微小差别分类问题，所以mlp的步长特别小，特别容易过拟合。

## 对齐

CNN分类是可以搞定没有对齐的的曲线的，但是由于算力问题没有做实验。

我个人认为，通过前期的弹性对齐之后，再进行分类和攻击，无论是算力还是效果上，性价比是最好的。我认为，对没对齐的曲线直接攻击分类是没有性价比的。




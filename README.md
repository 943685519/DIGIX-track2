# Baseline(BERT + PU-learning):

1.选取有标签的dataset作为 positive label 无标签的作为unlabeled标签

2.使用有标签的数据去做一个十分类分类器（BERT or LSTM）

3.把无标签的样本喂给分类器，根据最高置信度概率小于0.8的作为 reliable negetive样本

4.随机采样 P 样本 和 RN 样本去训练一个二分类器

5.对于测试集， 先做二分类，如果是负类则判为其他，如果是正类在做十分类。



时间预估：

整体训练时间：6.5小时左右(单卡2080TI)

预测时间：40分钟



baseline分数和排名：

F1-score :0.512621 rank: 10


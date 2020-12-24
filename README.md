# Easy_Entity_Linking
# 模型结构

### 模型一

NER--实体识别模型，由BERT + softmax 构成，这部分还是比较简单的

### 模型二

Similarity---相似句识别模型，这部分相对较复杂一点。

模型输入[[CLS]+实体句+[SEP]+候选句+[SEP]] + [实体句中实体的首尾位置]；

经过BERT输出，得到BERT_Encode；

将实体位置（i~j）向量取平均值；

然后与[cls]位置向量做拼接;

经过sigmoid输出值；

取候选句中最大值作为相似句；

得到知识库id



# 模型数据

数据来自2019年百度中文短文本实体链指大赛

链接：https://pan.baidu.com/s/1nuXnTJHZVA-Tn8J4buUKeA 
提取码：0y32 



# 模型相关库

Tensorflow == 2.0.0

Transformers == 2.0



# 模型效果

训练数据90000条，知识库390000+条

训练数据85000作为训练集

训练数据5000作为测试集

F1值 70%左右




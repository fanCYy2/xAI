## survey1 Towards Faithful Model Explanation in NLP: A Survey

### 1.基于相似度的方法。

通过训练样例提供解释。具体来说,为了解释模型对某个测试样例的 预测,它们会寻找其最相似的训练样例,这些样例位于学习到的表示空间中,作为当 前预测的支持。这类似于人类通过类比来解释自身行为,例如,医生根据过往病例作出 诊断。

### 2.模型内部结构分析
1.神经元分析

2.注意力

### 基于反向传播

1.梯度方法

2.传播方法

### 反事实干预

1.输入干预

特征靶向干预 和 样例靶向干预

2.模型表示干预

神经元靶向干预 和 特征表示靶向干预

### 自解释模型

1.可解释架构

2.生成解释{
    1. 抽取理由(rationable)
    2. 自然语言
}

### 受众
目标受众：不同受众群体对于模型解释可能有不同的目标。
模型开发者可能希望调试模型
同行研究者可能希望了解如何扩展/改进模型;
行业从业者可能希望评估该模型是否符合实际法规
最终用户可能希望验证他们能够安全地依赖模型决策。

## survey2 Explainable AI for Text Classification: Lessons from a Comprehensive Evaluation of Post Hoc Methods

这篇更像是survey + empirical evaluation

他对可解释性的分类很大， 我觉得可以将其看作是可解释性方法的属性。
### 分类（属性）
事前 & 事后

模型无关 & 模型特定

局部 & 群组 & 全局

## survey3 From outputs to insights: a survey of rationalization approaches for explainable text classification
这篇论文着重于rationable解释方法

### 分类

#### 抽取式rationable
1.抽取式方法

分为 multi_task model & pipelined model

简单来说，前者是encoder decoder , decoder负责抽取rationable，决定将那些词作为rationable encoder只输入decoder标记的那些，随后作出预测

而后者是前者的简化版本，encoder 和decoder分开训练

2.注意力方法

#### 生成式rationable

1.text to text

seq2seq：输入一段文本，输出一段文本（解释和标签一起输出）

2.生成式方法
一个生成器和解码器框架

生成器生成解释，解码器基于解释生成预测

## survey4 Post-hoc Interpretability for Neural NLP: A Survey

### 分类

#### input features

确定某个输入特征,例如一个词元,对于给定预测有多重要


#### 对抗样本

找到一种改动，使预测出错（样本本身的标签没变）

#### 相似示例

对于给定的输入示例,一种影响样本解释会从训练数据集中找到一些示例,这些示例从模型理解的角度来看,与输入示例相似。
回答了哪些训练样本影响了预测

#### 反事实

输入需要如何变化,才能使预测不同?（样本本身的标签发生了改变）

#### 自然语言

用自然语言解释

#### 概念

概念解释试图根据输入的抽象来解释模型,这种抽象称为概念。

#### vocabulary

模型如何组织词与词的关系。
例如一个情感分类任务：正面词和负面词在模型内部是否各自聚成一团？
正面词的簇里是否混进了本身没有情感色彩的词，比如某个演员的名字？如果有，可能说明数据集有偏差，模型把这个词和正面评价绑在了一起。
某些词是否带有性别等社会偏见？

#### 集成

把多个局部解释组合起来，形成一个全局解释。（有点和意为）

#### 语言信息
尝试让模型与数百年来发展起来的大量语言学理论保持一致。
模型利用了哪些语言学信息

#### 规则

规则解释试图通过一组简单规则来解释模型

### findings

一个普遍观察是,每种方法的文章通常都会引入自己的功能有据性或人类基础性的衡量指标
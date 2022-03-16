### WuDaoMM

Chinese-Transformer-XL
Under construction

本项目提供了智源研究院"文汇" 预训练模型Chinese-Transformer-XL的预训练和文本生成代码。[应用主页] [模型下载]

数据
本模型使用了智源研究院发布的中文预训练语料WuDaoCorpus 。具体地，我们使用了WuDaoCorpus中来自百度百科+搜狗百科（133G）、知乎（131G）、百度知道（38G）的语料，一共303GB数据。

模型
本模型使用了GPT-3 的训练目标，同时使用能够更好地处理长序列建模的Transformer-XL 替代了GPT中的Transformer。模型的结构与GPT-3 2.7B（32层，隐表示维度2560，每层32个注意力头）基本相同，因为Transformer-XL的结构改动，模型参数增加到了29亿。
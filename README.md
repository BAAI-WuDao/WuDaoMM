###更新 0328
1）修复部分种子失效问题
2）修复种子队列生成问题

### WuDaoMM 数据集
WuDaoMM属于北京智源人工智能研究院WuDaoCorpora开源数据集的一部分。去年我们开源了全球最大中文文本数据集WuDaoText，包含从100TB原始网页数据中清洗得出5TB的文本。今年开源的WuDaoMM是基于中文图文对的多模态数据，WuDaoMM全量数据集约有6.5亿图文对支持了包含文澜、Cogview等大规模中文多模态预训练模型的训练，数据集包含强相关数据5千万对和弱相关数据6亿对。为了便于研究者下载使用，我们开放了WuDaoMM的基线版本WuDaoMM-base，包含500万强相关图文数据对样例。WuDaoMM-base数据集是从强相关数据集每个大类别中均衡组成的的一个子数据集，足以支持当前主流预训练模型研究使用。如果研究者有全量数据需求，可以邮件与我们联系data@baai.ac.cn。WuDaoMM-base包含19个大类，分别为:能源、表情、工业、医疗、风景、动物、新闻、花卉、教育、艺术、人物、科学、大海、树木、汽车、社交、科技、运动等，单类别数据约7万~40万左右。

![0001](doc/0001.png)
:
### 下载

#### 1.下载环境要求

```
python3.6+
pip install aiohttp
```

#### 2.下载json文件

| Keys     | EXPLAIN      |
| -------- | ------------ |
| tag      | 图像类别     |
| url      | 图像下载链接 |
| captions | 图像描述     |
| name     | 图像保存名称 |

json文件包含了所有图像的url以及对应描述格式如下

```
{
"name": "3db6c9414b0c2e3d9978c6b1c285e3ab.jpg"
"tag": "工业",
"url": "http://**********.jpg",
"captions": "天际线,大阪城,日本"
},
```

json文件下载地址:https://data.wudaoai.cn/

### 下载工具使用

Git本项目后，将下载完成的json文件放置在json_dir文件夹下，然后运行download_img_tools.py，如下

```python
python download_img_tools.py
```

所有下载完成后，目录结构如下

```sh
pwd/
	doc
	json_dir
		Art.json
		Industry.json
		...
	Art
		2794f24e361b64bcd4740ed8789b4a17.jpg
	Industry
		3db6c9414b0c2e3d9978c6b1c285e3ab.jpg
	...
```

*注:
- 本程序自带断点续采功能，中断后重新运行脚本即可（程序在下载前会对所有下载任务与当前已完成下载进行比对，自动跳过已下载部分）。
- 由于数据搜集时间长，可能存在部分连接失效情况
- 部分图片链接是国外链接，需要有VPN支持*



### 版权问题

WuDaoMM数据集仅用于学术研究，任何使用该数据集都应该遵循以下要求。WuDaoMM不拥有这些图片的版权。 图片的使用必须遵守[Flickr使用条款](http://creativecommons.org/licenses/by/4.0/)。 图像的用户对使用数据集承担全部责任，不私自传播上面的图片。 如果图片的版权受到侵犯，请联系我们，我们将立即删除。  

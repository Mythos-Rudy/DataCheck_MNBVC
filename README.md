# DataCheck_MNBVC

## 项目描述
针对MNBVC 项目下的数据进行格式检查，要求数据格式满足[现有语料格式](https://wiki.mnbvc.org/doku.php/%E7%8E%B0%E6%9C%89%E8%AF%AD%E6%96%99%E6%A0%BC%E5%BC%8F):


- [QaData-单论对话语料](https://github.com/esbatmop/WikiHowQAExtractor-mnbvc)
- [QaData-多轮对话语料](https://github.com/pany8125/ShareGPTQAExtractor-mnbvc)
- [CodeData-代码语料](https://github.com/esbatmop/githubcode_extractor_mnbvc)
- [ForumData-论坛语料](https://github.com/aplmikex/forum_dialogue_mnbvc)
- [ParallelData-平行语料](https://github.com/liyongsea/parallel_corpus_mnbvc)


## 环境安装
```bash
pip install -r requirements.txt
```

## 运行
```bash
python check_data.py  --dataset data/ --k 100
```

## 运行说明

### 参数说明
- --dataset 待检查的数据文件名或者目录
- --k 抽样检查每个文件top k行

### 输出
- 正确的语料格式：the type of dataset {your data} is ...数据
- 错误的语料格式: can not match data type, the most similar type of dataset {your data} is ...格式, similar score is ...

错误的语料格式会提示错误类型和错误行号(从0 开始)：
- 字段缺失: line: ...: missing error, missing keys: ...
- 字段数据类型错误: line ...: type error, error keys: ..., expected type ...

检查完成后，会提示检查完成：
check dataset {your data} finished, right line ... / total check line ...

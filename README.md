# biaslens

**按子群比较模型输出中的差异。**

`biaslens` —— 对不同子群样本计算指标差异，给出差异幅度与显著性

- 零依赖，Python 3.10+ 标准库即可运行
- 单文件，`biaslens.py` 拷走就能用
- 不联网、不写文件

<!-- ipos:install -->
## 安装

零依赖，Python 3.10+ 即可：

```bash
pip install sraveel-pr-biaslens
```

装完直接用命令名调用：

```bash
biaslens --help
```

也可以不用安装，直接把 `biaslens.py` 拷走用——它只依赖标准库。

## 为什么需要它

样本量不足的子组会先被标出，避免误判

它遵守下面几条自己定的规矩：

1. **只报告能定位到具体位置的结论**，不做语义猜测。
2. **规则表公开**，每条命中都能对应到 偏见子群测试 领域的一条明示规则。
3. **输入为空或格式不对时明确报错**，不静默返回空结果。

## 用法

```bash
python biaslens.py --file input.txt
python biaslens.py --text "示例内容"
python biaslens.py --file input.txt --json
```

加 `--json` 可以拿到机器可读的结果，便于接到流水线里。

## 已知局限

- 比例的分母取自你给的口径，不替你选口径。
- 不判断比例高低是否合理。

## 跑测试

```bash
python test_biaslens.py
```

测试用独立的断言与临时数据，不污染工作目录。

## 来源与参考

- Python 标准库文档：<https://docs.python.org/3/>
- GitHub 仓库：<https://github.com/sraveel-pr/biaslens>

---

## 关于作者

sraveel-pr 做偏见子群测试相关的问题。这个工具先替你回答一个具体问题，再谈别的。

- 个人主页：<https://sraveel-pr.github.io>
- 仓库：<https://github.com/sraveel-pr/biaslens>

## 许可

MIT，见 [LICENSE](LICENSE)。

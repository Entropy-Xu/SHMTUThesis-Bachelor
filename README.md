# 上海海事大学本科毕业论文 LaTeX 模板（SHMTUThesis-benke）

> 本项目是上海海事大学**本科**毕业论文（<font color="red">非官方</font>）LaTeX 模板，基于 [SHMTUThesis](https://github.com/hellckt/SHMTUThesis) 硕士论文模板改造而来。

## 项目介绍

本模板适用于上海海事大学本科毕业论文（设计）的排版。模板格式参考了学校提供的本科毕业论文 Word 模板。

模板包含封面、独创性声明、版权使用授权书、中英文摘要、目录、正文、参考文献、致谢等完整结构。示例文件中包含了公式、表格、算法、参考文献等常用排版示例，可直接基于此撰写论文。

## 环境依赖

- 排版引擎：XeLaTeX
- 文献引擎：Biber
- 字符编码：UTF-8

> 如果编译时出现 XITS、LISU、YOUYUAN 字体缺失错误，请安装 `fonts` 目录中的字体。

## 使用方法

### 编译设置

将排版引擎设置为 `XeLaTeX`，文献引擎设置为 `Biber`，编译即可得到 PDF。

### 命令行编译

```bash
./compile.sh run
```

或手动执行：

```bash
xelatex main.tex
biber main
xelatex main.tex
xelatex main.tex
```

### VSCode

1. 安装 `LaTeX Workshop` 插件
2. 在 `settings.json` 中配置：

```json
"latex-workshop.latex.tools": [{
  "name": "biber",
  "command": "biber",
  "args": ["%DOCFILE%"]
}],
"latex-workshop.latex.recipes": [{
  "name": "xe->bib->xe->xe",
  "tools": ["xelatex", "biber", "xelatex", "xelatex"]
}]
```

3. 打开 `main.tex`，选择 `Recipe: xe->bib->xe->xe` 编译

## 项目结构

```
├── main.tex                        # 论文主体文件
├── shmtuthesis.cls                 # 文档类
├── shmtuthesis-undergraduate.ltx   # 本科论文样式
├── shmtuthesis.sty                 # 附加宏包
├── thesis.bib                      # 参考文献数据库
├── tex/
│   ├── information.tex             # 论文信息（题目、姓名、学院等）
│   ├── abstract.tex                # 中英文摘要
│   ├── introduction.tex            # 绪论示例
│   ├── float.tex                   # 浮动体示例（图、表、算法、代码）
│   ├── math_and_citations.tex      # 数学符号与文献引用示例
│   ├── summary.tex                 # 总结示例
│   └── acknowledgements.tex        # 致谢
├── figures/                        # 图片目录
├── fonts/                          # 字体文件
└── images/                         # 模板图片（校徽、校名）
```

## 致谢

- [SHMTUThesis](https://github.com/hellckt/SHMTUThesis) — 原硕士论文模板，由 hellckt 维护
- [SJTUThesis](https://github.com/sjtug/SJTUThesis) — 上海交通大学论文模板，提供了基础代码
- [CTeX-kit](https://github.com/CTeX-org/ctex-kit) — LaTeX 中文支持

## 软件许可证

- 上海海事大学校徽、校名图片版权归上海海事大学所有
- `shmtuthesis.cls` 及相关文件使用 [LPPL](https://www.latex-project.org/lppl.txt) 授权
- 其他部分使用 [Apache License 2.0](LICENSE) 授权

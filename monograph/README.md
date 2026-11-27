# 从 Theta 提升到广义 Riemann 猜想的证明

这部专著以配套蓝图和上游可读版 Lean 证明为依据，提供中文版与英文版两份成品，共享统一的矢量封面插图：

- 中文版 PDF：[GRH_Monograph.pdf](GRH_Monograph.pdf)
- 英文版 PDF：[GRH_Monograph_EN.pdf](GRH_Monograph_EN.pdf)

两版均在前言之后安排一页竖版证明依赖图，可从目录或前言跳转。图中编号链接至正文对应结果。

- 独立矢量图 [中文版](figures/proof-dependencies.pdf) · [英文版](figures/proof-dependencies-en.pdf)
- PNG 图 [中文版](figures/proof-dependencies.png) · [英文版](figures/proof-dependencies-en.png)
- [节点、依赖边与版式核对](work/proof-dependencies/figure-qa.md)

PDF 内的章、节、定理、图表、封面路线图和公式引用均可跳转，Lean 源码链接固定到上游提交和行号：[上游可读版](https://github.com/lsernau/grh-lean/tree/72fead102f663d5c7a407964a13dc0cf9d977207/grh)。

## 编译

需要 XeLaTeX、latexmk、biber、ctex、biblatex、tcolorbox、TikZ，以及 Noto CJK、AR PL UKai CN、TeX Gyre Pagella 与 TeX Gyre Heros 字体。

编译中文版（在本目录运行）：

```bash
latexmk -xelatex -interaction=nonstopmode -halt-on-error GRH_Monograph.tex
```

编译英文版（在 `en/` 目录运行）：

```bash
cd en && latexmk -xelatex -interaction=nonstopmode -halt-on-error GRH_Monograph_EN.tex
```

如需重新生成临界带零点与 Hardy $Z(t)$ 曲线数据（需 `mpmath`）：

```bash
python3 figures/plot_critical_strip.py
```

## 源码结构

- [GRH_Monograph.tex](GRH_Monograph.tex) 组装中文全书，版式、脚注与链接宏在 [preamble.tex](preamble.tex)，参考文献数据库见 [references.bib](references.bib)。
- [frontmatter.tex](frontmatter.tex) 放置中文封面、内容提要和目录，[preface.tex](preface.tex) 收录前言，正文分八章放在 `chapters/`，附录见 [backmatter.tex](backmatter.tex)。
- `en/` 收录完整英文版源码（[GRH_Monograph_EN.tex](en/GRH_Monograph_EN.tex)、[preamble.tex](en/preamble.tex)、[frontmatter.tex](en/frontmatter.tex)、[preface.tex](en/preface.tex)、`en/chapters/` 与 [backmatter.tex](en/backmatter.tex)）。
- `figures/` 收录中英文共用的 TikZ 封面插图 [cover-illustration.tex](figures/cover-illustration.tex)、高精度数据生成脚本 [plot_critical_strip.py](figures/plot_critical_strip.py) 与生成的坐标数据 [critical-strip-data.tex](figures/critical-strip-data.tex)。
- [来源与核对范围](work/source-ledger.md) 和 [数学复核提要](work/content-review-guide.md) 记录正文、蓝图与形式化源码的对应。

# 从 Theta 提升到广义 Riemann 猜想

这部中文专著以配套蓝图和上游可读版 Lean 证明为依据。阅读成品见 [GRH_Monograph.pdf](GRH_Monograph.pdf)。PDF 内的章、节、定理、图表和公式引用可跳转。Lean 源码链接固定到上游提交和行号。 [上游可读版](https://github.com/lsernau/grh-lean/tree/72fead102f663d5c7a407964a13dc0cf9d977207/grh)

## 编译

需要 XeLaTeX、latexmk、biber、ctex、biblatex、tcolorbox、TikZ，以及 Noto CJK 和 AR PL UKai CN 字体。在本目录运行

    latexmk -xelatex -interaction=nonstopmode -halt-on-error GRH_Monograph.tex

## 源码结构

- [GRH_Monograph.tex](GRH_Monograph.tex) 组装全书，版式、脚注与链接宏在 [preamble.tex](preamble.tex)，参考文献数据库见 [references.bib](references.bib)。
- [frontmatter.tex](frontmatter.tex) 放置封面、内容提要和目录。[preface.tex](preface.tex) 收录整篇前言。
- [ch01.tex](chapters/ch01.tex) 定义容许数据、扭转格和五类 Theta 提升，证明主不等式和解析归约。
- [ch02.tex](chapters/ch02.tex) 处理 CM 形式群、Theta 导数整除性和系数估值。
- [ch03.tex](chapters/ch03.tex) 证明 Seesaw 恒等式及定理 A(a)、A(b)。
- [ch04.tex](chapters/ch04.tex) 证明 Poincaré 映射的二阶矩估计和定理 B。
- [ch05.tex](chapters/ch05.tex) 分解链行列式，合成定理 C 的余体积估计。
- [ch06.tex](chapters/ch06.tex) 建立单步比较算子、伪提升正交性和高度界。
- [ch07.tex](chapters/ch07.tex) 构造正则 Selmer 扭转族并控制同余分母。
- [ch08.tex](chapters/ch08.tex) 证明离散序列周期的量化模长估计。
- [来源与核对范围](work/source-ledger.md) 和 [数学复核提要](work/content-review-guide.md) 记录正文、蓝图与形式化源码的对应。

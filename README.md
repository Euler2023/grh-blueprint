# RH 与 GRH 的 Lean 证明蓝图与中英文专著

**简体中文** · [English](README.en.md)

## Lean 证明蓝图

这份中文蓝图根据上游项目 [lsernau/grh-lean](https://github.com/lsernau/grh-lean) 的可读版 Lean 证明编写，导读其中的五条公开定理。正文从几何数据和带权素数余项出发，逐步说明定理 A、B、C、主不等式及其到零点结论的证明链。HTML 版附有交互依赖图，节点可跳转至相应陈述和 Lean 源码。

- [在 GitHub 预览 PDF](blueprint.pdf) · [下载 PDF](https://github.com/Euler2023/grh-blueprint/releases/latest/download/blueprint.pdf)
- [下载 HTML 阅读包](https://github.com/Euler2023/grh-blueprint/releases/latest/download/grh-blueprint-html.zip)
- [查看发布版本](https://github.com/Euler2023/grh-blueprint/releases)

## 中英文专著

《从 Theta 提升到广义 Riemann 猜想的证明》（*From Theta Lifts to the Proof of the Generalized Riemann Hypothesis*）以蓝图为基础，详述 Theta 提升和主不等式的证明，并说明如何由主不等式推出 Riemann 猜想与 Dirichlet $L$ 函数的广义 Riemann 猜想。正文中的 Lean 链接指向上游源码的固定提交和行号，现同时提供中文版与英文版。

- [在 GitHub 预览中文专著 PDF](monograph/GRH_Monograph.pdf)
- [在 GitHub 预览英文专著 PDF](monograph/GRH_Monograph_EN.pdf)
- [LaTeX 源码与编译说明](monograph/README.md)

## Updates

- **2026-11-27**：新增完整英文版专著（`monograph/GRH_Monograph_EN.pdf` 及 `monograph/en/` 源码）；更新中文版专著修订内容与中英文书名；重绘中英文共用的全矢量 TikZ 封面插图（含 50 位精度 Hardy $Z(t)$ 曲线、前六个非平凡零点与可点击跳转的证明路线图）。

## 本地阅读 HTML

解压 ZIP，进入 `grh-blueprint-html` 目录，运行以下命令，然后访问 [蓝图首页](http://127.0.0.1:8765/)。

```bash
python3 -m http.server 8765 --bind 127.0.0.1
```

公式和依赖图使用包内的 MathJax 和 Graphviz 资源。源码链接需要联网。要使用 PDF 中的源码链接，请下载后用本地 PDF 阅读器打开。

## 来源与署名

蓝图以可读版 GRH Lean 证明为依据。该版本由 Anthropic 基于 Levent Alpöge 的 Lean 证明改写。正文和依赖图中的源码链接固定到上游提交和具体行号。 [可读版 Lean 源码](https://github.com/lsernau/grh-lean/tree/72fead102f663d5c7a407964a13dc0cf9d977207/grh) · [锁定的 Mathlib 版本](https://github.com/leanprover-community/mathlib4/tree/56a005855ea17e0b0958f73ec801ae140b0a1679)

随附上游的 [LICENSE](LICENSE)、[NOTICE](NOTICE) 和 [ATTRIBUTION.md](ATTRIBUTION.md)。

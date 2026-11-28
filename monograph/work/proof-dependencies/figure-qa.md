# 全书证明依赖图成图与核对

## 版式

按书内竖版 A4 设计。使用五列对齐 A、B、C 的前置结果，第 8 章的实位周期分接 B 和 C。主不等式位于页面中轴，两组解析输入汇入右半平面无零点，页底呈现五条公开定理的实际推出关系。箭头沿节点间的空隙布置，容易混淆的交叉处用白色间隔区分。

中英文共用同一份 TikZ 坐标和路径。连同图下的跨章导航，图框为 153 × 224 mm，适配两版约 153 × 226 mm 的书内版心。普通节点用 9.5 pt 字号和 11.15 pt 行距，关键节点用 11 pt，页题用 18 pt。独立 PDF 各一页，页面尺寸为 210 × 297 mm，PNG 以 180 dpi 渲染。

## 数学与版面复核

- 39 个节点和 45 条有类型的箭头逐一对应获审的 Mermaid 草图及[边表](dependency-edges.csv)。两版各 312 个编号结果都与[节点表](dependency-ledger.csv)相符。
- 定理 1.72 的框内写明 Dirichlet \(L\) 函数、\(\operatorname{Re}s>1/2\) 与主特征 \(s=1\) 的例外。英文版同时明确了秩差一的限制和定理 1.80 的临界带假设。
- 坐标验证器报告 0 个错误和 15 个短箭头提示。紧邻节点之间的箭身与箭头在 180 dpi 整页渲染及局部检查时可辨。
- 两版图页的重叠检查均为 0 个错误。逐项核对了行距、线端附近的文字包围框和必要的线交叉提示。两版 PDF 的实际路径与 39 个节点的矩形内部均无交叠，文本笔画均可读。
- 独立复核指出的两处贴框连线已移开。复核者重新检查终稿，中文版、英文版的连线离无关框边最小净距分别为 1.45 pt、1.12 pt。中英文独立图和书内图页均经整页视觉检查。
- 两版独立图由 XeLaTeX、xdvipdfmx 生成。日志无缺字、字体替换或箱体溢出，PDF 的图页经检测为矢量。整书编译的字体提示与箱体提示位于图页之外。

## 书内位置与跳转

| 版本 | 图页页码 | PDF 页序 | 第 1 章 PDF 页序 | 图中结果链接 |
| --- | --- | ---: | ---: | ---: |
| 中文 | xiv | 14 | 15 | 74 / 74 |
| English | xii | 12 | 13 | 74 / 74 |

目录和前言的入口均跳到对应图页。通过两版辅助文件与 PDF 批注逐项核对，图上 74 个入口各自指向预期目标，点击区域无重叠。图下可沿 2.16 到 6.5、7.1 到 6.6 和 6.48、6.48 与 7.45 到 5.3 跳转。第 8 章的驻相周期、Bessel 测试、秩差一限制有三个独立落点。两条应用分别往返引理 4.1 和引理 5.1，各版额外核对 20 处正文跨章链接。

## 重建独立图

在 `monograph/figures/` 运行以下命令。两版整书按照[专著编译说明](../../README.md)重编。

```sh
xelatex -interaction=nonstopmode -halt-on-error proof-dependencies.tex
xelatex -interaction=nonstopmode -halt-on-error -jobname=proof-dependencies-en '\def\ProofMapEnglish{}\input{proof-dependencies.tex}'
pdftoppm -png -r 180 -singlefile proof-dependencies.pdf proof-dependencies
pdftoppm -png -r 180 -singlefile proof-dependencies-en.pdf proof-dependencies-en
```

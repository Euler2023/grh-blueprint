# 全书证明依赖图草案

箭头指向使用该结果的证明。实线表示直接依赖，灰色虚线表示技术输入，蓝色虚线表示互补情形汇合，点线表示推出或特化。

合并节点的证据按具体定理、引理或 Lean 声明记录。书内成图以蓝色编号和图下的跨章导航作为跳转入口。第 8 章的驻相周期、Bessel 测试和秩差一限制分别定位。

## 书内版式

前言之后、第 1 章之前安排一张竖版 A4 专页，沿用书内约 153 mm × 226 mm 的版心。图从上往下读。上部把 A、B 的分支放在左侧、C 的分支放在右侧，第 8 章的实位周期用两条线接入 B 和 C。中部以主不等式为汇合点。下部沿单侧界、Landau 判据和右半平面无零点下行，页底展开五条公开定理。每个框用结果编号和简短结论，印刷字号在排版时核对。

```mermaid
flowchart TB
  subgraph band1["A　提升范数与格指数"]
    direction TB
    jets["定理 2.5、引理 2.8<br/>Taylor 正规形与导数赋值"]:::upper
    cases["定理 3.20 及第 3.2–3.4 节有关引理<br/>各类有限位的整除性与格余长"]:::upper
    loss["引理 3.48<br/>复合提升的统一局部损失"]:::upper
    short["引理 3.4、3.7<br/>短整形式与复合提升范数"]:::upper
    ramified["引理 3.5–3.6<br/>分歧源空间的余维"]:::upper
    seesaw["定理 3.65<br/>上下提升链的 Seesaw 恒等式"]:::upper
    a1["定理 3.66 · A(a)<br/>提升平方范数上界"]:::upper
    a2["定理 3.67 · A(b)<br/>局部格指数上界"]:::upper
  end
  subgraph band2["实位周期下界"]
    direction TB
    laplace["引理 8.3、定理 8.4<br/>实位周期积分的 Laplace 下界"]:::period
    stationary["§8.4<br/>驻相位置群上的周期下界"]:::period
  end
  subgraph band3["B　少量平移的张成"]
    direction TB
    bessel["§8.4 的 Bessel 应用<br/>构造归一化实位测试"]:::spanning
    moments["引理 4.1、4.30、4.45 等<br/>Petersson 展开与近等距<br/>Poisson 筛与二阶矩"]:::spanning
    b["定理 4.46 · B<br/>少量平移像近乎张成"]:::spanning
  end
  subgraph band4["C　提升余体积下界"]
    direction TB
    coeff["引理 2.16<br/>第一块导数系数的有限位下界"]:::volume
    hecke["引理 6.5–6.7<br/>测试配对与逆 Hecke 值比"]:::volume
    comp["引理 6.46–6.47<br/>比较算子与正交压缩"]:::volume
    regular["定义 7.1、引理 7.20、7.43–7.45<br/>同步选取正则扭转与控制投影分母"]:::volume
    single["引理 6.48<br/>单步 Gram 行列式比的高度"]:::volume
    sync["引理 5.3<br/>同一扭转族控制全部单步"]:::volume
    factor["引理 5.2<br/>整链 Gram 行列式比的分解"]:::volume
    restriction["§8.4 的秩差一特例<br/>深层限制形式张成"]:::volume
    aux["引理 5.1<br/>具有整提升的辅助形式"]:::volume
    c["定理 5.4 · C<br/>提升余体积下界"]:::volume
  end
    star["定理 1.33 · 主不等式<br/>mS ≤ fa(log b)⁵"]:::main
  subgraph band5["从主不等式到素数幂余项"]
    direction TB
    normalize["引理 1.20、1.47<br/>双尺度恒等式与归一化上界"]:::analysis
    scales["引理 1.45–1.46<br/>大尺度容许数据的存在性"]:::analysis
    far["引理 1.48–1.49<br/>固定模数素数定理与大尺度余项"]:::analysis
    one["引理 1.50、定理 1.51<br/>素数幂余项的单侧界"]:::analysis
  end
  subgraph band6["右半平面无零点"]
    direction TB
    qtwist["引理 1.60、1.65–1.68<br/>Theta 尾积分、坏素数计数与二次扭转"]:::analysis
    residues["引理 1.69–1.70<br/>余项变换的留数与 Landau 引理"]:::analysis
    criterion["定理 1.71<br/>Landau 型无零点判据"]:::analysis
    half["定理 1.72<br/>右半平面无零点"]:::analysis
  end
  subgraph band7["五条公开定理"]
    direction TB
    zsym["引理 1.76<br/>ζ 函数的零点对称性"]:::public
    lsym["引理 1.74–1.75<br/>Dirichlet L 函数的零点对称性"]:::public
    rh["定理 1.77<br/>Riemann 猜想"]:::public
    zline["定理 1.78<br/>ζ 非平凡零点的临界线形式"]:::public
    grh_half["定理 1.79<br/>广义 Riemann 猜想的半平面形式"]:::public
    grh_line["定理 1.80<br/>临界带零点的临界线结论"]:::public
    grh_primitive["定理 1.81<br/>本原 Dirichlet 特征的特例"]:::public
  end
  jets -.-> cases
  cases -. 互补情形 .-> loss
  short --> a1
  ramified --> a1
  ramified --> a2
  seesaw --> a1
  seesaw --> a2
  loss -.-> a1
  loss --> a2
  laplace -.-> stationary
  stationary -.-> bessel
  bessel -.-> moments
  moments --> b
  ramified --> b
  coeff -.-> hecke
  regular -.-> hecke
  regular -.-> single
  comp --> single
  hecke --> single
  regular --> sync
  single --> sync
  stationary -.-> restriction
  restriction -.-> aux
  aux --> c
  factor --> c
  sync --> c
  a1 --> star
  a2 --> star
  b --> star
  c --> star
  star --> normalize
  normalize --> one
  scales --> one
  far --> one
  qtwist --> criterion
  residues --> criterion
  criterion --> half
  one --> half
  half --> rh
  zsym --> rh
  rh -.-> zline
  half -.-> grh_half
  half --> grh_line
  lsym --> grh_line
  grh_line -.-> grh_primitive
  classDef upper fill:#eff4fa,stroke:#416389,color:#162c45
  classDef period fill:#edf5f8,stroke:#49768b,color:#173542
  classDef spanning fill:#edf6f3,stroke:#3f7f70,color:#16362f
  classDef volume fill:#f8f0f2,stroke:#906474,color:#42232c
  classDef main fill:#eaeef7,stroke:#2b3d63,color:#142038,stroke-width:2px
  classDef analysis fill:#faf5e8,stroke:#8a7545,color:#3f3219
  classDef public fill:#f2f0f8,stroke:#6d608d,color:#291f3d
  linkStyle 0,7,10,11,14,15,16,22 stroke:#687683,stroke-width:1.1px,stroke-dasharray:5 3
  linkStyle 9,21,40,41,44 stroke:#65707d,stroke-width:1px,stroke-dasharray:1 3
  linkStyle 1 stroke:#356495,stroke-width:1.4px,stroke-dasharray:5 3
```

定理 1.72 同时使用定理 1.51 的单侧界和定理 1.71 的判据。第 7 章的正则性条件用于第 6 章的条件估计，正则族的存在性则在引理 5.3 中用来实际选取扭转。

完整的结果索引、逐边证据及分组说明见 [结果表](dependency-ledger.csv)、[边表](dependency-edges.csv) 和 [核对记录](dependency-audit.md)。


# 概要

中先生の交代磁性の論文Spin current generation in organic antiferromagnets
[リンク](https://www.nature.com/articles/s41467-019-12229-y)
と「交替磁性体のスピン分裂と交差相」(固体物理2024-05)の中に出てくる
κ-(ET)2-X についての計算についてのフォルダである。

# 構造

ノート兼実行環境用の jupyter notebook とスクリプト用の `funcs.py` の2つが本体である。
`funcs.py` の中には計算で使う関数や定数と、
相互作用の大きさと電子密度、メッシュのサイズを変えた κ-(ET)2-X を
1つのオブジェクトとするための class になっている。

クラスの中には
計算をするためのメソッド

- `calc_scf()`: 自己無撞着計算をする
- `calc_nscf()`: scf 計算で得られたフェルミエネルギーと反強磁性磁化の大きさをもとに
エネルギー分散とその固有状態を求める
- `calc_dos()`: 状態密度を求める
- `calc_kF_index()`: ブリュアンゾーンをメッシュに切ったときのフェルミ波数のインデックスを求める **(工事中)**
- `calc_spin_conductivity(mu, nu)`: スピン伝導度を求める **(工事中)**
- `calc_conductivity(mu, nu)`: 電気伝導度を求める **(工事中)**

と表示をするためのメソッド

- `plot_nsite()`: scf 計算の各ステップにおける各サイトを占有する電子の数
- `plot_scf()`: scf 計算の各ステップにおけるフェルミエネルギーと反強磁性磁化の大きさ
- `plot_band()`: ブリュアンゾーンのパスに沿ったエネルギー分散
- `plot_dos()`: 状態密度
- `plot_fermi_surface()`: フェルミ面の表示 **(工事中)**
- `plot3d_band()`: バンド分散を3次元で表示

が用意されている。

docstring を簡単には書いてあるので詳細は `funcs.py` を解読するとわかるはず
(わかりくかったらごめんなさい)。

`資料/`は元論文や関連資料が入っている。

`output/`は計算に時間がかかるものの出力結果を入れている。
ただ、計算が合っていないものも入っていたりするので気を付けてほしい。
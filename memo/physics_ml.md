# 物理の力学系、特に解析力学を事前知識としたニューラルネットとその応用

https://blog.albert2005.co.jp/2020/07/17/mechanical-system-nn/

# はじめに
## なぜ力学系の知識を使うのか？
解析的に解けない問題へのアプローチ

従来：第一原理計算
→ 支配方程式の係数がわからない場合が困る
網羅的に第一原理計算をして係数を求めるのは計算量的に困難

1. 機械学習でパラメータを推定
2. 推定したパラメータで方程式を組み立て、それから物理現象を予測する

その機械学習の効率を高めるために力学の理論を入れる
→ エネルギー保存など基本原則を外れたケースを学習から排除できる

# NNによる力学系の分類

* 具体的な微分方程式を一般的に解く “NN-based PDE solver”
* 時空間に関する微分方程式を解く “Physics-informed NN”
* 剛体力学における抽象的な方程式を解く “解析力学的NN”

## 1. NN-based PDE solver
例：ポアソン方程式

\nabla^2 u(x) = f(x)

f(x)を入力、u(x)を出力とするネットワークを作る

実際、関数はグリッド状なので、Conv2Dが有効

## 2. Physics-Informed Neural Network
微分方程式を損失関数としてハードコードし、微分方程式の解を出力する

参考： https://blog.albert2005.co.jp/2020/07/10/numerical-simulation-through-deeplearning/

KdV方程式を解いた例：
https://www.sciencedirect.com/science/article/pii/S0021999117309014

https://www.sciencedirect.com/science/article/pii/S0021999118307125


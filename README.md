# shocktube_2
## Reference
- Zhiping Mao, Ameya D. Jagtap, George Em Karniadakis, "Physics-informed neural networks for high-speed flows", Comput. Methods Appl. Mech. Engrg. 360 (2020) 112789.
-- 解析対象

- 宮本 崇, 西尾 真由子, 全 邦釘, "Physics-Informed Neural Networksによる1次元連続体の動的解析", AI・データサイエンス論文集2021 年 2 巻 J2 号 p. 152-156
-- コードを流用

## preについて
- Zhiping Maoら(2020)の3.1の類似問題を解析した
-- 数式については論文とは違い
$$\frac{\partial \rho}{\partial t} + \frac{\partial \rho u}{\partial x} = 0 $$
$$\frac{\partial \rho u}{\partial t} + \frac{\partial \rho u^2 + p}{\partial x}  = 0 $$
$$\frac{\partial E_t}{\partial t} + \frac{(E_t+p)u}{\partial x}  = 0 $$
-- ただし, $\rho(e+u^2/2)$であり, $e=\frac{p}{(\gamma-1)\rho}$である.
-- 0以下では$U(\rho, u, p)=(100, 1, 1)$, 0以上では$U(\rho, u, p)=(1, 1, 1)$で計算をしている

## 本体について
- Zhiping Maoら(2020)の4.1.1の類似問題を解析した
-- 数式については論文とは違い
$$\frac{\partial \rho}{\partial t} + \frac{\partial \rho u}{\partial x} = 0 $$
$$\frac{\partial \rho u}{\partial t} + \frac{\partial \rho u^2 + p}{\partial x}  = 0 $$
$$\frac{\partial E_t}{\partial t} + \frac{(E_t+p)u}{\partial x}  = 0 $$
-- ただし, $\rho(e+u^2/2)$であり, $e=\frac{p}{(\gamma-1)\rho}$である.
-- 衝撃波管の教師データはfortranによって作った
-- また教師データとして境界条件・初期条件・ある時刻の密度のデータを使っている

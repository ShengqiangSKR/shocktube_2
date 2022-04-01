# shocktube_2
## Reference
- Zhiping Mao, Ameya D. Jagtap, George Em Karniadakis, "Physics-informed neural networks for high-speed flows", Comput. Methods Appl. Mech. Engrg. 360 (2020) 112789.
- 解析対象

- 宮本 崇, 西尾 真由子, 全 邦釘, "Physics-Informed Neural Networksによる1次元連続体の動的解析", AI・データサイエンス論文集2021 年 2 巻 J2 号 p. 152-156
- コードを流用

## preについて
- Zhiping Maoら(2020)の3.1の類似問題を解析した
- 数式については論文とは違い
<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cfrac%7B%5Cpartial+%5Crho%7D%7B%5Cpartial+t%7D+%2B+%5Cfrac%7B%5Cpartial+%5Crho+u%7D%7B%5Cpartial+x%7D+%3D+0+" 
alt="\frac{\partial \rho}{\partial t} + \frac{\partial \rho u}{\partial x} = 0 ">

<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cfrac%7B%5Cpartial+%5Crho+u%7D%7B%5Cpartial+t%7D+%2B+%5Cfrac%7B%5Cpartial+%5Crho+u%5E2+%2B+p%7D%7B%5Cpartial+x%7D++%3D+0" 
alt="\frac{\partial \rho u}{\partial t} + \frac{\partial \rho u^2 + p}{\partial x}  = 0">

<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cfrac%7B%5Cpartial+E_t%7D%7B%5Cpartial+t%7D+%2B+%5Cfrac%7B%5Cpartial+%28E_t%2Bp%29u%7D%7B%5Cpartial+x%7D++%3D+0" 
alt="\frac{\partial E_t}{\partial t} + \frac{\partial (E_t+p)u}{\partial x}  = 0">

- ただし, <img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+Et+%3D+%5Crho%28e%2Bu%5E2%2F2%29" 
alt="Et = \rho(e+u^2/2)">であり, <img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+e%3D%5Cfrac%7Bp%7D%7B%28%5Cgamma-1%29%5Crho%7D" 
alt="e=\frac{p}{(\gamma-1)\rho}">である.
- 0以下では<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+U%28%5Crho%2C+u%2C+p%29%3D%28100%2C+1%2C+1%29" 
alt="U(\rho, u, p)=(100, 1, 1)">, 0以上では<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+U%28%5Crho%2C+u%2C+p%29%3D%281%2C+1%2C+1%29" 
alt="U(\rho, u, p)=(1, 1, 1)">で計算をしている

## 本体について
- Zhiping Maoら(2020)の4.1.1の類似問題を解析した
- 数式については論文とは違い
<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cfrac%7B%5Cpartial+%5Crho%7D%7B%5Cpartial+t%7D+%2B+%5Cfrac%7B%5Cpartial+%5Crho+u%7D%7B%5Cpartial+x%7D+%3D+0+" 
alt="\frac{\partial \rho}{\partial t} + \frac{\partial \rho u}{\partial x} = 0 ">

<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cfrac%7B%5Cpartial+%5Crho+u%7D%7B%5Cpartial+t%7D+%2B+%5Cfrac%7B%5Cpartial+%5Crho+u%5E2+%2B+p%7D%7B%5Cpartial+x%7D++%3D+0" 
alt="\frac{\partial \rho u}{\partial t} + \frac{\partial \rho u^2 + p}{\partial x}  = 0">

<img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+%5Cfrac%7B%5Cpartial+E_t%7D%7B%5Cpartial+t%7D+%2B+%5Cfrac%7B%5Cpartial+%28E_t%2Bp%29u%7D%7B%5Cpartial+x%7D++%3D+0" 
alt="\frac{\partial E_t}{\partial t} + \frac{\partial (E_t+p)u}{\partial x}  = 0">

- ただし, <img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+Et+%3D+%5Crho%28e%2Bu%5E2%2F2%29" 
alt="Et = \rho(e+u^2/2)">であり, <img src=
"https://render.githubusercontent.com/render/math?math=%5Ccolor%7Bblack%7D%5Cdisplaystyle+e%3D%5Cfrac%7Bp%7D%7B%28%5Cgamma-1%29%5Crho%7D" 
alt="e=\frac{p}{(\gamma-1)\rho}">である.
- 衝撃波管の教師データはfortranによって作った
- また教師データとして境界条件・初期条件・ある時刻の密度のデータを使っている

# Deep-Reinforcement-Learning-Book
[書籍「つくりながら学ぶ！深層強化学習」、著者：株式会社電通国際情報サービス 小川雄太郎、出版社: マイナビ出版 (2018/6/28) ](https://www.amazon.co.jp/%E3%81%A4%E3%81%8F%E3%82%8A%E3%81%AA%E3%81%8C%E3%82%89%E5%AD%A6%E3%81%B6-%E6%B7%B1%E5%B1%A4%E5%BC%B7%E5%8C%96%E5%AD%A6%E7%BF%92-PyTorch%E3%81%AB%E3%82%88%E3%82%8B%E5%AE%9F%E8%B7%B5%E3%83%97%E3%83%AD%E3%82%B0%E3%83%A9%E3%83%9F%E3%83%B3%E3%82%B0-%E6%A0%AA%E5%BC%8F%E4%BC%9A%E7%A4%BE%E9%9B%BB%E9%80%9A%E5%9B%BD%E9%9A%9B%E6%83%85%E5%A0%B1%E3%82%B5%E3%83%BC%E3%83%93%E3%82%B9-%E5%B0%8F%E5%B7%9D%E9%9B%84%E5%A4%AA%E9%83%8E/dp/4839965625)のサポートリポジトリです。


最下部に正誤表を記載しております。




<img src="./movies/book.jpg" width="300px">

<img src="./movies/7_breakout.gif" width="600px">
図　ブロック崩しを攻略（A2Cを使用し、GPU1枚で3時間の学習後）

<img src="./movies/2_2_maze_random.gif" width="300px">
図　迷路をランダムに移動

<img src="./movies/2_3_maze_reinforce.gif" width="300px">
図　迷路を強化学習

<img src="./movies/2_5_maze_state_value.gif" width="300px">
図　迷路内の各位置の価値を学習

<img src="./movies/3_4_cartpole_q_learning.gif" width="600px">
図　倒立振子を制御


### 正誤表

[1] 初版：p. 46

パラメータθの更新量の式において、符号がマイナスであるべき部分がプラスになっていました。これに伴い以下3点の修正をお願いします。

```
[1-1] p. 46 式（2行目）
⊿θ_{s, a_j} = {N(s_i, a_j) + P(s_i, a_j) N(s_i, a)} / T
↓
⊿θ_{s, a_j} = {N(s_i, a_j) - P(s_i, a_j) N(s_i, a)} / T


[1-2] p. 47 コード（上段）
delta_theta[i, j] = (N_ij + pi[i, j] * N_i) / T
↓
delta_theta[i, j] = (N_ij - pi[i, j] * N_i) / T


[1-3] p. 48 コード
stop_epsilon = 10**-8
↓
stop_epsilon = 10**-4
```




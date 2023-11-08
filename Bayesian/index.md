# ベイズ統計学

## 事前情報

最も確率密度が高くなる横軸の値を **最頻値(mode)** という。

コイン投げの例を考える。
適当な例を考えると、今得られているデータを元に考えると、表が出る最も確率が高いのは0.56である。
2値ならば、ベータ分布を使うことが多い。

## ベイズの定理

最初に押さえておくべき式として、以下のものが必要になる。

$$
p(\theta | data) = \frac{p(data | \theta) \cdot p(\theta)}{p(data)}
$$

$\theta : 推定誤差, p(\theta): 事前分布, data : データ, p(data | \theta):尤度, p(data):規格化定数, p(\theta | data):事後分布$となる。

上の式は、得られたデータを使って推定対象 $\theta$
の分布をアップデートする式である。

## 最尤法

尤度を最大にするような推定手法。以下のような例を考える。

$$
p(1|\theta) = \theta \\
p(0|\theta) = 1 - \theta
$$

表、裏、表、裏、表で計算する例とする。

$$
p(10101 | \theta) = \theta \cdot (1 - \theta) \cdot \theta \cdot (1 - \theta) \cdot \theta \\
= \theta^{3} \cdot (1 - \theta)^{2}
$$

100回だったら、 $p(data|\theta)=\theta^{56}\cdot (1-\theta)^{44}$
として計算できる。 表の出る確率 $\theta$
の推定値は、上の式が最大になるような $\theta$
となる。この場合、ベータ分布の最頻値 $0.56$ となる。

## ベイズアプローチ

$p(data|\theta)=\theta^{56}\cdot (1-\theta)^{44}$
をベイズの定理に代入する。
Q1: ALS都有哪些应用场景?
A1:
ALS的矩阵分解算法常应用于推荐系统中，将用户(user)对商品(item)的评分矩阵，分解为用户对商品隐含特征的偏好矩阵，和商品在隐含特征上的映射矩阵。有以下2大应用场景：
评分预测（Rating Prediction） 主要用于用户对商品有明确的评价矩阵的场景。如：用户对电影的评分、对看过的书的评分。
Top-N推荐（Item Ranking） 用户没有明确的反馈对商品的偏好，而是通过一些行为隐式的反馈。如：对商品的购买次数、对电视节目收看的次数或者时长，这时我们可以推测次数越多，看得时间越长，用户的偏好程度越高，但是对于没有购买或者收看的节目，可能是由于用户不知道有该商品，或者没有途径获取该商品，我们不能确定的推测用户不喜欢该商品。所以引入置信度$c_{ui}=1+\alpha r_{ui}$，通过用户的隐式反馈，为用户提供一个可能感兴趣的Item列表。
Q2: ALS进行矩阵分解的时候，为什么可以并行化处理?
A2:
矩阵相乘过程中，评分矩阵R中的每个元素都是可以独立计算的，即彼此之间并无依赖性；每个元素都是由用户矩阵的对应行与商品矩阵的对应列内积所得，行向量之间无关、列向量之间无关。所以可以使用并行处理，从而提高矩阵相乘的计算效率。

Q3: 梯度下降法中的批量梯度下降（BGD），随机梯度下降（SGD），和小批量梯度下降有什么区别（MBGD）
A3:
BGD批量梯度下降：
在每次更新时使用所有样本
稳定，但收敛慢；
SGD随机梯度下降：
每次更新时随机使用一个样本，用它来近似所有的样本
更快收敛、最终解在全局最优解附近；
MBGD小批量梯度下降：
每次更新时用b个样本，是BGD和SGD的折中方法
速度较快。
Q4 你阅读过和推荐系统/计算广告/预测相关的论文么？有哪些论文是你比较推荐的，可以分享到微信群中
A4:
现在英文原文阅读水平还不够，还没有读过。现在只能看二手信息。在提高英语中，争取下个月可以读懂原文。


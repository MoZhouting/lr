# lr
基于LR的优化方法：梯度下降法，随机梯度下降法，牛顿法，LBFGS，BFGS
是梯度下降还是梯度上升取决于求最大值还是最小值，而且要确保函数是凸的或者凹的。这样才能保证收敛到全局最优点。
梯度下降法所需要的alpha即步长是要改变的，而且有两种方法去提高：一种把特征进行归一化，这样收敛比较快，另一种是随着越接近真值越要改变步长。步长要越小。
牛顿下降法可应用于多个方面，比如sqrt函数的求解。但牛顿法在计算多维变量的时候出现的海森矩阵是个大问题，即二阶导数。因此需要估计。
LR回归是一种分类方法，我们都知道有很多分类方法，但是为什么需要逻辑回归，试想我想区分出那个浓度是最佳加工条件，
那么有时候浓度在5g附近是最佳的，大于10可能就饱和了，就好像迟滞回线的形式，因此需要一个能够刻画自变量变化的函数，
sigmod函数，就是接近时变化最快，远离是变化比较慢。下面就是数学家们怎么找到sigmoid函数的形式了，我仅能猜测出他是一个s行的。
不过他的导数最好有和为定值的乘积。其值在某个值附近波动很大，那么就行控制中的微分环节一样，引入变化率加入系统，同时sigmod 也变化率也可以改变。
当然这不是初衷，如果我们是分类的话，
我肯定是希望点得到概率越大越好这样我判断。这要先从事件发生的机率来解释，几率是发生概率比上不发生的概率，几率大就发送大些，几率小就比较难发生，在sigmod函数中两个概率相等是分类边界。然后小距离内波动距离，大距离时就饱和了，这也满足事物的一般特征。前面加浓度的例子。（非线性的吧一句话）
下面就是怎么刻画损失函数了，我们有数据和标签，那么怎么才能确定最佳的w，肯定是最大释然，但怎么去刻画
因为是分类问题，前面的感知器用函数间隔，那么我就要确保
我要的只要是分类正确的就是增大的，这样去求最大值就行。就是都满足了，这样最大释然函数也出来了（p）**y（1-p）**（1-y）
下面就是优化的问题，梯度下降法，这里我感觉这并不是凸函数，所以优化时要注意。
随机梯度下降法结果：
![image](https://github.com/chenglu66/lr/blob/master/figure_1-1.png)
批量梯度下降法结果：
![image](https://github.com/chenglu66/lr/blob/master/figure_1-2.png)
一般随机梯度下降法结果：
![image](https://github.com/chenglu66/lr/blob/master/figure_1-3.png)
从图中可以看出是算法没收敛，可以看到w的曲线因此加大迭代次数到9000可以得到，
![image](https://github.com/chenglu66/lr/blob/master/123.png)

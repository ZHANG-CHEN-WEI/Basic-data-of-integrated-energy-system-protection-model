# Basic-data-of-integrated-energy-system-protection-model
Based on the established electric gas thermal coupling integrated energy system as an example, the probability of node / line being attacked, the probability of node / line being successfully attacked and the cost parameters are shown below.
## 节点/线路被攻击的概率
&ensp;&ensp;&ensp;&ensp;本文认为，节点/线路会受到自然灾害攻击和人为攻击两种攻击方式，其中自然灾害攻击发生概率低，但是所有节点/线路都有可能发生，而人为攻击发生的概率相对较高，且集中于较为重要的节点/线路。即带权重的介数较高的节点/线路更易遭受人为攻击。因此，本模型所设置的节点被攻击的概率如下式所示:  
$$\{P_{attack,i}} = 0.01 + \frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}$$
式中，0.01表示自然灾害攻击节点的概率；$\frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$表示人为攻击节点的概率，节点的带权重节点介数越高被攻击的概率就越高。  
&ensp;&ensp;&ensp;&ensp;线路被攻击的概率如下式所示:
$$\{P_{attack,j}} = 0.1 + \frac{{linebetweennes{s_j} \times lineindex}}{{10}}\$$
式中，0.1表示自然灾害攻击线路的概率，线路比节点更易遭受自然灾害的攻击；$\frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$表示人为攻击线路的概率，线路的带权重节点介数越高被攻击的概率就越高。  
## 节点/线路被成功攻击的概率
&ensp;&ensp;&ensp;&ensp;本文认为，节点/线路被成功攻击的概率与其带权重介数有关。节点/线路的带权重介数越大，说明其越重要，防护就越完善，被成功攻击的概率就越低。同时，节点比线路被成功攻击的概率要低。因此，本模型所设置的节点被成功攻击的概率如下式所示：
$$\{P_{attacksuccess,i}} = 0.5 - \frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$$
&ensp;&ensp;&ensp;&ensp;线路被成功攻击的概率如下式所示：
$$\{P_{attacksuccess,j}} = 0.6 - \frac{{linbetweennes{s_j} \times lineindex}}{{10}}\$$
## 加边成本参数
&ensp;&ensp;&ensp;&ensp;本模型设置的电网、气网、热网的加边成本参数如表1所示。其中，电网加边是加输电线路，气网加边是加天然气管道，热网加边是加供回水管道（加一条热网边即同时加供水管道和回水管道）。  
#### 表1:加边成本参数
子网类型  | 电网（万元/条）|天然气网（万元/条）|热网（万元/条）
:-------------: |:-------------:|:-------------:|:-------------:
加边成本参数  | 1500|2000|4000
## 物理防护成本参数
&ensp;&ensp;&ensp;&ensp;本模型设置的节点、线路物理防护成本系数如表2所示。
#### 表2:物理防护成本系数
物理防护类型  | 节点（万元）|线路（万元）
:-------------: |:-------------:|:-------------:
物理防护成本参数  | 2000|1600
## 备用站/备用线路成本参数
&ensp;&ensp;&ensp;&ensp;本文认为，节点的带权重介数越高，说明节点越关键，建立该节点的备用站的成本就越高；线路的带权重介数越高，说明线路越关键，建立该线路的备用线路的成本就越高。因此，本章设置的加备用站成本如下式所示：
$$costcoefficientbus = {\rm{COSTCOEFFICIENTBUS}} \times (0.1 + \frac{{nodebetweennes{s_i}}}{{\sum\limits_{0 < i \le nodeindex} {nodebetweennes{s_i}} }})\$$
式中， $\{\rm{COSTCOEFFICIENTBUS}}\$表示加备用站的成本系数；0.1表示建立备用站的固定成本系数；$\frac{{nodebetweennes{s_i}}}{{\sum\limits_{0 < i \le nodeindex} {nodebetweennes{s_i}} }}\$表示节点带权重介数的占比。
&ensp;&ensp;&ensp;&ensp;本模型设置的加备用站、备用线路成本系数如表3所示。
#### 表3:备用站/备用线路成本系数
保护类型  | 加备用站（万元）|加备用线路（万元）
:-------------: |:-------------:|:-------------:
成本参数  |24000|18000
## 其他参数
&ensp;&ensp;&ensp;&ensp;本模型算例中所使用的其他参数，具体为加边数量与变量处理等约束如表4所示。
#### 表4:其他参数数值
 参数 | $\alpha $|$\beta $|$\gamma $
:-------------: |:-------------:|:-------------:|:-------------:
数值  |0.15%|0.15%|0.15%

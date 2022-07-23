# Basic-data-of-integrated-energy-system-protection-model
Based on the established electric gas thermal coupling integrated energy system as an example, the probability of node / line being attacked, the probability of node / line being successfully attacked and the cost parameters are shown below.
## 节点/线路被攻击的概率
    本文认为，节点/线路会受到自然灾害攻击和人为攻击两种攻击方式，其中自然灾害攻击发生概率低，但是所有节点/线路都有可能发生，而人为攻击发生的概率相对较高，且集中于较为重要的节点/线路，即带权重的介数较高的节点/线路更易遭受人为攻击。因此，本模型所设置的节点被攻击的概率如下式所示。  
$\{P_{attack,i}} = 0.01 + \frac{{nodebetweennes{s_i} \times nodeindex}}{{10}}\$

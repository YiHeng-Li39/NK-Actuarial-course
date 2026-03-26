# 精算概论学习资料

欢迎来到本课程的专属资料库！这里将系统存放课程讲义、核心公式推导与模型代码。

## 1. 核心精算符号与公式渲染测试

以下是几个精算学中基础的现值与概率计算公式。

### 纯生存期末禀赋 (Pure Endowment)

对于一个年龄为 \(x\) 岁的人，如果他在 \(n\) 年后依然存活，将获得 1 单位的生存金。其精算现值表示为：

\[
{}_{n}E_x = v^n \cdot {}_{n}p_x = \frac{D_{x+n}}{D_x}
\]

### 终身寿险趸交纯保费 (Net Single Premium)

假设死亡保险金于死亡所在保单年度末给付，对于 \(x\) 岁的人，保额为 1 的终身寿险趸交纯保费为：

\[
A_x = \sum_{k=0}^{\infty} v^{k+1} \cdot {}_{k|}q_x = \frac{M_x}{D_x}
\]

## 2. 代码高亮测试

除了公式，我们还可以直接在这里展示精算建模（例如 GLM 或基础保费测算）的代码：

```python
def calc_pure_endowment(interest_rate, n, p_x):
    """
    计算纯生存期末禀赋
    :param interest_rate: 预定利率 (如 0.035)
    :param n: 期限
    :param p_x: n年生存概率
    """
    v = 1 / (1 + interest_rate)
    return (v ** n) * p_x
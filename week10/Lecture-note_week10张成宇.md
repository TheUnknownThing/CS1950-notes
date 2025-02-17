# Lecture Note for week 10
## Def: Algorithm

可以通过循环以及条件判断，在规定一系列行为之后交给计算机解决的方法  
特点：可复用，特定问题特定算法  

## 类基数排序
使用在 IBM 083 卡片排序机  

特点：在机械装置上实现  

方案：由低位向高位进行，每一次按照当前位归类，保证每一个桶内相对原有顺序不变。
```
Example:  
  108, 708, 001, 269, 015, 096
-----------------------------------
First sort:
  [001] [015] [096] [108 708] [269]
-----------------------------------
Second sort:
  [001 108 708] [015] [269] [096]
-----------------------------------
Third sort:
  [001 015 096] [108] [268] [708]
```
可以理解为 每一次排序让有序的集合递归变大  

优点：
 - 复杂度和单个数字长度相关，适合处理大规模小数据
 - 每次只进行一位数的大小比较，符合机械结构功能特性

对比其他排序算法，可以归为两类：
 - 类似该排序算法，逐渐扩大有序范围
 - 选取 pivot，优先维护相对大小

## Page Rank
信息检索算法，由Google创始人 Larry Page 发明。  

核心原理在于如何定义网页的**重要程度**

在 Page Rank 中， 一个网页的重要程度由指向它的网页数以及指向其网页的重要程度来决定，具体而言，使用如下公式：

$R(i)=\sum_{k=1}^{N}R(k)\frac{1}{d(k)}$

其中 $d(k)$ 是 k 节点的出度  

可以将其转化为矩阵运算，利用高斯消元等方法求出R值  

但在实际应用中，矩阵很可能达到难以计算的规模

有多种方案来进行优化，如：
- 并不实时更新矩阵的值，优先更新原先计算结果中$R(i)$较大的节点，因为更新它会对相关节点产生较大的影响




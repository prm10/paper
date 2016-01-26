Auvolat A, Vincent P. Clustering is efficient for approximate maximum inner product search[J]. arXiv preprint arXiv:1507.05910, 2015.
# 摘要
　　针对Maximum Inner Product Search问题，通常有locality-sensitive hashing (LSH) 和 tree-based solutions两种近似解法。本文将这些方法与其他简单的近似解法做对比，基于kmeans算法的变种。特别是，在将MIPS问题转化为MCSS后，我们训练了一种球形kmeans算法。在两个标准推荐系统和一些大型词嵌入上的实验证明了该方法在保证结果不变的情况下取得了明显提速。该方法也对噪声更鲁棒。
# 简介

　　这里列举两类会遇到MIPS的问题：一是推荐系统中给定user向量，找出与之点积最大的向量对应的商品；二是海量类别的分类任务如预测下一个单词时，需要用softmax。

　　对于这类问题，如果在尽可能保证精度的情况下使得搜索复杂度远低于线性的，则会极大提高其在大规模数据上的应用价值。
　　本文讨论的所有方法都是基于候选集，即通过这些方法产生一个全集的子集，再在该子集上求精确的k-MIPS，这样就会很快。而方法的优劣主要体现在该子集的大小更小、同时又与真实结果的交集更大。

　　MIPS与最近邻搜索以及最大相似度搜索很相关。

# 相关工作
　　主要有两类，一类是基于树的，依赖于数据，一类是hash，不依赖数据。
　　

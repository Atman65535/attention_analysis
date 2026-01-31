阶段一 · Attention 解剖路线（研究者向，不是入门）

目标一句话：
从“Attention 是模块” → “Attention 是一类可变结构算子”

总体分三层（你按层推进）
Layer A：Attention 的数学本体（你动刀的地方）
Layer B：Attention 的结构变体与等价性
Layer C：Attention 在视觉 / 扩散中的功能分化

你不是要全读完，你是要沿着一条主线把它们连起来。

🔹 Layer A：Attention 是什么（不是 Transformer 是什么）
1️⃣ Attention Is All You Need

Vaswani et al., 2017

你要干什么（重点）：

不要管 encoder-decoder

不要管多头的工程意义

你只干三件事：

把 QKᵀV 写成一个信息路由算子

想清楚：softmax 到底是在约束什么

问一个问题：

如果我把 softmax 换成别的东西，attention 还剩什么？

👉 输出物：
一页笔记：

Attention = 相似度核 + 归一化 + 值传播

2️⃣ On the Mathematical Properties of Attention（或等价工作）

如：

"The Expressive Power of Attention"

"Transformers as Soft Reasoners"

你要干什么：

看 attention 是否是线性/非线性

看它能不能表示 permutation equivariance

看它是不是“万能”

👉 你真正要抓住的点：

Attention 不是通用算子，它在结构表达上是“软的”

🔹 Layer B：Attention 的等价形式（这是你吃透的关键）
3️⃣ Rethinking Attention with Performers / Linear Attention

Choromanski et al., Performer

你要干什么：

看 kernel trick 怎么把 softmax attention 变成近似线性

问一个问题：

attention 到底是“内容驱动”，还是“核驱动”？

👉 重要认知跃迁：

Attention ≈ kernelized message passing
softmax 只是一个选择，不是本质

4️⃣ Transformers are RNNs / Attention as Message Passing

如：

"Transformers are Graph Neural Networks"

"On the Equivalence of Self-Attention and Convolution"

你要干什么：

把 attention 看成：

图上的加权信息传播

或一种动态卷积

👉 输出物：

一张你自己画的图：
Attention ≈ 动态邻接矩阵 + 值聚合

这是你**以后“控制 attention”**的理论支点。

🔹 Layer C：Attention 在视觉 / 扩散中“到底在干嘛”

（你已经在这层了，但现在要反过来补地基）

5️⃣ An Image is Worth 16x16 Words (ViT)

你要干什么：

不看分类结果

看 attention map 的空间行为

问三个问题：

self-attn 在视觉中是不是在“找物体”？

它有没有稳定几何含义？

patch 粒度变化会发生什么？

6️⃣ Prompt-to-Prompt / Cross-Attention Control（你已经看过）

这次你换一个视角：

不看“能不能改图”

看：

cross-attn 在 diffusion 中承担的是“绑定”还是“调制”？

你会发现：
👉 很多工作只是经验操控，没有理论结构。

🔹 你真正的“主线问题”（写在笔记首页）

你整个阶段一，只围绕这三个问题读：

Q1：Attention 是不是一种结构化算子？还是只是 soft weighting？
Q2：Attention 能不能表达“硬约束”？如果不能，为什么？
Q3：Attention 在 diffusion 中，是主因还是调制器？

这三个问题，以后能自然引出“超越 Transformer”。

🔥 给你一个【7 天启动计划】（很现实）
Day 1–2

重读 Attention is All You Need（只看 attention）

手写 QKᵀV 的 3 种解释

Day 3

读 Performer

自问：softmax 是不是偶然选择？

Day 4

找一篇 attention = message passing 的文章

画图（非常重要）

Day 5

回到 Stable Diffusion

标出：

哪几层是“语义绑定”

哪几层只是噪声调制

Day 6–7

写一篇不发表的 mini note：

“Attention is a soft structural prior, not a reasoning engine”

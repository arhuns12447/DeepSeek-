# DeepSeek-
DeepSeek满血版3分钟轻松搞定节目串词主持稿！
TurboDiffusion之所以能跑得这么快，靠的是以下四大黑科技加持：

1. SageAttention：低比特量化注意力加速

传统Transformer注意力层在高分辨率视频场景中，计算开销巨大。TurboDiffusion采用清华自主研发的SageAttention技术，进行了低比特量化注意力加速，充分压榨了显卡性能，极致提速。

GitHub链接：https://github.com/thu-ml/SageAttention

2. Sparse-Linear Attention（SLA）：稀疏注意力加速

在稀疏计算方面，TurboDiffusion引入了SLA（Sparse-Linear Attention）。

由于稀疏计算与低比特Tensor Core加速是正交的，SLA可以构建在SageAttention之上，显著减少了全连接矩阵乘法的冗余计算，在推理过程中进一步获得数倍的额外加速。

GitHub链接：https://github.com/thu-ml/SLA

3. rCM步数蒸馏加速：更少步生成

来自NVIDIA开源实验室的rCM，是一种先进的步数蒸馏方法。它通过训练，让少量的采样步骤也能恢复与原模型一致的质量。

这种方法能进行步数蒸馏加速，减少推理过程中的「扩散步数」，降低延迟而不损失画质。

比如，原始Diffusion需要50–100步，rCM可压缩到4-8步。

GitHub链接：https://github.com/NVlabs/rcm

4. W8A8 INT8量化：线性层加速

TurboDiffusion在线性层采用了W8A8的INT8量化策略，这样，就将模型权重和激活映射到8位整数空间，并在128×128的块粒度上进行分块量化，兼顾了速度与精度，而且还显著降低了推理功耗与内存占用。

这4项核心技术均由清华大学TSAIL团队联合生数科技自主研发，对AI多模态大模型的技术突破与产业落地具有里程碑式的价值与深远影响力。其中，SageAttention更是全球首个实现注意力计算量化加速的技术方案，已被工业界大规模部署应用。

例如，SageAttention已成功集成至NVIDIA推理引擎Tensor RT，同时完成在华为昇腾、摩尔线程S6000等主流GPU平台的部署与落地。此外，腾讯混元、字节豆包、阿里Tora、生数Vidu、智谱清影、百度飞桨、昆仑万维、Google Veo3、商汤、vLLM等国内外头部科技企业及团队，均已在核心产品中应用该技术，凭借其卓越性能创造了可观的经济效益https://weibo.com/ttarticle/p/show?id=2309405246777242026716
https://weibo.com/ttarticle/p/show?id=2309405246781993910329
https://weibo.com/ttarticle/p/show?id=2309405247020041633838
https://weibo.com/ttarticle/p/show?id=2309405247021622886421
https://weibo.com/ttarticle/p/show?id=2309405247023145419002
https://weibo.com/ttarticle/p/show?id=2309405247025045700847
https://weibo.com/ttarticle/p/show?id=2309405247026798919860
https://weibo.com/ttarticle/p/show?id=2309405247028509933627
https://weibo.com/ttarticle/p/show?id=2309405247032930730102
https://weibo.com/ttarticle/p/show?id=2309405247034293878948

<p align="center"><img src="https://raw.githubusercontent.com/ikun-llm/.github/main/profile/logo.png" width="120" /></p>
<h2 align="center">ikun-GRPO</h2>
<p align="center"><b>强化学习练习生</b><br/><sub>Level 2 | 对齐篇</sub></p>

---

> GRPO = Group Relative "Practice" Optimization，组内相对练习优化。

## 你将学到

- PPO vs GRPO：为什么 DeepSeek 用 GRPO？
- 在线生成 + 奖励模型打分
- 组内相对基线（不需要 Critic 模型！）
- 奖励函数设计：格式奖励 + 语义奖励
- MiniMind 原生 GRPO 实现（非 trl 封装）

## 核心代码

基于 [MiniMind](https://github.com/jingyaogong/minimind) 的 `trainer/train_grpo.py`

```bash
cd trainer && python train_grpo.py \
    --from_weight full_sft --hidden_size 512
```

## PPO vs GRPO

```
PPO:  需要 Actor + Critic + Reference + Reward = 4 个模型
GRPO: 只需要 Actor + Reference + Reward = 3 个模型

PPO:  用 Critic 估计 baseline
GRPO: 用组内平均奖励作为 baseline → 更简单、更稳定
```

## 系列导航

| Level | Repo | 学什么 |
|-------|------|--------|
| 1 | [ikun-tokenizer](https://github.com/ikun-llm/ikun-tokenizer) | 分词器原理 |
| 1 | [ikun-pretrain](https://github.com/ikun-llm/ikun-pretrain) | 从零预训练 |
| 1 | [ikun-2.5B](https://github.com/ikun-llm/ikun-2.5B) | SFT + LoRA 微调 |
| 2 | [ikun-DPO](https://github.com/ikun-llm/ikun-DPO) | 偏好对齐 |
| **2** | **ikun-GRPO** <-- 你在这里 | 强化学习 |
| 2 | [ikun-Reason](https://github.com/ikun-llm/ikun-Reason) | 推理模型 |
| 3 | [ikun-MoE](https://github.com/ikun-llm/ikun-MoE) | 混合专家 |
| 3 | [ikun-Distill](https://github.com/ikun-llm/ikun-Distill) | 知识蒸馏 |
| 3 | [ikun-V](https://github.com/ikun-llm/ikun-V) | 多模态 |
| 4 | [ikun-deploy](https://github.com/ikun-llm/ikun-deploy) | 部署 |

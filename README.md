# ⚙ LeyoAI Flow Automation Assistant (Small)

> LeyoAI 流程自动化助手（小型版）

---

## 🇬🇧 English

### Overview

**LeyoAI Flow Automation Assistant (Small)** — Part of the [LeyoAI](https://leyoai.vercel.app) platform by 杭州市上城区乐友信息服务工作室.

Flow Automation Assistant — Automates workflows, extracts process entities, manages task pipelines.

### Model Details

| Item | Value |
|------|-------|
| Base Model | `Qwen/Qwen2.5-1.5B-Instruct` |
| PEFT Type | LoRA |
| LoRA Rank | 16 |
| LoRA Alpha | 32 |
| LoRA Dropout | 0.1 |
| Target Modules | ['q_proj', 'k_proj', 'v_proj', 'o_proj'] |
| Task Type | CAUSAL_LM |
| Training Device | Apple Mac Studio (MPS) |
| Precision | FP32 |

### Quick Start

```python
from peft import PeftModel
from transformers import AutoModelForCausalLM, AutoTokenizer

base = AutoModelForCausalLM.from_pretrained("Qwen/Qwen2.5-1.5B-Instruct")
tok = AutoTokenizer.from_pretrained("Qwen/Qwen2.5-1.5B-Instruct")
model = PeftModel.from_pretrained(base, "richard3153/leyoai-flow-small")
model.eval()

msgs = [{"role": "user", "content": "Your question"}]
inputs = tok.apply_chat_template(msgs, return_tensors="pt")
out = model.generate(inputs, max_new_tokens=256)
print(tok.decode(out[0]))
```

### HuggingFace

Also available: [FFZwai/leyoai-flow-small](https://huggingface.co/FFZwai/leyoai-flow-small)

---

## 🇨🇳 中文

### 概述

**LeyoAI 流程自动化助手（小型版）** — [杭州市上城区乐友信息服务工作室](https://leyoai.vercel.app)旗下 [LeyoAI](https://leyoai.vercel.app) 平台。

流程自动化助手 — 自动化工作流、提取流程实体、管理任务管线。

### 模型详情

| 项目 | 值 |
|------|-----|
| 基座模型 | `Qwen/Qwen2.5-1.5B-Instruct` |
| 微调方式 | LoRA |
| LoRA 秩 | 16 |
| LoRA Alpha | 32 |
| 目标模块 | ['q_proj', 'k_proj', 'v_proj', 'o_proj'] |
| 训练设备 | Apple Mac Studio (MPS) |
| 精度 | FP32 |

### 快速使用

```python
from peft import PeftModel
from transformers import AutoModelForCausalLM, AutoTokenizer

base = AutoModelForCausalLM.from_pretrained("Qwen/Qwen2.5-1.5B-Instruct")
tok = AutoTokenizer.from_pretrained("Qwen/Qwen2.5-1.5B-Instruct")
model = PeftModel.from_pretrained(base, "richard3153/leyoai-flow-small")
model.eval()

msgs = [{"role": "user", "content": "你的问题"}]
inputs = tok.apply_chat_template(msgs, return_tensors="pt")
out = model.generate(inputs, max_new_tokens=256)
print(tok.decode(out[0]))
```

### HuggingFace

也可在 HuggingFace 获取：[FFZwai/leyoai-flow-small](https://huggingface.co/FFZwai/leyoai-flow-small)

---

## License

MIT License — 杭州市上城区乐友信息服务工作室

## Links

- 🌐 [LeyoAI](https://leyoai.vercel.app) | 🤗 [HuggingFace](https://huggingface.co/FFZwai) | 💻 [GitHub](https://github.com/richard3153)

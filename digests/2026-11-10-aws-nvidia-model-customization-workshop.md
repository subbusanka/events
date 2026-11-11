# AWS × NVIDIA Model Customization Workshop
**Date:** 2026-11-10
**Venue/Organizer:** AWS Builder Loft, San Francisco

## Opportunities
- Fine-tuning open models (Nemotron Nano/Super) via SageMaker can cost under $100 — cited for both Hugging Face sample data and AWS's own path.
- NVIDIA GitHub hosts several ready-made fine-tuning recipes.
- NVIDIA offers GPU-accelerated data processing for Spark workloads.
- Nemotron has serverless hosting options.
- Open models were presented as lower cost and lower latency than frontier/closed models, especially for vertical-industry use cases.
- Hugging Face has a large base to draw from: 350 open datasets, 1,000+ open models.

## Open Questions
- Ganesh Hegde — is fine-tuning additive (can it be layered incrementally on top of a prior fine-tune)?
- Deepak Rupakula — what's the approach to beta testing a customized model?
- A speaker claimed fine-tuning can be "37x cheaper" — unclear what the actual training cost and dataset effectiveness behind that number were.

## Exploration Points
- Thought: instead of running several separate agents, a single mixture-of-experts (MoE) model might consolidate that work.
- Model customization is broader than fine-tuning: fine-tuning (updating weights on labeled data) is one method among several — prompt engineering, RAG, adapters/LoRA, distillation, and pretraining on domain data are others.
- Foundation models are pretrained, general-purpose "off-the-shelf" base models (e.g., GPT, Claude, Llama, Nemotron) meant to be adapted via customization rather than built from scratch per task.
- SFT (supervised fine-tuning) = training on labeled input/output example pairs. SFT-RL adds a reinforcement-learning stage after SFT (e.g., RLHF-style).
- "Open" was called out as not just meaning downloadable weights — a broader bar than expected.
- System-of-models and model-routing libraries came up as an architecture pattern for coordinating multiple models.
- Live audience poll ("pick a number 25–35") converged heavily on 31 — used as a demonstration that LLMs cluster on non-random answers rather than sampling uniformly.
- The Union.ai talk was well received: https://www.union.ai/

## Worthy Notes for Antara
- Sub-$100 fine-tuning cost claims (Hugging Face + AWS/SageMaker) are directly relevant to cost modeling for the Data Engineering Box agent.
- NVIDIA's GPU-accelerated Spark processing overlaps with Data Engineering Box's generated Spark code — worth checking for cost or speed gains.
- The MoE-as-single-model thought is a real architectural alternative to the current agents-plus-harness design for Data Engineering Box.
- Model routing libraries / system-of-models is relevant infrastructure if a multi-model approach is kept instead of MoE.

## Sessions
- NVIDIA: Nemotron — Curtice Lockhart
- Nemotron 3.5 30B Lightning walkthrough — Chakra Nagarajan

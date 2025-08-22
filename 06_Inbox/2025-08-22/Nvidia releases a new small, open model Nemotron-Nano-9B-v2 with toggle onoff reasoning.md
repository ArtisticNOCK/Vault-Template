---
title: "Nvidia releases a new small, open model Nemotron-Nano-9B-v2 with toggle on/off reasoning"
source: "https://venturebeat.com/ai/nvidia-releases-a-new-small-open-model-nemotron-nano-9b-v2-with-toggle-on-off-reasoning/"
author:
  - "[[Carl Franzen]]"
published: 2025-08-19
created: 2025-08-22
description: "Developers are free to create and distribute derivative models. Importantly, Nvidia does not claim ownership of any outputs generated..."
tags:
  - "clippings"
---
[Skip to main content](https://venturebeat.com/ai/nvidia-releases-a-new-small-open-model-nemotron-nano-9b-v2-with-toggle-on-off-reasoning/#primary)

*Want smarter insights in your inbox? Sign up for our weekly newsletters to get only what matters to enterprise AI, data, and security leaders.**[Subscribe Now](https://venturebeat.com/newsletters/)*

---

Small models are having a moment. On the heels of the release of a new AI vision model [small enough to fit on a smartwatch](https://x.com/maximelabonne/status/1957377692401021382) from [MIT spinoff Liquid AI](https://venturebeat.com/ai/liquid-ai-wants-to-give-smartphones-small-fast-ai-that-can-see-with-new-lfm2-vl-model/), and a model small [enough to run on a smartphone from Google](https://venturebeat.com/ai/google-unveils-ultra-small-and-efficient-open-source-ai-model-gemma-3-270m-that-can-run-on-smartphones/), **Nvidia is joining the party today** with [a new small language model (SLM)](https://huggingface.co/collections/nvidia/nvidia-nemotron-689f6d6e6ead8e77dd641615) of its own, **Nemotron-Nano-9B-V2**, which attained the highest performance in its class on selected benchmarks and comes with the ability for users to toggle on and off AI “reasoning,” that is, self-checking before outputting an answer.

While the 9 billion parameters are larger than some of the multimillion parameter small models VentureBeat has covered recently**, Nvidia notes it is a meaningful reduction from its original size of 12 billion parameters** and is designed to fit on a **single Nvidia A10 GPU**.

As Oleksii Kuchiaev, Nvidia Director of AI Model Post-Training, [said on X](https://x.com/kuchaev/status/1957513859876712554) in response to a question I submitted to him: “The 12B was pruned to 9B to specifically fit A10 which is a popular GPU choice for deployment. **It is also a hybrid model which allows it to process a larger batch size and be up to 6x faster than similar sized transformer models.”**

For context, many leading LLMs are in the 70+ billion parameter range (recall parameters refer to the internal settings governing the model’s behavior, with more generally denoting a larger and more capable, yet more compute intensive model).

The model handles multiple languages, including English, German, Spanish, French, Italian, Japanese, and in extended descriptions, Korean, Portuguese, Russian, and Chinese. It’s suitable for both **instruction following and code generation.**

[Nemotron-Nano-9B-V2](https://huggingface.co/nvidia/NVIDIA-Nemotron-Nano-9B-v2) and its [pre-training datasets](https://huggingface.co/collections/nvidia/nemotron-pre-training-dataset-689d9de36f84279d83786b35) available right now on Hugging Face and through the company’s model catalog.

## A fusion of Transformer and Mamba architectures

It’s based on [Nemotron-H](https://arxiv.org/abs/2504.03624), a set of hybrid Mamba-Transformer models that form the foundation for the company’s latest offerings.

While most popular LLMs are pure “Transformer” models, which rely entirely on attention layers, they can become costly in memory and compute as sequence lengths grow.

Instead, Nemotron-H models and others using the [Mamba architecture developed by researchers](https://arxiv.org/pdf/2312.00752) at Carnegie Mellon University and Princeton, also **weave in selective state space models (or SSMs), which can handle very long sequences of information in and out by maintaining state.**

These layers scale linearly with sequence length and can process contexts much longer than standard self-attention without the same memory and compute overhead.

A h **ybrid Mamba-Transformer reduces those costs by substituting most of the attention with linear-time state space layers, achieving up to 2–3× higher throughput on long contexts** with comparable accuracy.

Other AI labs beyond Nvidia such [as AI21\* have also released models](https://venturebeat.com/ai/ai21-labs-juices-up-gen-ai-transformers-with-jamba/) based on the Mamba architecture.

## Toggle on/of reasoning using language

Nemotron-Nano-9B-v2 is positioned as a unified, text-only chat and reasoning model trained from scratch.

The **system defaults to generating a reasoning trace before providing a final answer, though users can toggle this behavior** through simple control tokens such as /think or /no\_think.

The model also i **ntroduces runtime “thinking budget” management**, which **allows developers to cap the number of tokens** devoted to internal reasoning before the model completes a response.

This mechanism is aimed at balancing accuracy with latency, **particularly in applications like customer support or autonomous agents.**

## Benchmarks tell a promising story

Evaluation results highlight competitive accuracy against other open small-scale models. Tested in “reasoning on” mode using the NeMo-Skills suite, **Nemotron-Nano-9B-v2 reaches 72.1 percent on AIME25**, **97.8 percent on MATH500, 64.0 percent on GPQA**, and **71.1 percent on LiveCodeBench**.

Scores on instruction following and long-context benchmarks are also reported: **90.3 percent on IFEval, 78.9 percent on the RULER 128K test**, and smaller but measurable gains on BFCL v3 and the HLE benchmark.

![](https://venturebeat.com/wp-content/uploads/2025/08/accuracy_chart.png)

**Across the board, Nano-9B-v2 shows higher accuracy than Qwen3-8B,** a common point of comparison.

![](https://venturebeat.com/wp-content/uploads/2025/08/acc-vs-budget.png)

Nvidia illustrates these results with accuracy-versus-budget curves that show how performance scales as the token allowance for reasoning increases. The company suggests that careful budget control can help developers optimize both quality and latency in production use cases.

## Trained on synthetic datasets

Both the Nano model and the Nemotron-H family rely on a mixture of curated, web-sourced, and synthetic training data.

The corpora include general text, code, mathematics, science, legal, and financial documents, as well as alignment-style question-answering datasets.

Nvidia confirms the use of synthetic reasoning traces generated by other large models to strengthen performance on complex benchmarks.

## Licensing and commercial use

The Nano-9B-v2 model is released under the [Nvidia Open Model License Agreement](https://www.nvidia.com/en-us/agreements/enterprise-software/nvidia-open-model-license/), last updated in June 2025.

The license is designed to be permissive and enterprise-friendly. **Nvidia explicitly states that the models are *commercially usable* out of the box**, and that **developers are free to create and distribute derivative models.**

Importantly, Nvidia does not claim ownership of any outputs generated by the model, leaving responsibility and rights with the developer or organization using it.

For an enterprise developer, this means the model can be put into production immediately without negotiating a separate commercial license or paying fees tied to usage thresholds, revenue levels, or user counts. There are no clauses requiring a paid license once a company reaches a certain scale, unlike some tiered open licenses used by other providers.

That said, the agreement does include several conditions enterprises must observe:

- **Guardrails**: Users cannot bypass or disable built-in safety mechanisms (referred to as “guardrails”) without implementing comparable replacements suited to their deployment.
- **Redistribution**: Any redistribution of the model or derivatives must include the Nvidia Open Model License text and attribution (“Licensed by Nvidia Corporation under the Nvidia Open Model License”).
- **Compliance**: Users must comply with trade regulations and restrictions (e.g., U.S. export laws).
- **Trustworthy AI terms**: Usage must align with Nvidia Trustworthy AI guidelines, which cover responsible deployment and ethical considerations.
- **Litigation clause**: If a user initiates copyright or patent litigation against another entity alleging infringement by the model, the license automatically terminates.

These conditions focus on legal and responsible use rather than commercial scale. Enterprises do not need to seek additional permission or pay royalties to Nvidia simply for building products, monetizing them, or scaling their user base. Instead, they must make sure deployment practices respect safety, attribution, and compliance obligations.

## Positioning in the market

With Nemotron-Nano-9B-v2, Nvidia is targeting developers who need a balance of reasoning capability and deployment efficiency at smaller scales.

The runtime budget control and reasoning-toggle features are meant to give system builders more flexibility in managing accuracy versus response speed.

Their release on Hugging Face and Nvidia’s model catalog indicates that they are **meant to be broadly accessible for experimentation and integration.**

Nvidia’s release of Nemotron-Nano-9B-v2 showcase a continued focus on efficiency and controllable reasoning in language models.

**By combining hybrid architectures with new compression and training techniques**, the company is offering developers tools that seek to maintain accuracy while reducing costs and latency.

*\*Editor’s note: corrected on August 20, 2025 after mistakenly printing the wrong company name, Ai2 instead of AI21.*

**Daily insights on business use cases with VB Daily**

If you want to impress your boss, VB Daily has you covered. We give you the inside scoop on what companies are doing with generative AI, from regulatory shifts to practical deployments, so you can share insights for maximum ROI.

Read our [Privacy Policy](https://venturebeat.com/terms-of-service/)

Thanks for subscribing. Check out more [VB newsletters here](https://venturebeat.com/newsletters/).

An error occured.

![](https://venturebeat.com/wp-content/themes/vb-news/brand/img/vb-daily-phone.png)
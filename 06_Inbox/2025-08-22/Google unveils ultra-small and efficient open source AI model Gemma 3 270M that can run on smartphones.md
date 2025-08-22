---
title: "Google unveils ultra-small and efficient open source AI model Gemma 3 270M that can run on smartphones"
source: "https://venturebeat.com/ai/google-unveils-ultra-small-and-efficient-open-source-ai-model-gemma-3-270m-that-can-run-on-smartphones/"
author:
  - "[[Carl Franzen]]"
published: 2025-08-15
created: 2025-08-21
description: "For enterprise teams and commercial developers, this means the model can be embedded in products or fine-tuned."
tags:
  - "clippings"
---
*Want smarter insights in your inbox? Sign up for our weekly newsletters to get only what matters to enterprise AI, data, and security leaders.**[Subscribe Now](https://venturebeat.com/newsletters/)*

---

**Google’s DeepMind AI research team** has [unveiled a new open source AI model today,](https://developers.googleblog.com/en/introducing-gemma-3-270m/) **Gemma 3 270M.**

As its name would suggest, this is a **270-million-parameter model** — far smaller than the 70 billion or more parameters of many frontier LLMs (parameters being the number of internal settings governing the model’s behavior).

While more parameters generally translates to a larger and more powerful model, Google’s focus with this is nearly the opposite: high-efficiency, giving developers a model **small enough to run directly on smartphones** and **locally**, **without an internet connection**, as shown in internal tests on a Pixel 9 Pro SoC.

Yet, the model is still capable of handling complex, domain-specific tasks and can be quickly fine-tuned in mere minutes to fit an enterprise or indie developer’s needs.

On the [social network X](https://x.com/osanseviero/status/1956032217257287688), Google DeepMind Staff AI Developer Relations Engineer Omar Sanseviero added that it Gemma 3 270M can also **run directly in a user’s web browser, on a Raspberry Pi**, and “in your toaster,” underscoring its ability to operate on very lightweight hardware.

Gemma 3 270M combines 170 million embedding parameters — thanks to a large 256k vocabulary capable of handling rare and specific tokens — with 100 million transformer block parameters.

According to Google, the architecture supports strong performance on instruction-following tasks right out of the box while staying small enough for rapid fine-tuning and deployment on devices with limited resources, including mobile hardware.

Gemma 3 270M inherits the architecture and pretraining of the larger Gemma 3 models, ensuring compatibility across the Gemma ecosystem. With documentation, fine-tuning recipes, and deployment guides available for tools like Hugging Face, UnSloth, and JAX, developers can move from experimentation to deployment quickly.

## High scores on benchmarks for its size, and high hefficiency

  
On the **IFEval benchmark, which measures a model’s ability to follow instructions**, the instruction-tuned Gemma 3 270M scored **51.2%**.

The score places it **well above similarly small models like SmolLM2 135M Instruct and Qwen 2.5 0.5B Instruct**, and closer to the performance range of some billion-parameter models, according to Google’s published comparison.

However, as [researchers](https://x.com/maximelabonne/status/1956033482871734689) and [leaders](https://x.com/ramin_m_h/status/1956030558275833879) at rival AI startup [Liquid AI](https://venturebeat.com/ai/liquid-ai-wants-to-give-smartphones-small-fast-ai-that-can-see-with-new-lfm2-vl-model/) pointed out in replies on X, Google left off Liquid’s own [LFM2-350M model released back](https://www.liquid.ai/blog/liquid-foundation-models-v2-our-second-series-of-generative-ai-models) in July of this year, which scored a whopping **65.12%** with just a few more parameters (similar sized language model, however).

One of the model’s defining strengths is its energy efficiency. In internal tests using the INT4-quantized model on a Pixel 9 Pro SoC, **25 conversations consumed just 0.75% of the device’s battery.**

This makes Gemma 3 270M a practical choice for on-device AI, particularly in cases where privacy and offline functionality are important.

The release includes both a pretrained and an instruction-tuned model, giving developers immediate utility for general instruction-following tasks.

Quantization-Aware Trained (QAT) checkpoints are also available, enabling INT4 precision with minimal performance loss and making the model production-ready for resource-constrained environments.

## A small, fine-tuned version of Gemma 3 270M can perform many functions of larger LLMs

Google frames Gemma 3 270M as part of a broader philosophy of choosing the right tool for the job rather than relying on raw model size.

For functions like sentiment analysis, entity extraction, query routing, structured text generation, compliance checks, and creative writing, the company says a fine-tuned small model can deliver faster, more cost-effective results than a large general-purpose one.

The benefits of specialization are evident in past work, such as Adaptive ML’s collaboration with SK Telecom.

By fine-tuning a Gemma 3 4B model for multilingual content moderation, the team outperformed much larger proprietary systems.

**Gemma 3 270M is designed to enable similar success at an even smaller scale,** supporting fleets of specialized models tailored to individual tasks.

## Demo Bedtime Story Generator app shows off the potential of Gemma 3 270M

Beyond enterprise use, the model also fits creative scenarios. In a [demo video posted on YouTube](https://youtu.be/ds95v-Aiu5E?si=EkfuUG80MzaoIIyD), Google shows off a Bedtime Story Generator app built with Gemma 3 270M and Transformers.js that **runs entirely offline in a web browser,** showing the versatility of the model in lightweight, accessible applications.

![](https://www.youtube.com/watch?v=ds95v-Aiu5E)

The video highlights the model’s ability to synthesize multiple inputs by allowing selections for a main character (e.g., “a magical cat”), a setting (“in an enchanted forest”), a plot twist (“uncovers a secret door”), a theme (“Adventurous”), and a desired length (“Short”).

Once the parameters are set, the Gemma 3 270M model generates a coherent and imaginative story. The application proceeds to weave a short, adventurous tale based on the user’s choices, demonstrating the model’s capacity for creative, context-aware text generation.

This video serves as a powerful example of how **the lightweight yet capable Gemma 3 270M can power fast, engaging, and interactive applications without relying on the cloud**, opening up new possibilities for on-device AI experiences.

Gemma 3 270M is released under the Gemma Terms of Use, which allow use, reproduction, modification, and distribution of the model and derivatives, provided certain conditions are met.

These include carrying forward use restrictions outlined in Google’s Prohibited Use Policy, supplying the Terms of Use to downstream recipients, and clearly indicating any modifications made. Distribution can be direct or through hosted services such as APIs or web apps.

For enterprise teams and commercial developers, this means the model can be embedded in products, deployed as part of cloud services, or fine-tuned into specialized derivatives, so long as licensing terms are respected. Outputs generated by the model are not claimed by Google, giving businesses full rights over the content they create.

However, developers are responsible for ensuring compliance with applicable laws and for avoiding prohibited uses, such as generating harmful content or violating privacy rules.

The **license is not open-source in the traditional sense, but it does enable broad commercial use without a separate paid license.**

For companies building commercial AI applications, the main operational considerations are ensuring end users are bound by equivalent restrictions, documenting model modifications, and implementing safety measures aligned with the prohibited uses policy.

With the Gemmaverse surpassing 200 million downloads and the Gemma lineup spanning cloud, desktop, and mobile-optimized variants, Google AI Developers are positioning Gemma 3 270M as a foundation for building fast, cost-effective, and privacy-focused AI solutions, and already, it seems off to a great start.

**Daily insights on business use cases with VB Daily**

If you want to impress your boss, VB Daily has you covered. We give you the inside scoop on what companies are doing with generative AI, from regulatory shifts to practical deployments, so you can share insights for maximum ROI.

Read our [Privacy Policy](https://venturebeat.com/terms-of-service/)

Thanks for subscribing. Check out more [VB newsletters here](https://venturebeat.com/newsletters/).

An error occured.

![](https://venturebeat.com/wp-content/themes/vb-news/brand/img/vb-daily-phone.png)
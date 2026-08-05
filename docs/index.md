---
title: LLMRouter
hide:
  - navigation
---

<section class="llmr-hero">
  <div class="llmr-hero-logo">
    <img src="assets/logo.png" alt="LLMRouter logo">
  </div>
  <p class="llmr-kicker">A unified library, evaluation suite, and analysis platform for LLM routing</p>
  <h1>LLMRouter</h1>
  <p class="llmr-subtitle">
    A modular open-source framework for training, evaluating, and deploying LLM routers that select the right model for each query under quality and cost constraints.
  </p>
  <div class="llmr-hero-actions" aria-label="Project links">
    <a href="leaderboard/">Leaderboard</a>
    <a href="https://github.com/YHD0225/LLMRouter" target="_blank" rel="noopener">Code</a>
  </div>
  <div class="llmr-badges" aria-label="Project badges">
    <span>16+ routers</span>
    <span>3 routing families</span>
    <span>xRouteBench</span>
    <span>Quality-cost evaluation</span>
  </div>
</section>

<section class="llmr-section llmr-overview">
  <h2>Overview</h2>
  <p>
    No single large language model is optimal across all queries, domains, and budgets. LLMRouter treats model selection as a routing problem: given a query, history, user context, and candidate model pool, the router decides which model should answer so that deployments can preserve response quality while controlling inference cost.
  </p>
  <p>
    The project contributes both a library and an evaluation protocol. The library standardizes router implementation behind common training, inference, data generation, and evaluation interfaces. The benchmark, xRouteBench, evaluates routers across general NLP, memory-augmented reasoning, multimodal understanding, video, time-series, personalized, and real-user settings.
  </p>
</section>

<section class="llmr-figure-section">
  <figure>
    <img src="assets/llmrouter_.png" alt="LLMRouter system overview">
    <figcaption>
      LLMRouter connects data generation, router training, inference, and benchmark evaluation under one reusable workflow.
    </figcaption>
  </figure>
</section>

<section class="llmr-section">
  <h2>What LLMRouter Provides</h2>
  <div class="llmr-feature-grid">
    <article>
      <span>01</span>
      <h3>Unified Routing Formulation</h3>
      <p>
        LLM routing is formulated as a sequential decision process with five components: context encoder, model encoder, scoring function, decision rule, and learning signal.
      </p>
    </article>
    <article>
      <span>02</span>
      <h3>Router Families</h3>
      <p>
        Existing methods are organized into single-turn, multi-turn, and personalized routing families, making router behavior easier to compare and extend.
      </p>
    </article>
    <article>
      <span>03</span>
      <h3>Modular Library</h3>
      <p>
        New routers can be added by implementing routing logic and a loss function, while the surrounding data, training, inference, and evaluation pipeline stays shared.
      </p>
    </article>
    <article>
      <span>04</span>
      <h3>Standardized Benchmark</h3>
      <p>
        xRouteBench runs routers under a consistent candidate model pool, metric suite, and cost-aware protocol for fair comparison.
      </p>
    </article>
  </div>
</section>

<section class="llmr-section llmr-framework">
  <h2>Unified Routing Framework</h2>
  <div class="llmr-framework-grid">
    <div>
      <h3>Routing state</h3>
      <p>Query, user context, interaction history, and candidate model information are represented as a state that can support both one-shot and multi-step routing.</p>
    </div>
    <div>
      <h3>Routing action</h3>
      <p>The router can dispatch a query to one or more candidate models, or terminate and aggregate collected responses in multi-turn settings.</p>
    </div>
    <div>
      <h3>Optimization goal</h3>
      <p>The objective balances task-specific response quality with inference cost, enabling evaluation under different budget regimes.</p>
    </div>
  </div>
</section>

<section class="llmr-section">
  <h2>xRouteBench</h2>
  <p>
    xRouteBench is designed to evaluate whether a router can generalize across task types and deployment conditions. It spans general NLP, memory-augmented tasks, image and video understanding, time-series reasoning, human-preference personalization, and real-user traces.
  </p>
  <div class="llmr-track-grid">
    <span>General NLP</span>
    <span>Memory</span>
    <span>Multimodal</span>
    <span>Video</span>
    <span>Time-series</span>
    <span>Personalized</span>
    <span>Real users</span>
  </div>
</section>

<section class="llmr-section">
  <h2>Key Findings</h2>
  <div class="llmr-finding-list">
    <p><strong>Learned routing improves over fixed-model baselines.</strong> The empirical study finds a 14.6% relative improvement over the strongest fixed-model baseline.</p>
    <p><strong>Cost changes the ranking.</strong> Router rankings can reverse under tighter cost constraints, favoring lightweight routing strategies in budget-sensitive settings.</p>
    <p><strong>Personalization matters.</strong> User-conditioned routing delivers consistent gains when preference or user context is available.</p>
  </div>
</section>

<section class="llmr-section">
  <h2>Citation</h2>
  <pre><code>@misc{feng2026llmrouter,
  title        = {LLMRouter: A Unified Library, Evaluation, and Analysis for LLM Routing},
  author       = {Tao Feng and Haozhen Zhang and Zijie Lei and Haodong Yue and Chongshan Lin and Jiaxuan You},
  year         = {2026},
  howpublished = {\url{https://github.com/ulab-uiuc/LLMRouter}}
}</code></pre>
</section>

---
title: LLMRouter
hide:
  - navigation
---

<section class="llmr-hero llmr-hero--research">
  <div class="llmr-hero-copy">
    <p class="llmr-eyebrow">LLM ROUTING, MADE COMPARABLE</p>
    <h1>Route every query<br>to the <em>right</em> LLM.</h1>
    <p class="llmr-subtitle">
      LLMRouter is an open-source library, evaluation pipeline, and benchmark for choosing models under real quality and cost constraints.
    </p>
    <div class="llmr-hero-actions" aria-label="Project links">
      <a href="leaderboard/">Explore the leaderboard <span aria-hidden="true">→</span></a>
      <a class="llmr-button--secondary" href="https://github.com/YHD0225/LLMRouter" target="_blank" rel="noopener">View code <span aria-hidden="true">↗</span></a>
    </div>
  </div>
  <div class="llmr-route-card" aria-label="Illustration of a routing decision">
    <div class="llmr-route-card__head">
      <span>ROUTING DECISION</span><span class="llmr-live-dot">LIVE</span>
    </div>
    <div class="llmr-query"><span>q</span><p>“Explain this chart and forecast next quarter.”</p></div>
    <div class="llmr-route-lines" aria-hidden="true"><i></i><i></i><i></i></div>
    <div class="llmr-model-choice llmr-model-choice--selected"><span>01</span><div><strong>Vision + reasoning model</strong><small>selected · quality / cost optimum</small></div><b>✓</b></div>
    <div class="llmr-model-choice"><span>02</span><div><strong>General chat model</strong><small>not selected · lower expected reward</small></div></div>
    <div class="llmr-model-choice"><span>03</span><div><strong>Large frontier model</strong><small>not selected · unnecessary cost</small></div></div>
  </div>
</section>

<section class="llmr-proof-strip" aria-label="LLMRouter at a glance">
  <div><strong>17</strong><span>built-in routers</span></div>
  <div><strong>3</strong><span>routing families</span></div>
  <div><strong>18</strong><span>candidate models evaluated</span></div>
  <div><strong>14.6%</strong><span>relative gain over the best fixed model</span></div>
</section>

<section class="llmr-section llmr-section--intro">
  <div class="llmr-section-label">WHY ROUTING</div>
  <div class="llmr-intro-grid">
    <h2>There is no universally best model.</h2>
    <div>
      <p>Capability, latency, modality support, price, conversation history, and user preference all change which model is the right choice. Always selecting the largest model is expensive—and it is not reliably best.</p>
      <p>LLMRouter makes that choice explicit. It formulates routing as a sequential decision process that optimizes <strong>response quality − cost</strong>, then gives researchers and builders one system to train, compare, and deploy routing policies.</p>
    </div>
  </div>
</section>

<section class="llmr-figure-section llmr-system-figure">
  <figure>
    <img src="assets/llmrouter_.png" alt="The LLMRouter unified routing framework">
    <figcaption>The same formulation captures one-shot model selection, multi-turn routing, and personalized routing.</figcaption>
  </figure>
</section>

<section class="llmr-section">
  <div class="llmr-section-label">ONE FORMULATION</div>
  <h2>Five components. Any router.</h2>
  <p class="llmr-section-lede">Every method is expressed as the same decision pipeline, so methods that once required incompatible codebases can be studied under shared assumptions.</p>
  <div class="llmr-component-grid">
    <article><span class="llmr-component-symbol">E<sub>q</sub></span><h3>Context encoder</h3><p>Represents the query, optional user context, and interaction history.</p></article>
    <article><span class="llmr-component-symbol">E<sub>m</sub></span><h3>Model encoder</h3><p>Describes candidates through metadata, history, or learned representations.</p></article>
    <article><span class="llmr-component-symbol">g</span><h3>Scoring function</h3><p>Measures how well each candidate fits the routing state.</p></article>
    <article><span class="llmr-component-symbol">d</span><h3>Decision rule</h3><p>Dispatches, escalates, or terminates while accounting for budget.</p></article>
    <article><span class="llmr-component-symbol">ℒ</span><h3>Learning signal</h3><p>Optimizes the quality–cost objective from pointwise, pairwise, or trajectory feedback.</p></article>
  </div>
  <div class="llmr-family-row" aria-label="Router families"><span>Single-turn</span><i></i><span>Multi-turn &amp; agentic</span><i></i><span>Personalized</span></div>
</section>

<section class="llmr-section llmr-pipeline-section">
  <div class="llmr-section-label">FROM DATA TO DEPLOYMENT</div>
  <h2>Build evidence before making a routing claim.</h2>
  <div class="llmr-pipeline">
    <article><span>01</span><h3>Curate queries</h3><p>Normalize benchmark or custom tasks into a common schema with ground truth and task metrics.</p></article>
    <article><span>02</span><h3>Collect responses</h3><p>Run every candidate model, record outputs and token usage, and construct dense routing supervision.</p></article>
    <article><span>03</span><h3>Score &amp; price</h3><p>Apply task-specific quality metrics and per-token cost under one reproducible protocol.</p></article>
    <article><span>04</span><h3>Train, evaluate, deploy</h3><p>Sweep operating points, compare frontiers, then serve the same router in an OpenAI-compatible stack.</p></article>
  </div>
</section>

<section class="llmr-section llmr-benchmark-section">
  <div class="llmr-benchmark-copy">
    <div class="llmr-section-label">XROUTEBENCH</div>
    <h2>A benchmark for the settings where routing actually changes.</h2>
    <p>Every router faces the same queries, candidate pool, metrics, and quality–cost objective. xRouteBench covers 4,767 test queries in eight test sets across five tracks, including long-context memory, visual inputs, time-series, and user-specific preferences.</p>
    <a class="llmr-text-link" href="leaderboard/">Compare routers across operating points <span aria-hidden="true">→</span></a>
  </div>
  <div class="llmr-track-grid llmr-track-grid--rich">
    <span><b>01</b>General LLM tasks</span>
    <span><b>02</b>Memory</span>
    <span><b>03</b>Vision &amp; video</span>
    <span><b>04</b>Time-series</span>
    <span><b>05</b>Personalization</span>
  </div>
</section>

<section class="llmr-section llmr-findings-section">
  <div class="llmr-section-label">WHAT THE STUDY FINDS</div>
  <h2>Routing is an operating-point decision.</h2>
  <div class="llmr-finding-grid">
    <article><span class="llmr-findings-number">14.6%</span><h3>Learned routes beat the best fixed-model baseline.</h3><p>They can choose smaller, cheaper models for queries where the largest model has no advantage.</p></article>
    <article><span class="llmr-findings-number">≠</span><h3>No router wins every task or budget.</h3><p>Rankings reverse as cost weight changes—router choice should match the deployment objective.</p></article>
    <article><span class="llmr-findings-number">83.05</span><h3>Personalization wins with live feedback.</h3><p>On held-out real-user sessions, the best personalized router matched user preferences 83.05% of the time.</p></article>
  </div>
</section>

<section class="llmr-section llmr-build-section">
  <div>
    <div class="llmr-section-label">OPEN SOURCE</div>
    <h2>Start with a router. End with a system.</h2>
    <p>Implement the routing method and loss function; LLMRouter supplies shared data construction, training, inference, evaluation, and deployment infrastructure.</p>
  </div>
  <div class="llmr-build-actions">
    <a href="https://github.com/YHD0225/LLMRouter" target="_blank" rel="noopener">Open the repository <span aria-hidden="true">↗</span></a>
    <a href="leaderboard/">See benchmark results <span aria-hidden="true">→</span></a>
  </div>
</section>

<section class="llmr-citation">
  <div><span>RESEARCH</span><h2>Cite LLMRouter</h2></div>
  <pre><code>@misc{feng2026llmrouter,
  title  = {LLMRouter: A Unified Library, Evaluation, and Analysis for LLM Routing},
  author = {Tao Feng and Haozhen Zhang and Zijie Lei and Haodong Yue and Chongshan Lin and Jiaxuan You},
  year   = {2026}
}</code></pre>
</section>

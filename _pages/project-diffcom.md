---
title: "DiffCom"
permalink: /project/DiffCom/
layout: project-landing
---

<style>
  html,
  body {
    margin: 0;
    padding: 0;
    background: #ffffff;
    color: #111111;
    font-family: "Noto Sans", "Helvetica Neue", Helvetica, Arial, sans-serif;
    font-size: 17px;
  }

  .layout--project-landing .initial-content,
  .layout--project-landing #main,
  .layout--project-landing .page__footer {
    display: none;
  }

  .dc-page,
  .dc-page * {
    box-sizing: border-box;
  }

  .dc-shell {
    width: 100%;
    max-width: 980px;
    margin: 0 auto;
    padding: 34px 22px 72px;
  }

  .dc-hero {
    text-align: center;
  }

  .dc-title {
    margin: 0 auto 16px;
    max-width: 940px;
    font-size: clamp(2.15rem, 4.6vw, 3.55rem);
    line-height: 1.12;
    font-weight: 700;
    letter-spacing: -0.025em;
  }

  .dc-authors,
  .dc-affiliations,
  .dc-meta {
    margin: 0 auto 6px;
    max-width: 960px;
    font-size: 1.02rem;
    line-height: 1.65;
  }

  .dc-authors strong {
    font-weight: 700;
  }

  .dc-links {
    display: flex;
    justify-content: center;
    flex-wrap: wrap;
    gap: 14px;
    margin: 26px 0;
  }

  .dc-links a {
    display: inline-flex;
    align-items: center;
    justify-content: center;
    min-width: 108px;
    padding: 12px 18px;
    border-radius: 8px;
    border: 1px solid #d7d7d7;
    background: #f4f4f4;
    color: #1a5fb4;
    font-weight: 600;
    text-decoration: none;
    transition: background 0.18s ease, transform 0.18s ease, box-shadow 0.18s ease;
  }

  .dc-links a:hover {
    background: #e8e8e8;
    color: #154a8a;
    text-decoration: none;
    transform: translateY(-1px);
    box-shadow: 0 8px 18px rgba(15, 23, 42, 0.08);
  }

  .dc-page a {
    color: #1a5fb4;
  }

  .dc-page a:hover {
    color: #154a8a;
  }

  .dc-tldr {
    margin: 0 auto 30px;
    max-width: 880px;
    text-align: center;
    font-size: 1.08rem;
    line-height: 1.7;
  }

  .dc-section {
    margin-top: 42px;
  }

  .dc-section-title {
    margin: 0 0 16px;
    text-align: center;
    font-size: 1.7rem;
    font-weight: 700;
    letter-spacing: -0.01em;
  }

  .dc-page p {
    margin: 0 auto 14px;
    line-height: 1.62;
  }

  .dc-abstract,
  .dc-text {
    max-width: 900px;
    text-align: left;
    color: #222222;
  }

  .dc-figure {
    margin: 18px auto 24px;
    max-width: 940px;
    text-align: center;
  }

  .dc-figure img {
    max-width: 100%;
    width: 100%;
    display: block;
    margin: 0 auto;
  }

  .dc-figure-small {
    max-width: 720px;
  }

  .dc-figure figcaption {
    margin-top: 10px;
    font-size: 0.92rem;
    line-height: 1.55;
    color: #4a4a4a;
    text-align: center;
  }

  .dc-table {
    width: 100%;
    border-collapse: collapse;
    margin: 18px auto 8px;
    max-width: 760px;
    font-size: 0.98rem;
  }

  .dc-table th,
  .dc-table td {
    padding: 10px 12px;
    border: 1px solid #d6d6d6;
    text-align: center;
  }

  .dc-table th {
    background: #f4f4f4;
    font-weight: 700;
  }

  .dc-citation {
    max-width: 920px;
    margin: 0 auto;
  }

  .dc-citation pre {
    margin: 0;
    padding: 18px 20px;
    background: #f7f7f7;
    border-radius: 4px;
    border: 1px solid #dddddd;
    white-space: pre-wrap;
    word-break: break-word;
    font-size: 0.96rem;
    line-height: 1.6;
    font-family: ui-monospace, SFMono-Regular, Menlo, Consolas, monospace;
  }

  .dc-anchor {
    scroll-margin-top: 24px;
  }

  @media (max-width: 640px) {
    .dc-shell {
      padding: 24px 16px 56px;
    }

    .dc-title {
      font-size: 2rem;
    }

    .dc-links a {
      min-width: 96px;
      padding: 10px 16px;
    }
  }
</style>

<div class="dc-page">
  <main class="dc-shell">
    <section class="dc-hero">
      <h1 class="dc-title">DiffCom: Decoupled Sparse Priors Guided Diffusion Compression for Point Clouds</h1>
      <p class="dc-authors"><strong>Xiaoge Zhang</strong>, Zijie Wu, Mingtao Feng, Mehwish Nasim, Saeed Anwar, Ajmal Mian</p>
      <p class="dc-affiliations">The University of Western Australia, Xidian University</p>
      <p class="dc-meta">IEEE Transactions on Circuits and Systems for Video Technology (TCSVT), 2026</p>
      <div class="dc-links">
        <a href="https://arxiv.org/abs/2411.13860v3">Paper</a>
        <a href="#pipeline">Pipeline</a>
        <a href="#code">Code</a>
        <a href="#data">Data</a>
      </div>
      <p class="dc-tldr">DiffCom is a decoupled sparse-prior guided diffusion framework for point cloud compression, designed to reduce latent redundancy while preserving high-fidelity geometry under aggressive bitrates.</p>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/fig1-improve.png' | relative_url }}" alt="DiffCom improvement visualization">
      </figure>
    </section>

    <section id="abstract" class="dc-section dc-anchor">
      <h2 class="dc-section-title">Abstract</h2>
      <p class="dc-abstract">While conventional lossy compression methods predominantly depend on autoencoders to map point clouds into latent representations, they often neglect the intrinsic redundancy within these latent points. To address this limitation, DiffCom presents a diffusion-based architecture steered by sparse priors, designed to minimize latent redundancy while securing superior reconstruction fidelity, particularly in low-bitrate scenarios.</p>
      <p class="dc-abstract">A key feature of the framework is an efficient dual-density data flow that alleviates the stringent size constraints imposed on latent points. By integrating a Probabilistic Attention-based Conditional Denoiser (PACD), the method encapsulates critical reconstruction details within sparse priors, which are hierarchically decoupled into intra- and inter-point components. Comprehensive experiments on ShapeNet and standard MPEG PCC datasets demonstrate superior rate-distortion trade-offs.</p>
    </section>

    <section id="pipeline" class="dc-section dc-anchor">
      <h2 class="dc-section-title">Pipeline</h2>
      <p class="dc-text">The pipeline employs a two-stage data flow. First, DiffCom extracts sparse priors through a sparse point encoder and context-aware entropy model. Then, during decompression, it starts from Gaussian noise and applies PACD conditioned on the sparse priors to reconstruct dense latent representations, which are decoded into the final point cloud.</p>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/quickrun.png' | relative_url }}" alt="Comparison between conventional compression and DiffCom">
        <figcaption><strong>Figure 1.</strong> (a) Conventional compressors code the latent representation of points directly via a naive context-free entropy model. (b) Our method codes the sparse priors via a context-aware entropy model. It employs a two-stage data flow to compress the points further into decoupled sparse priors. It incorporates a probabilistic attention-based conditional denoiser (PACD) model to denoise the latent representations conditioned on the sparse priors.</figcaption>
      </figure>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/overview.png' | relative_url }}" alt="DiffCom framework overview">
        <figcaption><strong>Figure 2.</strong> Overview of our decoupled sparse priors guided diffusion compression model for point cloud (DiffCom). Instead of directly encoding the input point cloud into latent points and features, we utilize a sparse point encoder to extract a sparser representation. The sparser representations are decoupled into sparse points and inter-point local distributions. During decompression, we begin with Gaussian noise and apply a Probabilistic attention-based conditional denoiser (PACD) conditioned on the sparse priors, reconstructing the latent representation. These reconstructed latents are then decoded to produce a high-quality point cloud.</figcaption>
      </figure>
    </section>

    <section class="dc-section">
      <h2 class="dc-section-title">Qualitative Results</h2>
      <p class="dc-text">DiffCom preserves more complete object structures at matched bitrates on ShapeNet and generalizes to dense MPEG point clouds.</p>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/shapenet-qualitative.png' | relative_url }}" alt="ShapeNet qualitative comparison">
        <figcaption>Qualitative results on ShapeNet at two selected rates.</figcaption>
      </figure>
      <figure class="dc-figure dc-figure-small">
        <img src="{{ '/images/projects/diffcom/mpeg-vis.png' | relative_url }}" alt="MPEG qualitative comparison">
        <figcaption>Qualitative comparison on longdress_vox10_1300 from the MPEG dataset.</figcaption>
      </figure>
    </section>

    <section id="data" class="dc-section dc-anchor">
      <h2 class="dc-section-title">Datasets</h2>
      <p class="dc-text">DiffCom is trained on ShapeNet and evaluated on object-level ShapeNet point clouds as well as standard MPEG PCC test samples from 8iVFB and Owlii.</p>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/shapenet-sample.png' | relative_url }}" alt="ShapeNet training samples">
        <figcaption>Training samples from ShapeNet.</figcaption>
      </figure>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/mvub-sample.png' | relative_url }}" alt="MPEG test samples">
        <figcaption>Test samples from 8iVFB and Owlii datasets.</figcaption>
      </figure>
    </section>

    <section id="results" class="dc-section dc-anchor">
      <h2 class="dc-section-title">Rate-Distortion Results</h2>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/mpeg-rdcurve.png' | relative_url }}" alt="MPEG rate-distortion curve">
        <figcaption>Rate-distortion performance on the MPEG dataset.</figcaption>
      </figure>
      <figure class="dc-figure">
        <img src="{{ '/images/projects/diffcom/shapenet-rdcurve.png' | relative_url }}" alt="ShapeNet rate-distortion curve">
        <figcaption>Rate-distortion performance on the ShapeNet dataset.</figcaption>
      </figure>
      <figure class="dc-figure dc-figure-small">
        <img src="{{ '/images/projects/diffcom/shapenet-ablation.png' | relative_url }}" alt="ShapeNet ablation on denoising steps">
        <figcaption>Ablation of denoising steps on ShapeNet.</figcaption>
      </figure>
      <div style="width:100%; overflow-x:auto;">
        <table class="dc-table">
          <thead>
            <tr>
              <th>Dataset</th>
              <th>PSNR Gain</th>
              <th>Rate Saving</th>
            </tr>
          </thead>
          <tbody>
            <tr>
              <td>MPEG average vs. G-PCC</td>
              <td>+14.62 dB</td>
              <td>98.46%</td>
            </tr>
            <tr>
              <td>ShapeNet vs. Depoco</td>
              <td>+6.89 dB</td>
              <td>89.31%</td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <section id="code" class="dc-section dc-anchor">
      <h2 class="dc-section-title">Code</h2>
      <p class="dc-text">Code will be released when available.</p>
    </section>

    <section id="citation" class="dc-section dc-anchor">
      <h2 class="dc-section-title">Citation</h2>
      <div class="dc-citation">
        <pre>@article{zhang2026diffcom,
  title={DiffCom: Decoupled Sparse Priors Guided Diffusion Compression for Point Clouds},
  author={Zhang, Xiaoge and Wu, Zijie and Feng, Mingtao and Nasim, Mehwish and Anwar, Saeed and Mian, Ajmal},
  journal={IEEE Transactions on Circuits and Systems for Video Technology},
  year={2026},
  publisher={IEEE}
}</pre>
      </div>
    </section>
  </main>
</div>

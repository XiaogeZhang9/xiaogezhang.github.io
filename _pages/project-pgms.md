---
title: "PGMS"
permalink: /project/PGMS/
layout: default
author_profile: false
---

<html>
<head>
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/css/bootstrap.min.css">
    <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.4.0/css/font-awesome.min.css">
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/1.11.3/jquery.min.js"></script>
    <script src="https://maxcdn.bootstrapcdn.com/bootstrap/3.3.5/js/bootstrap.min.js"></script>
    <style>
        * { box-sizing: border-box; }
        body { font-family: 'Helvetica Neue', Helvetica, Arial, sans-serif; }
        a { color: #1a5fb4; }
        a:hover { color: #154a8a; }
        .container#main { width: 100%; max-width: 1100px; padding-top: 20px; }
        .row { margin-left: 0; margin-right: 0; }
        .text-justify { text-align: justify; }
        .pt-5 { padding-top: 30px; }
        .bibtex pre { background: #f5f5f5; padding: 15px; border-radius: 4px; font-size: 13px; }
        h2.text-center { margin-top: 30px; }
        .img-responsive { display: block; max-width: 100% !important; height: auto; }
        .list-inline > li { padding-right: 10px; padding-left: 10px; }
        .result-figure { margin: 20px auto 30px; text-align: center; }
        .result-figure img { max-width: 100%; height: auto; margin: 0 auto; }
        .result-figure-caption { margin-top: 10px; font-size: 13px; text-align: justify; }
        .table-responsive { width: 100%; overflow-x: auto; -webkit-overflow-scrolling: touch; }
        .nav-pills > li > a { color: #1a5fb4; }
        .nav-pills > li > a:hover, .nav-pills > li > a:focus { color: #154a8a; }
    </style>
</head>
<body>
    <div class="container" id="main">
        <div class="row">
            <h2 class="col-md-12 text-center">
                PGMS: Pyramidal Gaussian Mixture Splatting for 3DGS Compression<br>
                <small>
                </small>
            </h2>
        </div>

        <div class="row">
            <div class="col-md-12 text-center">
                <ul class="list-inline">
                    <li><a href="{{ '/' | relative_url }}">Xiaoge Zhang<sup>1</sup></a></li>
                    <li>Zijie Wu<sup>1</sup></li>
                    <li>Zichen Geng<sup>1</sup></li>
                    <li>Mehwish Nasim<sup>1</sup></li>
                    <li>Saeed Anwar<sup>1</sup></li>
                    <li>Ajmal Mian<sup>1</sup></li>
                </ul>
                <ul class="list-inline">
                    <li><sup>1</sup>The University of Western Australia</li>
                </ul>
            </div>
        </div>

        <div class="row">
            <div class="col-md-8 col-md-offset-2 text-center">
                <ul class="nav nav-pills nav-justified">
                    <li>
                        <a href="https://arxiv.org/abs/">
                            <i class="fa fa-file-pdf-o fa-3x"></i>
                            <h4><strong>Paper</strong></h4>
                        </a>
                    </li>
                    <li>
                        <a href="https://github.com/XiaogeZhang9">
                            <i class="fa fa-github fa-3x"></i>
                            <h4><strong>Code</strong></h4>
                        </a>
                    </li>
                </ul>
            </div>
        </div>

        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>Abstract</h3>
                <p class="text-justify">
                    3D Gaussian Splatting (3DGS) has become an established representation for real-time novel view synthesis. However, preserving fine geometric structures and appearance details typically requires millions of Gaussian primitives, resulting in substantial storage and transmission overhead. 3DGS compression has been extensively studied through attribute quantization, entropy coding, and lightweight reparameterization. However, existing methods often operate on a fixed backbone and therefore do not explicitly model the joint redundancy between geometry and appearance in the original dense Gaussian set.
                </p>
                <p class="text-justify">
                    To address this limitation, we propose <strong>Pyramidal Gaussian Mixture Splatting</strong> (PGMS), a plug-and-play 3DGS compression framework that reformulates dense Gaussian primitives into a rate-controllable pyramidal representation with scale-dependent attributes. Experiments on standard benchmarks show that our method delivers strong compression with high rendering fidelity and consistently outperforms state-of-the-art 3DGS compression methods.
                </p>
            </div>
        </div>

        <div class="row">
            <div class="col-md-10 col-md-offset-1">
                <h2 class="text-center pt-5">Pipeline</h2>
                <div class="result-figure">
                    <img src="{{ '/images/projects/pgms/overview-screenshot.png' | relative_url }}" class="img-responsive" alt="PGMS mixture primitive pyramid construction">
                    <p class="result-figure-caption">
                        Given a set of densified Gaussians, PGMS adaptively learns a tiered budget for the mixture pyramid, constructs a Mixture Primitive Pyramid through level-wise clustering, and applies compositing-aware updates to preserve visual fidelity.
                    </p>
                </div>
            </div>
        </div>

        <div class="row">
            <div class="col-md-10 col-md-offset-1">
                <h2 class="text-center pt-5">Results</h2>

                <h3>Main Quantitative Results</h3>
                <div class="result-figure">
                    <img src="{{ '/images/projects/pgms/table-main.png' | relative_url }}" class="img-responsive" alt="PGMS main quantitative comparison table">
                    <p class="result-figure-caption">
                        Comparison on MipNeRF-360, Tanks&amp;Temples and Deep Blending with Size/Count metrics.
                    </p>
                </div>

                <h3>Qualitative Comparison</h3>
                <div class="result-figure">
                    <img src="{{ '/images/projects/pgms/qualitative.png' | relative_url }}" class="img-responsive" alt="PGMS qualitative comparison">
                    <p class="result-figure-caption">
                        Qualitative comparison with GHAP, MaskGaussian, and PCGS.
                    </p>
                </div>

                <h3>Computational Efficiency</h3>
                <div class="result-figure">
                    <img src="{{ '/images/projects/pgms/efficiency.png' | relative_url }}" class="img-responsive" alt="PGMS computational efficiency comparison">
                    <p class="result-figure-caption">
                        Complexity comparison across Scaffold-GS backbone on Mip-NeRF360, Tanks &amp; Temples, and Deep Blending datasets.
                    </p>
                </div>
            </div>
        </div>

        <!-- Citation (hidden until accepted) -->
        <!--
        <div class="row">
            <h2 class="text-center">Citation</h2>
            <div class="bibtex col-md-8 col-md-offset-2">
                <pre>@inproceedings{zhang2026pgms,
  title     = {PGMS: Pyramidal Gaussian Mixture Splatting for 3DGS Compression},
  author    = {Zhang, Xiaoge and Wu, Zijie and Geng, Zichen and Nasim, Mehwish and Anwar, Saeed and Mian, Ajmal},
  booktitle = {Advances in Neural Information Processing Systems (NeurIPS)},
  year      = {2026}
}</pre>
            </div>
        </div>
        -->

        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>Acknowledgements</h3>
                <p class="text-justify">
                    This work was supported by the Australian Research Council (ARC) under discovery grant project # 240101926. Professor Ajmal Mian was supported by ARC Fellowship Award funded by Australian Government under Project FT210100268.
                </p>
            </div>
        </div>
    </div>
</body>
</html>

---
title: "FLaTEC"
permalink: /project/FLaTEC/
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
        .pt-3 { padding-top: 15px; }
        .pt-5 { padding-top: 30px; }
        .bibtex pre { background: #f5f5f5; padding: 15px; border-radius: 4px; font-size: 13px; }
        h2.text-center { margin-top: 30px; }
        .img-responsive { display: block; max-width: 100% !important; height: auto; }
        .list-inline > li { padding-right: 10px; padding-left: 10px; }
        table { margin: 0 auto; }
        .table-custom { border-top: 2px solid #000; border-bottom: 2px solid #000; }
        .table-custom td, .table-custom th { padding: 6px 12px; text-align: center; }
        .table-responsive { width: 100%; overflow-x: auto; -webkit-overflow-scrolling: touch; }
        .nav-pills > li > a { color: #1a5fb4; }
        .nav-pills > li > a:hover, .nav-pills > li > a:focus { color: #154a8a; }
    </style>
</head>
<body>
    <div class="container" id="main">
        <div class="row">
            <h2 class="col-md-12 text-center">
                FLaTEC: Frequency-disentangled Latent Triplanes for Efficient Compression of LiDAR Point Clouds<br>
                <small>
                    ICME 2026
                </small>
            </h2>
        </div>
        <div class="row">
            <div class="col-md-12 text-center">
                <ul class="list-inline">
                    <li>
                        <a href="{{ '/' | relative_url }}">
                            Xiaoge Zhang<sup>1</sup>
                        </a>
                    </li>
                    <li>
                        Zijie Wu<sup>1</sup>
                    </li>
                    <li>
                        Mingtao Feng<sup>2</sup>
                    </li>
                    <li>
                        Zichen Geng<sup>1</sup>
                    </li>
                    <li>
                        Mehwish Nasim<sup>1</sup>
                    </li>
                    <li>
                        Saeed Anwar<sup>1</sup>
                    </li>
                    <li>
                        Ajmal Mian<sup>1</sup>
                    </li>
                </ul>
                <ul class="list-inline">
                    <li>
                        <sup>1</sup>The University of Western Australia
                    </li>
                    <li>
                        <sup>2</sup>Xidian University
                    </li>
                </ul>
            </div>
        </div>

        <div class="row">
            <div class="col-md-8 col-md-offset-2 text-center">
                <ul class="nav nav-pills nav-justified">
                    <li>
                        <a href="https://arxiv.org/abs/2511.20065">
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

        <!-- Teaser -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/flatec/quickshot.png' | relative_url }}" class="img-responsive" style="width: 90%; margin: 0 auto;">
                </p>
                <p class="text-justify">
                    Qualitative and quantitative comparison of point cloud compression methods. The proposed FLaTEC substantially reduces both the compressed file size and encoding/decoding time, while achieving comparable reconstruction quality to the baseline. The zoom-in region highlights on-road vehicles in the autonomous driving context.
                </p>
            </div>
        </div>

        <!-- Abstract -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>
                    Abstract
                </h3>
                <p class="text-justify">
                    Point cloud compression methods jointly optimize bitrates and reconstruction distortion. However, balancing compression ratio and reconstruction quality is difficult because low-frequency and high-frequency components contribute differently at the same resolution. To address this, we propose FLaTEC, a frequency-aware compression model that enables high compression of a full scan. We first convert voxelized embeddings into triplane representations to reduce sparsity and storage requirements, and then introduce a frequency-disentangling technique that isolates compact low-frequency components while aggregating multi-scale high-frequency details. The decoupled low-frequency and high-frequency components are stored in binary format. During decoding, full-spectrum signals are progressively recovered via a modulation block. Our method achieves state-of-the-art rate-distortion performance and outperforms the standard codecs by 78% and 94% in BD-rate on both SemanticKITTI and Ford datasets.
                </p>
            </div>
        </div>

        <!-- Key Idea -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>
                    Key Idea: Anisotropic Bitrate Allocation
                </h3>
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/flatec/quickrun.png' | relative_url }}" class="img-responsive" style="width: 55%; margin: 0 auto;">
                </p>
                <p class="text-justify">
                    (a) Traditional deep learning methods encode all frequency components at the same resolution, resulting in a suboptimal trade-off for compression. (b) Our method disentangles high-frequency details from basic features, allowing for flexible bitrate allocation across different levels of detail.
                </p>
            </div>
        </div>

        <!-- Pipeline -->
        <div class="row">
            <div class="col-md-10 col-md-offset-1">
                <h2 class="text-center pt-5">Pipeline</h2>
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/flatec/pipeline.png' | relative_url }}" class="img-responsive" style="width: 100%;">
                </p>
                <p class="text-justify">
                    Overview of our compression method. FD and FM refer to feature decomposition and frequency modulation. HF is high frequency. Voxel features are initially projected onto three orthogonal views&mdash;top, front, and side&mdash;to reduce sparsity and storage costs. These projected triplane features are then processed through separate 2D encoders, which output global content and high-frequency priors. The encoded features are subsequently quantized and converted into a binary string. During decoding, 2D decoders reconstruct fine-grained triplane features guided by high-frequency priors. Finally, the voxel features are refined with spatial correlations before generating volumetric occupancy probability.
                </p>
            </div>
        </div>

        <!-- Quantitative Results -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h2 class="text-center pt-5">Results</h2>
                <h3>Runtime and Rate-Performance on 40mILEN</h3>
                <div class="table-responsive">
                    <table class="table table-custom">
                        <thead>
                            <tr>
                                <th>Method</th>
                                <th>Enc/Dec (s)</th>
                                <th>Rate Gain</th>
                                <th>PSNR Gain</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>G-PCC</td>
                                <td>2.25/1.43</td>
                                <td>0.00%</td>
                                <td>0.00</td>
                            </tr>
                            <tr>
                                <td>Depoco</td>
                                <td><u>0.17</u>/<b>0.00086</b></td>
                                <td>+54.04%</td>
                                <td>-2.06</td>
                            </tr>
                            <tr>
                                <td>D-PCC</td>
                                <td>1.26/0.24</td>
                                <td>+89.70%</td>
                                <td>-0.46</td>
                            </tr>
                            <tr>
                                <td>Pointsoup</td>
                                <td>2.58/<u>0.0045</u></td>
                                <td><u>-64.11%</u></td>
                                <td><b>+3.40</b></td>
                            </tr>
                            <tr>
                                <td>Ours (w/o R)</td>
                                <td><b>0.065</b>/0.12</td>
                                <td><b>-94.21%</b></td>
                                <td>+1.40</td>
                            </tr>
                            <tr>
                                <td>Ours</td>
                                <td><b>0.065</b>/0.19</td>
                                <td>-93.73%</td>
                                <td><u>+1.89</u></td>
                            </tr>
                        </tbody>
                    </table>
                </div>
            </div>
        </div>

        <!-- Rate-Distortion SemanticKITTI -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>Rate-Distortion on SemanticKITTI</h3>
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/flatec/kitti_runtime.png' | relative_url }}" class="img-responsive" style="width: 90%; margin: 0 auto;">
                </p>
                <p class="text-justify">
                    Left: Decoding efficiency and model footprint on SemanticKITTI, circle size indicates model size. Right: Rate-distortion curve on SemanticKITTI_vox1mm.
                </p>
            </div>
        </div>

        <!-- Generalization on Ford -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>Generalization on Ford Dataset</h3>
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/flatec/ford_rd.png' | relative_url }}" class="img-responsive" style="width: 90%; margin: 0 auto;">
                </p>
                <p class="text-justify">
                    Generalization ability test on Ford Dataset. Our method demonstrates robustness and generalizes well to unseen LiDAR scenes.
                </p>
            </div>
        </div>

        <!-- Qualitative Results -->
        <div class="row">
            <div class="col-md-10 col-md-offset-1">
                <h2 class="text-center pt-5">Qualitative Results</h2>
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/flatec/qualitative_semkitti.png' | relative_url }}" class="img-responsive" style="width: 100%;">
                </p>
                <p class="text-center">
                    Qualitative results on the 40mILEN dataset. E/D denotes encoding and decoding time (in secs). Zoom in for details.
                </p>
            </div>
        </div>

        <!-- Citation -->
        <div class="row">
            <h2 class="text-center">Citation</h2>
            <div class="bibtex col-md-8 col-md-offset-2">
                <pre>@inproceedings{zhang2026flatec,
  title     = {FLaTEC: Frequency-disentangled Latent Triplanes for Efficient Compression of LiDAR Point Clouds},
  author    = {Zhang, Xiaoge and Wu, Zijie and Feng, Mingtao and Geng, Zichen and Nasim, Mehwish and Anwar, Saeed and Mian, Ajmal},
  booktitle = {IEEE International Conference on Multimedia and Expo (ICME)},
  year      = {2026}
}</pre>
            </div>
        </div>

        <!-- Acknowledgements -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h3>
                    Acknowledgements
                </h3>
                <p class="text-justify">
                    This work was supported by the Australian Research Council (ARC) under discovery grant project # 240101926. Professor Ajmal Mian was supported by ARC Fellowship Award funded by Australian Government under Project FT210100268.
                </p>
            </div>
        </div>
    </div>
</body>
</html>

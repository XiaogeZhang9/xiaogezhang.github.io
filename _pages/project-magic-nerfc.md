---
title: "MaGic-NeRF"
permalink: /project/MaGiC-NeRF/
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
                MAGiC-NeRF: Multimodal Generative Priors and Conditional Flow<br>for Extreme NeRF Compression<br>
                <small>
                    Submitted to IEEE Transactions on Circuits and Systems for Video Technology (TCSVT), 2026
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
                        Zichen Geng<sup>1</sup>
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
                </ul>
            </div>
        </div>

        <div class="row">
            <div class="col-md-8 col-md-offset-2 text-center">
                <ul class="nav nav-pills nav-justified">
                    <li>
                        <a href="#">
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
                    <img src="{{ '/images/projects/magic-nerfc/quickrun.png' | relative_url }}" class="img-responsive" style="width: 85%; margin: 0 auto;">
                </p>
                <p class="text-justify">
                    <strong>Figure 1.</strong> Our MaGic-NeRF achieves ultra-high compression ratios, storing a single model in just 0.04 MB. We transform the NeRF into conditionally generative neural planes, employing an LMM to decompose the condition into compact semantic representations.
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
                    Neural Radiance Fields (NeRFs) offer realistic scene representations but require substantial storage, limiting their deployment in real-world systems. Existing NeRF compression methods inherently face a trade-off between compression efficiency and reconstruction fidelity, and cannot fully exploit the semantic priors naturally present in scenes. We introduce MaGic-NeRF, a novel framework that achieves extremely high compression ratios by leveraging robust flow models and multimodal semantic priors. To reduce storage overhead, we distill a trained NeRF into neural planes and encode them with a flow model conditioned on a rendered image. The conditioning image is hierarchically reasoned by large multimodal models (LMMs), enabling semantic-aware decomposition and intuitively guided reconstruction.
                </p>
                <p class="text-justify">
                    We also introduce 3DFRONT-NeRF, an indoor dataset that combines complex scene-level geometry with controllable object-level semantics, featuring realistic materials and physically-based lighting in complex room layouts. The benchmark supports novel view synthesis, 3D reconstruction, semantic reasoning, and layout generation. Extensive experiments demonstrate that our approach achieves compression ratios of up to <b>1900&times;</b> and <b>4400&times;</b> relative to TensoRF on our 3DFRONT-NeRF and LLFF, respectively, and <b>125&times;</b> relative to the original MLP-based NeRF on object-level datasets. We will release the code and dataset.
                </p>
            </div>
        </div>

        <!-- Pipeline -->
        <div class="row">
            <div class="col-md-10 col-md-offset-1">
                <h2 class="text-center pt-5">Pipeline</h2>
                <p style="text-align: center;">
                    <img src="{{ '/images/projects/magic-nerfc/pipeline.png' | relative_url }}" class="img-responsive" style="width: 100%;">
                </p>
                <p class="text-justify">
                    <strong>Figure 2.</strong> Overview of our MaGic-NeRF framework. (a) A pretrained TensoRF is distilled into a triplane, which is then embedded using HDT-Flow conditioned on a rendered image. (b) The conditioning image is decomposed into a compact 2D semantic prior consisting of an ultra-low-resolution image, text, and a mask. (c) The stored semantic prior is passed through a step-wise generation process to recover the condition image. (d) The recovered image is fed to the inverse flow to reconstruct a high-fidelity triplane for direct rendering. Dashed boxes indicate trainable modules.
                </p>
            </div>
        </div>

        <!-- Quantitative Results -->
        <div class="row">
            <div class="col-md-8 col-md-offset-2">
                <h2 class="text-center pt-5">Results</h2>
                <h3>Quantitative Comparisons on 3DFRONT-NeRF and LLFF</h3>
                <div class="table-responsive">
                    <table class="table table-custom">
                        <thead>
                            <tr>
                                <th rowspan="2">Models</th>
                                <th colspan="4">3DFRONT-NeRF</th>
                                <th colspan="4">LLFF</th>
                            </tr>
                            <tr>
                                <th>Size&darr;</th>
                                <th>Ratio&uarr;</th>
                                <th>PSNR&uarr;</th>
                                <th>SSIM&uarr;</th>
                                <th>Size&darr;</th>
                                <th>Ratio&uarr;</th>
                                <th>PSNR&uarr;</th>
                                <th>SSIM&uarr;</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td>TensoRF-VM</td>
                                <td>76.10</td>
                                <td>1.00</td>
                                <td>41.15</td>
                                <td><b>0.990</b></td>
                                <td>179.80</td>
                                <td>1.00</td>
                                <td><b>26.70</b></td>
                                <td><b>0.836</b></td>
                            </tr>
                            <tr>
                                <td>DVGO</td>
                                <td>135.35</td>
                                <td>0.56</td>
                                <td>29.96</td>
                                <td>0.918</td>
                                <td>-</td>
                                <td>-</td>
                                <td>-</td>
                                <td>-</td>
                            </tr>
                            <tr>
                                <td>VQ-DVGO</td>
                                <td>0.11</td>
                                <td>692.73</td>
                                <td>29.95</td>
                                <td>0.917</td>
                                <td>-</td>
                                <td>-</td>
                                <td>-</td>
                                <td>-</td>
                            </tr>
                            <tr>
                                <td>VQ-TensoRF</td>
                                <td>3.96</td>
                                <td>19.22</td>
                                <td>39.84</td>
                                <td>0.987</td>
                                <td>8.80</td>
                                <td>20.43</td>
                                <td>26.46</td>
                                <td>0.824</td>
                            </tr>
                            <tr>
                                <td>TC-TensoRF-l</td>
                                <td>4.00</td>
                                <td>19.03</td>
                                <td>40.74</td>
                                <td>0.988</td>
                                <td>4.90</td>
                                <td>36.73</td>
                                <td>26.44</td>
                                <td>0.826</td>
                            </tr>
                            <tr>
                                <td>TC-TensoRF-h</td>
                                <td>1.60</td>
                                <td>47.56</td>
                                <td>39.64</td>
                                <td>0.982</td>
                                <td>1.70</td>
                                <td>105.76</td>
                                <td>25.72</td>
                                <td>0.786</td>
                            </tr>
                            <tr>
                                <td>Re:TensoRF-l</td>
                                <td>36.36</td>
                                <td>2.09</td>
                                <td><b>41.59</b></td>
                                <td>0.989</td>
                                <td>20.20</td>
                                <td>8.91</td>
                                <td>26.55</td>
                                <td>0.797</td>
                            </tr>
                            <tr>
                                <td>Re:TensoRF-h</td>
                                <td>5.35</td>
                                <td>14.23</td>
                                <td>34.52</td>
                                <td>0.971</td>
                                <td>-</td>
                                <td>-</td>
                                <td>-</td>
                                <td>-</td>
                            </tr>
                            <tr>
                                <td>Snapshot</td>
                                <td>0.16</td>
                                <td>475.62</td>
                                <td>36.86</td>
                                <td>0.973</td>
                                <td>0.16</td>
                                <td>1123.75</td>
                                <td>24.59</td>
                                <td>0.747</td>
                            </tr>
                            <tr>
                                <td><b>Ours</b></td>
                                <td><b>0.04</b></td>
                                <td><b>1902.50</b></td>
                                <td>38.40</td>
                                <td>0.985</td>
                                <td><b>0.04</b></td>
                                <td><b>4495.00</b></td>
                                <td>25.30</td>
                                <td>0.785</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <p class="text-justify" style="font-size: 13px;">
                    Quantitative comparisons on 3DFRONT-NeRF and LLFF datasets. We mainly evaluate against TensoRF and other TensoRF-based compression methods. Best results are marked in <b>bold</b>. Size is measured in MB.
                </p>
            </div>
        </div>

        <!-- Table 2: NeRF-Synthetic, Synthetic-NSVF, Tanks & Temples -->
        <div class="row">
            <div class="col-md-10 col-md-offset-1">
                <h3 class="text-center">Quantitative Comparisons on NeRF-Synthetic, Synthetic-NSVF, and Tanks &amp; Temples</h3>
                <div class="table-responsive">
                    <table class="table table-custom" style="font-size: 13px;">
                        <thead>
                            <tr>
                                <th rowspan="2"></th>
                                <th rowspan="2">Models</th>
                                <th colspan="3">NeRF-Synthetic</th>
                                <th colspan="3">Synthetic-NSVF</th>
                                <th colspan="3">Tanks and Temples</th>
                            </tr>
                            <tr>
                                <th>Size&darr;</th>
                                <th>Ratio&uarr;</th>
                                <th>PSNR&uarr;</th>
                                <th>Size&darr;</th>
                                <th>Ratio&uarr;</th>
                                <th>PSNR&uarr;</th>
                                <th>Size&darr;</th>
                                <th>Ratio&uarr;</th>
                                <th>PSNR&uarr;</th>
                            </tr>
                        </thead>
                        <tbody>
                            <tr>
                                <td rowspan="11" style="vertical-align: middle; font-size: 12px;"><em>Conventional<br>NeRFs</em></td>
                                <td>NeRF</td>
                                <td>5.00</td><td>1.00</td><td>31.01</td>
                                <td>5.00</td><td>1.00</td><td>30.81</td>
                                <td>5.00</td><td>1.00</td><td>25.78</td>
                            </tr>
                            <tr>
                                <td>KiloNeRF</td>
                                <td>100.00</td><td>0.05</td><td>31.00</td>
                                <td>100.00</td><td>0.05</td><td>33.37</td>
                                <td>100.00</td><td>0.05</td><td>28.41</td>
                            </tr>
                            <tr>
                                <td>NSVF</td>
                                <td>16.00</td><td>0.31</td><td>31.74</td>
                                <td>16.00</td><td>0.31</td><td>35.18</td>
                                <td>16.00</td><td>0.31</td><td>28.40</td>
                            </tr>
                            <tr>
                                <td>TensoRF-CP</td>
                                <td>3.90</td><td>1.28</td><td>31.56</td>
                                <td>3.90</td><td>1.28</td><td>34.48</td>
                                <td>3.90</td><td>1.28</td><td>27.59</td>
                            </tr>
                            <tr>
                                <td>TensoRF-VM</td>
                                <td>71.80</td><td>0.07</td><td>33.14</td>
                                <td>72.00</td><td>0.07</td><td><b>36.71</b></td>
                                <td>76.20</td><td>0.07</td><td><b>28.56</b></td>
                            </tr>
                            <tr>
                                <td>InstantNGP*</td>
                                <td>11.60</td><td>0.43</td><td>32.82</td>
                                <td>-</td><td>-</td><td>-</td>
                                <td>-</td><td>-</td><td>28.36</td>
                            </tr>
                            <tr>
                                <td>PlenOctree</td>
                                <td>1976</td><td>0.003</td><td>31.71</td>
                                <td>-</td><td>-</td><td>-</td>
                                <td>1976</td><td>0.003</td><td>27.99</td>
                            </tr>
                            <tr>
                                <td>K-Planes</td>
                                <td>33.00</td><td>0.15</td><td>32.21</td>
                                <td>-</td><td>-</td><td>-</td>
                                <td>-</td><td>-</td><td>-</td>
                            </tr>
                            <tr>
                                <td>Plenoxels</td>
                                <td>259.80</td><td>0.02</td><td>31.71</td>
                                <td>283.30</td><td>0.02</td><td>34.12</td>
                                <td>367.70</td><td>0.01</td><td>26.84</td>
                            </tr>
                            <tr>
                                <td>DVGO</td>
                                <td>112.50</td><td>0.04</td><td>31.90</td>
                                <td>119.80</td><td>0.04</td><td>34.88</td>
                                <td>113.20</td><td>0.04</td><td>28.29</td>
                            </tr>
                            <tr>
                                <td>GS</td>
                                <td>67.30</td><td>0.07</td><td><b>33.80</b></td>
                                <td>-</td><td>-</td><td>-</td>
                                <td>-</td><td>-</td><td>27.94</td>
                            </tr>
                            <tr>
                                <td rowspan="10" style="vertical-align: middle; font-size: 12px;"><em>Compressed<br>NeRFs</em></td>
                                <td>SVRF</td>
                                <td>7.32</td><td>0.68</td><td>32.45</td>
                                <td>6.65</td><td>0.75</td><td>35.63</td>
                                <td>8.28</td><td>0.60</td><td>28.54</td>
                            </tr>
                            <tr>
                                <td>VQ-TensoRF</td>
                                <td>1.43</td><td>3.49</td><td>31.76</td>
                                <td>1.26</td><td>3.97</td><td>34.63</td>
                                <td>1.42</td><td>3.52</td><td>28.18</td>
                            </tr>
                            <tr>
                                <td>TinyNeRF</td>
                                <td>2.00</td><td>2.50</td><td>31.72</td>
                                <td>2.00</td><td>2.50</td><td>34.62</td>
                                <td>2.00</td><td>2.50</td><td>28.19</td>
                            </tr>
                            <tr>
                                <td>Shell-VQRF</td>
                                <td>1.37</td><td>3.65</td><td>31.81</td>
                                <td>1.23</td><td>4.07</td><td>34.67</td>
                                <td>1.41</td><td>3.54</td><td>28.21</td>
                            </tr>
                            <tr>
                                <td>TC-TensoRF-l</td>
                                <td>3.40</td><td>1.47</td><td>32.93</td>
                                <td>4.00</td><td>1.25</td><td>36.34</td>
                                <td>2.90</td><td>1.72</td><td>28.42</td>
                            </tr>
                            <tr>
                                <td>TC-TensoRF-h</td>
                                <td>1.60</td><td>3.13</td><td>32.31</td>
                                <td>1.60</td><td>3.13</td><td>35.33</td>
                                <td>1.60</td><td>3.13</td><td>28.08</td>
                            </tr>
                            <tr>
                                <td>Re-TensoRF-l</td>
                                <td>3.99</td><td>1.25</td><td>31.47</td>
                                <td>4.37</td><td>1.14</td><td>34.90</td>
                                <td>4.69</td><td>1.07</td><td>28.22</td>
                            </tr>
                            <tr>
                                <td>Re-TensoRF-h</td>
                                <td>2.00</td><td>2.50</td><td>31.08</td>
                                <td>2.46</td><td>2.03</td><td>34.90</td>
                                <td>1.62</td><td>3.09</td><td>27.90</td>
                            </tr>
                            <tr>
                                <td>SnapShot</td>
                                <td>0.16</td><td>31.25</td><td>28.74</td>
                                <td>0.16</td><td>31.25</td><td>31.94</td>
                                <td>0.16</td><td>31.25</td><td>25.24</td>
                            </tr>
                            <tr>
                                <td><b>Ours</b></td>
                                <td><b>0.04</b></td><td><b>125.00</b></td><td>30.06</td>
                                <td><b>0.04</b></td><td><b>125.00</b></td><td>33.76</td>
                                <td><b>0.04</b></td><td><b>125.00</b></td><td>26.44</td>
                            </tr>
                        </tbody>
                    </table>
                </div>
                <p class="text-justify" style="font-size: 13px;">
                    Quantitative comparisons on the NeRF-Synthetic, Synthetic-NSVF, and Tanks &amp; Temples datasets. We evaluate against conventional NeRF models and methods tailored for NeRF compression. Size is measured in MB.
                </p>
            </div>
        </div>

        <!-- Citation (hidden until accepted)
        <div class="row">
            <h2 class="text-center">Citation</h2>
            <div class="bibtex col-md-8 col-md-offset-2">
                <pre>@article{zhang2026magicnerf,
  title     = {MAGiC-NeRF: Multimodal Generative Priors and Conditional Flow for Extreme NeRF Compression},
  author    = {Zhang, Xiaoge and Wu, Zijie and Geng, Zichen and Anwar, Saeed and Mian, Ajmal},
  journal   = {IEEE Transactions on Circuits and Systems for Video Technology},
  year      = {2026}
}</pre>
            </div>
        </div>
        -->

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

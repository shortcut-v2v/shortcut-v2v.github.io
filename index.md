---
layout: project_page
permalink: /

title: 'Shortcut-V2V: Compression Framework for Video-to-Video Translation based on Temporal Redundancy Reduction'
authors:
    <a href="https://cychungg.github.io/">Chaeyeon Chung</a>*<sup>1</sup>, <a href="https://github.com/indigopyj">Yeojeong Park</a>*<sup>1,2</sup>, <a href="https://github.com/shadow2496">Seunghwan Choi</a><sup>1</sup>, <a href="https://github.com/misheeltoli">Munkhsoyol Ganbat</a><sup>1</sup>, <a href="https://sites.google.com/site/jaegulchoo/">Jaegul Choo</a><sup>1</sup>
affiliations:
    <sup>1</sup>KAIST AI, <sup>2</sup>KT Research & Development Center, KT Corporation
paper: https://arxiv.org/abs/2308.08011
code: https://github.com/indigopyj/Shortcut-V2V
---


<div class="columns is-centered has-text-centered">
    <div class="column is-four-fifths">
        <h2>Abstract</h2>
        <div class="content has-text-justified">
Video-to-video translation aims to generate video frames of a target domain from an input video.
Despite its usefulness, the existing video-to-video translation methods require enormous computations, necessitating their model compression for wide use.
While there exist compression methods that improve computational efficiency in various image/video tasks, a generally-applicable compression method for video-to-video translation has not been studied much.
In response, this paper presents <i>Shortcut-V2V</i>, a general-purpose compression framework for video-to-video translation.
Shortcut-V2V avoids full inference for every neighboring video frame by approximating the intermediate features of a current frame from those of the preceding frame.
Moreover, in our framework, a newly-proposed block called AdaBD adaptively blends and deforms features of neighboring frames, which makes more accurate predictions of the intermediate features possible.
We conduct quantitative and qualitative evaluations using well-known video-to-video translation models on various tasks to demonstrate the general applicability of our framework.
The results show that Shoutcut-V2V achieves comparable performance compared to the original video-to-video translation model while saving <b>3.2-5.7x</b> computational cost and <b>7.8-44x</b> memory at test time.
        </div>
    </div>
</div>

---

## Pipeline
In this paper, we propose Shortcut-V2V, a general compression framework to improve the test-time efficiency in video-to-video translation.
As illustrated in Figure 1.(a), given {<b>I</b><sub>t</sub>}<sup>N<sub>T</sub>-1</sup><sub>t=0</sub> as input video frames, we first use full teacher model T to synthesize the output of the first frame.
Then, for the next frames, our newly-proposed Shortcut block efficiently approximates <b>f</b><sub>t</sub>, the features from the l<sub>d</sub>-th decoding layer of the teacher model. 
This is achieved by leveraging the l<sub>e</sub>-th-th encoding layer features <b>a</b><sub>t</sub> along with reference features, <b>a</b><sub>ref</sub> and <b>f</b><sub>ref</sub>, from the previous frame. 
Here, l<sub>d</sub> and l<sub>e</sub> correspond to layer indices of the teacher model.
Lastly, predicted features <b>f&#770;</b><sub>t</sub> are injected into the following layers of the teacher model to synthesize the final output <b>O&#770;</b><sub>t</sub>.
To avoid error accumulation, we conduct full teacher inference and update the reference features at every max interval &alpha;.
![Turing Machine](/static/image/method_iccv.png)

*Figure 1. Overview of the proposed ShortCutV2V. (a) is an overall architecture of Shorcut-V2V, and (b) shows a detailed architecture of Shortcut block.*



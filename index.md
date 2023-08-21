---
layout: project_page
permalink: /

title: 'Shortcut-V2V: Compression Framework for Video-to-Video Translation based on Temporal Redundancy Reduction'
authors:
    Chaeyeon Chung*<sup>1</sup>, ![Yeojeong Park](https://github.com/indigopyj)*<sup>1,2</sup>, Seunghwan Choi<sup>1</sup>, Munkhsoyol Ganbat<sup>1</sup>, Jaegul Choo<sup>1</sup>
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
In response, this paper presents *Shortcut-V2V*, a general-purpose compression framework for video-to-video translation.
Shortcut-V2V avoids full inference for every neighboring video frame by approximating the intermediate features of a current frame from those of the preceding frame.
Moreover, in our framework, a newly-proposed block called AdaBD adaptively blends and deforms features of neighboring frames, which makes more accurate predictions of the intermediate features possible.
We conduct quantitative and qualitative evaluations using well-known video-to-video translation models on various tasks to demonstrate the general applicability of our framework.
The results show that Shoutcut-V2V achieves comparable performance compared to the original video-to-video translation model while saving <b>3.2-5.7x</b> computational cost and <b>7.8-44x</b> memory at test time.
        </div>
    </div>
</div>

---

## Pipeline
content from overview blah blah blah
![Turing Machine](/static/image/method_iccv.svg)

*Figure 1. Overview of the proposed ShortCutV2V. (a) is an overall architecture of Shorcut-V2V, and (b) shows a detailed architecture of Shortcut block.*



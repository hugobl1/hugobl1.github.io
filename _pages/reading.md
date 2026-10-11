---
layout: page
title: Reading lists
permalink: /reading/
description: Papers I have read, organized into thematic reading paths around my research interests.
nav: true
nav_order: 2.5
_styles: |
  .reading-figure {
    margin: 1.25rem 0;
  }
  .reading-figure img {
    display: block;
    width: auto;
    max-width: 100%;
    height: auto;
    background: white;
    border-radius: 4px;
  }
  .reading-figure figcaption {
    margin-top: 0.5rem;
    font-size: 0.85rem;
    color: var(--global-text-color-light);
  }
  .reading-category > summary {
    cursor: pointer;
    font-size: 1.75rem;
    font-weight: 500;
    margin: 1.5rem 0 1rem;
  }
  .reading-path > summary {
    cursor: pointer;
    font-size: 1.35rem;
    font-weight: 500;
    margin: 1rem 0;
  }
  .reading-category > summary:focus-visible,
  .reading-path > summary:focus-visible {
    outline: 2px solid var(--global-theme-color);
    outline-offset: 4px;
  }
  .reading-status {
    display: inline-block;
    padding: 0.2rem 0.65rem;
    border: 1px solid;
    border-radius: 999px;
    font-size: 0.8rem;
    font-weight: 600;
    vertical-align: middle;
  }
  .reading-status--read {
    color: #166534;
    background: #dcfce7;
    border-color: #86efac;
  }
  .reading-status--to-read {
    color: #854d0e;
    background: #fef3c7;
    border-color: #fcd34d;
  }
---

**Reading status:** <span class="reading-status reading-status--read">Read</span> already read · <span class="reading-status reading-status--to-read">To read</span> on my reading list.

<details class="reading-category" markdown="1">
<summary>Multi-view Stereo</summary>

Reading paths on recovering dense 3D geometry from multiple images.

<details class="reading-path" markdown="1">
<summary>PatchMatch: from image correspondence to multi-view stereo</summary>

This reading list follows the evolution of PatchMatch, from fast patch correspondence to dense stereo and multi-view 3D reconstruction. It connects efficient hypothesis propagation with the geometric constraints needed to recover scene structure.

**Suggested reading order:** PatchMatch → PatchMatch Stereo → ACMH / ACMM.

Start with the propagation and random search principles, then see how they extend to per-pixel plane hypotheses and, finally, multi-view consistency across scales.

---

#### 1. PatchMatch

<span class="reading-status reading-status--read">Read</span>

**Connelly Barnes, Eli Shechtman, Adam Finkelstein, and Dan B. Goldman · SIGGRAPH 2009**

_PatchMatch: A Randomized Correspondence Algorithm for Structural Image Editing._  
ACM Transactions on Graphics, 28(3), Article 24.

<figure class="reading-figure">
  <a href="https://pixl.cs.princeton.edu/gfx/pubs/Barnes_2009_PAR/patchmatch.pdf">
    <img src="{{ '/assets/img/reading/patchmatch-structural-editing.webp' | relative_url }}" width="893" height="139" loading="lazy" alt="Six temple images demonstrating hole filling, constrained retargeting and reshuffling with PatchMatch.">
  </a>
  <figcaption>Structural image editing. Figure 1 from Barnes et al. (2009). <a href="https://pixl.cs.princeton.edu/gfx/pubs/Barnes_2009_PAR/patchmatch.pdf">Source PDF</a>.</figcaption>
</figure>

**Contribution:** Fast approximate patch correspondence through propagation of neighboring matches and random search. The algorithm exploits spatial coherence to efficiently find useful matches for structural image editing.

**Reading focus:** Understand how propagation and random search complement each other—the foundation of the stereo methods below.

[Paper & PDF](https://pixl.cs.princeton.edu/gfx/pubs/Barnes_2009_PAR/index.php) · [DOI: 10.1145/1531326.1531330](https://doi.org/10.1145/1531326.1531330)

---

#### 2. PatchMatch Stereo

<span class="reading-status reading-status--read">Read</span>

**Michael Bleyer, Christoph Rhemann, and Carsten Rother · BMVC 2011**

_PatchMatch Stereo: Stereo Matching with Slanted Support Windows._  
British Machine Vision Conference, pp. 1–11.

<figure class="reading-figure">
  <a href="https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/PatchMatchStereo_BMVC2011_6MB.pdf">
    <img src="{{ '/assets/img/reading/patchmatch-stereo-slanted-windows.webp' | relative_url }}" width="790" height="183" loading="lazy" alt="Corridor scene comparing ground truth, fronto-parallel disparity estimates and reconstruction with slanted support windows.">
  </a>
  <figcaption>Slanted support windows improve reconstruction of inclined surfaces. Figure 2 from Bleyer et al. (2011). <a href="https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/PatchMatchStereo_BMVC2011_6MB.pdf">Source PDF</a>.</figcaption>
</figure>

**Contribution:** Dense disparity estimation by optimizing a 3D plane hypothesis at each pixel. Slanted support windows model surface orientation, while spatial and cross-view propagation transfer promising hypotheses.

**Reading focus:** Follow the shift from patch offsets to plane hypotheses, and how this reduces the fronto-parallel bias of conventional support windows.

[Paper](https://www.microsoft.com/en-us/research/publication/patchmatch-stereo-stereo-matching-with-slanted-support-windows/) · [PDF](https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/PatchMatchStereo_BMVC2011_6MB.pdf) · [DOI: 10.5244/C.25.14](https://doi.org/10.5244/C.25.14)

---

#### 3. ACMH / ACMM

<span class="reading-status reading-status--read">Read</span>

**Qingshan Xu and Wenbing Tao · CVPR 2019**

_Multi-Scale Geometric Consistency Guided Multi-View Stereo._  
IEEE/CVF Conference on Computer Vision and Pattern Recognition, pp. 5483–5492.

<figure class="reading-figure">
  <a href="https://openaccess.thecvf.com/content_CVPR_2019/papers/Xu_Multi-Scale_Geometric_Consistency_Guided_Multi-View_Stereo_CVPR_2019_paper.pdf">
    <img src="{{ '/assets/img/reading/acmm-checkerboard-propagation.webp' | relative_url }}" width="419" height="162" loading="lazy" alt="Three diagrams comparing sequential, symmetric checkerboard and adaptive checkerboard propagation.">
  </a>
  <figcaption>Sequential, symmetric checkerboard and adaptive checkerboard propagation. Figure 1 from Xu and Tao (2019). <a href="https://openaccess.thecvf.com/content_CVPR_2019/papers/Xu_Multi-Scale_Geometric_Consistency_Guided_Multi-View_Stereo_CVPR_2019_paper.pdf">Source PDF</a>.</figcaption>
</figure>

**Contribution:** PatchMatch-based multi-view stereo using adaptive checkerboard propagation and multi-hypothesis view selection (ACMH). ACMM extends this foundation with multi-scale geometric consistency to improve reconstruction in weakly textured regions.

**Reading focus:** Examine how view selection and geometric consistency make hypothesis propagation reliable across multiple images, and why coarse-to-fine reconstruction helps in regions with little texture.

[PDF](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xu_Multi-Scale_Geometric_Consistency_Guided_Multi-View_Stereo_CVPR_2019_paper.pdf) · [Code: ACMH](https://github.com/GhiXu/ACMH) · [Code: ACMM](https://github.com/GhiXu/ACMM)

</details>

</details>

<details class="reading-category" markdown="1">
<summary>Monte Carlo Rendering</summary>

Reading paths on sampling strategies and variance reduction for physically based rendering.

<details class="reading-path" markdown="1">
<summary>Multiple importance sampling</summary>

#### 1. Optimally Combining Sampling Techniques for Monte Carlo Rendering

<span class="reading-status reading-status--to-read">To read</span>

**Eric Veach and Leonidas J. Guibas · SIGGRAPH 1995**

_Optimally Combining Sampling Techniques for Monte Carlo Rendering._  
Proceedings of SIGGRAPH ’95, pp. 419–428.

<figure class="reading-figure">
  <a href="https://graphics.stanford.edu/papers/combine/">
    <img src="{{ '/assets/img/reading/veach-guibas-multiple-importance-sampling.jpg' | relative_url }}" width="500" height="458" loading="lazy" alt="Glossy surfaces illuminated by four differently sized area lights, rendered by combining light-source and BRDF samples.">
  </a>
  <figcaption>Glossy highlights using a weighted combination of light-source and BRDF samples with the power heuristic. Figure 2(c) from Veach and Guibas (1995). <a href="https://graphics.stanford.edu/papers/combine/">Source: authors’ project page</a>.</figcaption>
</figure>

**Contribution:** Introduces multiple importance sampling: weighted combinations of samples from several distributions produce unbiased Monte Carlo estimators with reduced variance, including applications to glossy lighting and bidirectional path tracing.

**Reading focus:** Understand how the balance and power heuristics combine complementary sampling strategies, and why combining light-source and BRDF sampling improves robustness.

[Paper & figures](https://graphics.stanford.edu/papers/combine/) · [DOI: 10.1145/218380.218498](https://doi.org/10.1145/218380.218498)

</details>

</details>

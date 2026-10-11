---
layout: page
title: Reading lists
permalink: /reading/
description: Papers I have read, organized into thematic reading paths around my research interests.
nav: true
nav_order: 2.5
_styles: |
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

## Multi-view Stereo

Reading paths on recovering dense 3D geometry from multiple images.

### PatchMatch: from image correspondence to multi-view stereo

This reading list follows the evolution of PatchMatch, from fast patch correspondence to dense stereo and multi-view 3D reconstruction. It connects efficient hypothesis propagation with the geometric constraints needed to recover scene structure.

**Suggested reading order:** PatchMatch → PatchMatch Stereo → ACMH / ACMM.

Start with the propagation and random search principles, then see how they extend to per-pixel plane hypotheses and, finally, multi-view consistency across scales.

---

#### 1. PatchMatch

<span class="reading-status reading-status--read">Read</span>

**Connelly Barnes, Eli Shechtman, Adam Finkelstein, and Dan B. Goldman · SIGGRAPH 2009**

_PatchMatch: A Randomized Correspondence Algorithm for Structural Image Editing._  
ACM Transactions on Graphics, 28(3), Article 24.

**Contribution:** Fast approximate patch correspondence through propagation of neighboring matches and random search. The algorithm exploits spatial coherence to efficiently find useful matches for structural image editing.

**Reading focus:** Understand how propagation and random search complement each other—the foundation of the stereo methods below.

[Paper & PDF](https://pixl.cs.princeton.edu/gfx/pubs/Barnes_2009_PAR/index.php) · [DOI: 10.1145/1531326.1531330](https://doi.org/10.1145/1531326.1531330)

---

#### 2. PatchMatch Stereo

<span class="reading-status reading-status--read">Read</span>

**Michael Bleyer, Christoph Rhemann, and Carsten Rother · BMVC 2011**

_PatchMatch Stereo: Stereo Matching with Slanted Support Windows._  
British Machine Vision Conference, pp. 1–11.

**Contribution:** Dense disparity estimation by optimizing a 3D plane hypothesis at each pixel. Slanted support windows model surface orientation, while spatial and cross-view propagation transfer promising hypotheses.

**Reading focus:** Follow the shift from patch offsets to plane hypotheses, and how this reduces the fronto-parallel bias of conventional support windows.

[Paper](https://www.microsoft.com/en-us/research/publication/patchmatch-stereo-stereo-matching-with-slanted-support-windows/) · [PDF](https://www.microsoft.com/en-us/research/wp-content/uploads/2011/01/PatchMatchStereo_BMVC2011_6MB.pdf) · [DOI: 10.5244/C.25.14](https://doi.org/10.5244/C.25.14)

---

#### 3. ACMH / ACMM

<span class="reading-status reading-status--read">Read</span>

**Qingshan Xu and Wenbing Tao · CVPR 2019**

_Multi-Scale Geometric Consistency Guided Multi-View Stereo._  
IEEE/CVF Conference on Computer Vision and Pattern Recognition, pp. 5483–5492.

**Contribution:** PatchMatch-based multi-view stereo using adaptive checkerboard propagation and multi-hypothesis view selection (ACMH). ACMM extends this foundation with multi-scale geometric consistency to improve reconstruction in weakly textured regions.

**Reading focus:** Examine how view selection and geometric consistency make hypothesis propagation reliable across multiple images, and why coarse-to-fine reconstruction helps in regions with little texture.

[PDF](https://openaccess.thecvf.com/content_CVPR_2019/papers/Xu_Multi-Scale_Geometric_Consistency_Guided_Multi-View_Stereo_CVPR_2019_paper.pdf) · [Code: ACMH](https://github.com/GhiXu/ACMH) · [Code: ACMM](https://github.com/GhiXu/ACMM)

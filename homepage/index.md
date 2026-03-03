---
layout: resume
title: "Resume Page"
---

## **Basis**

Currently, I'm a M.S. student in electronic engineering at [SIST](https://sist.shanghaitech.edu.cn/sist_en) from [ShanghaiTech Univ.](https://www.shanghaitech.edu.cn/eng/), supervised by His Excellency [Prof. Hao Geng](https://true-genghao.github.io/genghao/).

<!-- Research Interests Section -->
<div class="interests">
  <p>My research insterests include</p>
  <ul>
    <li>AI4Physics, AI4Optics, AI4Optimization</li>
    <li>Deep learning and optimization in Electronic Design Automation</li>
    <li>Design for manufacturing</li>
  </ul>
</div>

## **Publications**

<p class="publications-note">Representative publications in which I am the primary author are highlighted.</p>

<!-- ============================================
     Publications Data
     Format: ID|Authors|Title|Venue|IsPrimary|ProjectLink|PaperLink|CertificateLink
     ============================================ -->

{% assign primary_author_papers = "He, Hongquan|Hongquan He" | split: "|" %}
{% assign publications = site.data.publications | default: site.empty_array %}

{% assign papers = "
DAC-2026|**Hongquan He**, Ziyang Yu, Jiaqi Liu, Bei Yu, Jingyi Yu<sup>&dagger;</sup>, Hao Geng<sup>&dagger;</sup>|CPW-SMO: Generating Mask Sets and Common Source for Maximum Common Process Window|IEEE/ACM Proceedings Design Automation Conference (DAC), Long Beach, Jul. 26–29, 2026. (accepted)|true
NeurIPS-2025|**Hongquan He**, Zhen Wang, Jingya Wang, Tao Wu, Xuming He, Bei Yu, Jingyi Yu<sup>&dagger;</sup>, Hao Geng<sup>&dagger;</sup>|LithoSim: A Large, Holistic Lithography Simulation Benchmark for AI-Driven Semiconductor Manufacturing|Annular Conference on Neural Information Processing Systems (NeurIPS), San Diego, USA, Dec. 01-07, 2025.|true|https://dw-hongquan.github.io/LithoSim/|https://neurips.cc/virtual/2025/loc/san-diego/poster/121778
ICCAD-2025|Zhen Wang<sup>\*</sup>, **Hongquan He<sup>\*</sup>**, Tao Wu, Xuming He, Qi Sun, Cheng Zhuo, Bei Yu, Jingyi Yu<sup>&dagger;</sup>, Hao Geng<sup>&dagger;</sup>|LMLitho: A Large Vision Model-Driven Lithography Simulation Framework|IEEE/ACM International Conference on Computer-Aided Design (ICCAD), Munich, Oct. 26–30, 2025. (Best Paper Award Nomination)|true||https://ieeexplore.ieee.org/document/11240940/|/assets/img/homepage/ICCAD25-BPN.pdf
DAC-2025|Kai Ma, Zhen Wang, **Hongquan He**, Qi Xu, Tinghuan Chen, Hao Geng<sup>&dagger;</sup>|LMM-IR: Large-Scale Netlist-Aware Multi-modal Framework for Static IR-Drop Prediction|IEEE/ACM Design Automation Conference (DAC), San Francisco, Jun. 22–25, 2025.|false||https://ieeexplore.ieee.org/document/11133205
DAC-2024|Guojin Chen, **Hongquan He**, Peng Xu, Hao Geng, Bei Yu<sup>&dagger;</sup>|Efficient Bilevel Source Mask Optimization|IEEE/ACM Proceedings Design Automation Conference (DAC), San Francisco, Jun. 23–27, 2024.|false||https://dl.acm.org/doi/10.1145/3649329.3656252
DATE-2024|**Hongquan He**, Guowen Kuang, Qi Sun, Hao Geng<sup>&dagger;</sup>|PoLM: Point Cloud and Large Pre-trained Model Catch Mixed-type Wafer Defect Pattern Recognition|IEEE/ACM Proceedings Design, Automation and Test in Europe (DATE), Valencia, Spain, Mar. 25–27, 2024.|true||https://ieeexplore.ieee.org/document/10546714
" | split: "
" %}

<!-- Papers Grid -->
<div class="papers-grid">
  {% for paper in papers %}
    {% if paper != "" %}
      {% comment %} Parse paper data {% endcomment %}
      {% assign fields = paper | split: "|" %}
      {% assign paper_id = fields[0] %}
      {% assign authors = fields[1] %}
      {% assign title = fields[2] %}
      {% assign venue = fields[3] %}
      {% assign is_primary = fields[4] %}
      {% assign link = fields[5] | default: "" %}
      {% assign paper_link = fields[6] | default: "" %}
      {% assign cert_link = fields[7] | default: "" %}

      {% comment %} Extract conference name and year from ID {% endcomment %}
      {% assign conf_parts = paper_id | split: "-" %}
      {% assign conf_name = conf_parts[0] %}
      {% assign conf_year = conf_parts[1] | slice: 2, 2 %}

      {% comment %} Check if primary author {% endcomment %}
      {% assign is_primary_author = false %}
      {% if is_primary == "true" %}
        {% assign is_primary_author = true %}
      {% endif %}

      {% comment %} Render paper card {% endcomment %}
      <div class="paper-card {% if is_primary_author %}primary-author{% endif %}" id="paper-{{ paper_id }}">
        <!-- Badges -->
        <div class="paper-badge">
          <span class="badge-conf">{{ conf_name }}'{{ conf_year }}</span>
          {% if venue contains "Best Paper" %}
            <span class="badge-award">Best Paper Nomination</span>
          {% endif %}
        </div>

        <!-- Paper Details -->
        <h3 class="paper-title">{{ title }}</h3>
        <p class="paper-authors">{{ authors | markdownify | strip }}</p>
        <p class="paper-venue">{{ venue }}</p>

        <!-- Links -->
        <div class="paper-links">
          {% if link != "" %}
            <a href="{{ link }}" target="_blank" class="paper-link">
              <svg class="icon" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M18 10.5a6.5 6.5 0 1 0-13 0 6.5 6.5 0 0 0 13 0zm-6.5 8.5c1.5 0 2.9-.4 4.1-1.1l4.5 4.5 1.4-1.4-4.5-4.5c.7-1.2 1.1-2.6 1.1-4.1 0-4.1-3.4-7.5-7.5-7.5S4 6.4 4 10.5s3.4 7.5 7.5 7.5z"/>
              </svg>
              Project Page
            </a>
          {% endif %}
          {% if paper_link != "" %}
            <a href="{{ paper_link }}" target="_blank" class="paper-link">
              <svg class="icon" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-3 10h-8v-2h8v2z"/>
              </svg>
              Paper
            </a>
          {% endif %}
          {% if cert_link != "" %}
            <a href="{{ cert_link }}" target="_blank" class="paper-link">
              <svg class="icon" viewBox="0 0 24 24" width="16" height="16">
                <path fill="currentColor" d="M19 3H5c-1.1 0-2 .9-2 2v14c0 1.1.9 2 2 2h14c1.1 0 2-.9 2-2V5c0-1.1-.9-2-2-2zm-7 3c1.66 0 3 1.34 3 3s-1.34 3-3 3-3-1.34-3-3 1.34-3 3-3zm0 2c-.55 0-1 .45-1 1s.45 1 1 1 1-.45 1-1-.45-1-1-1zm6 10H6v-1c0-2 4-3.1 6-3.1s6 1.1 6 3.1v1z"/>
              </svg>
              Certificate
            </a>
          {% endif %}
        </div>
      </div>
    {% endif %}
  {% endfor %}
</div>

<!-- Footnote -->
<div class="paper-footer">
  <p class="footnote">
    <sup>*</sup>Equal contribution
    <span class="separator">•</span>
    <sup>&dagger;</sup>Corresponding author
  </p>
</div>

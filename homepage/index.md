---
layout: resume
title: "Resume Page"
---

## **Basis**

Currently, I'm a M.S. student in electronic engineering at [School of Information Science and Technology](https://sist.shanghaitech.edu.cn/sist_en/) from [ShanghaiTech Univ.](https://www.shanghaitech.edu.cn/eng/), supervised by His Excellency [Prof. Hao Geng](https://true-genghao.github.io/genghao/).

My research insterests include

*   AI4Physics, AI4Optics, AI4Optimization
*   Deep learning and optimization in Electronic Design Automation
*   Design for manufacturing

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>出版物 · 主要作者高亮</title>
    <style>
        /* 干净现代的风格，兼顾学术阅读体验 */
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

        body {
            font-family: 'Inter', -apple-system, BlinkMacSystemFont, 'Segoe UI', Roboto, Helvetica, Arial, sans-serif;
            background: #f5f7fb;
            display: flex;
            flex-direction: column;
            align-items: center;
            justify-content: center;
            min-height: 100vh;
            padding: 2rem 1rem;
            line-height: 1.5;
            color: #1e293b;
        }

        .publications-container {
            max-width: 900px;
            width: 100%;
            margin: 0 auto;
        }

        /* 标题 */
        .section-title {
            font-size: 2rem;
            font-weight: 600;
            letter-spacing: -0.02em;
            margin-bottom: 2rem;
            border-bottom: 2px solid #e2e8f0;
            padding-bottom: 0.75rem;
            color: #0f172a;
        }

        .section-title span {
            background: #dbeafe;
            color: #1e40af;
            font-size: 0.9rem;
            font-weight: 500;
            padding: 0.25rem 1rem;
            border-radius: 30px;
            margin-left: 1rem;
            vertical-align: middle;
        }

        /* 每一个paper都是一个block——卡片样式 */
        .paper-block {
            background: #ffffff;
            border-radius: 24px;
            padding: 1.75rem 2rem;
            margin-bottom: 1.5rem;
            box-shadow: 0 8px 20px rgba(0,0,0,0.02), 0 2px 6px rgba(0,20,40,0.05);
            transition: all 0.2s ease;
            border: 1px solid #edf2f7;
        }

        /* 高亮区块：代表主要作者 (primary author) 的论文 */
        .paper-block.primary-highlight {
            background: #eef6ff;      /* 柔和蓝色基底，象征高亮 */
            border-left: 6px solid #2563eb;
            box-shadow: 0 12px 24px -8px rgba(37, 99, 235, 0.15);
            border-top: 1px solid #b9d3f8;
            border-right: 1px solid #b9d3f8;
            border-bottom: 1px solid #b9d3f8;
            border-radius: 20px 24px 24px 20px;
        }

        /* 作者行 */
        .paper-authors {
            font-size: 1rem;
            margin-bottom: 0.5rem;
            display: flex;
            flex-wrap: wrap;
            align-items: baseline;
        }

        .author {
            display: inline-block;
            margin-right: 0.4rem;
            white-space: nowrap;
        }

        .author-highlight {
            font-weight: 600;
            color: #0f3b7a;
            background: #dbeafe70;
            padding: 0.1rem 0.3rem;
            border-radius: 6px;
        }

        .equal-contrib {
            font-size: 0.85rem;
            background: #f1f5f9;
            color: #475569;
            padding: 0.2rem 0.6rem;
            border-radius: 30px;
            display: inline-block;
            margin-left: 0.5rem;
            vertical-align: middle;
            font-weight: 400;
        }

        .corr-mark {
            font-size: 0.85rem;
            color: #4b5563;
            background: #f3f4f6;
            padding: 0.1rem 0.5rem;
            border-radius: 12px;
            margin-left: 0.3rem;
            white-space: nowrap;
        }

        /* 论文标题 + 额外标记 */
        .paper-title {
            font-weight: 650;
            font-size: 1.2rem;
            margin: 0.6rem 0 0.4rem 0;
            color: #0a2540;
            line-height: 1.4;
        }

        /* 会议/期刊信息 */
        .paper-venue {
            font-size: 0.98rem;
            color: #2d3a4f;
            background: #f8fafc;
            padding: 0.3rem 0.8rem;
            border-radius: 30px;
            display: inline-block;
            margin: 0.6rem 0 0.5rem 0;
            border: 1px solid #e9eef3;
            font-weight: 450;
        }

        .paper-extra {
            font-size: 0.95rem;
            color: #4a5a72;
            margin: 0.5rem 0 0.2rem 0;
        }

        /* 链接和标记 */
        .paper-links {
            margin-top: 0.8rem;
            display: flex;
            flex-wrap: wrap;
            gap: 1.2rem;
            align-items: center;
        }

        .paper-links a {
            text-decoration: none;
            background: #f1f5f9;
            color: #1e3a8a;
            padding: 0.3rem 1rem;
            border-radius: 40px;
            font-size: 0.9rem;
            font-weight: 500;
            border: 1px solid #cfdfef;
            transition: 0.1s ease;
            display: inline-flex;
            align-items: center;
        }

        .paper-links a:hover {
            background: #e0e9f5;
            border-color: #9bb9dd;
            color: #0b2a5e;
        }

        .badge {
            background: #e6b91e10;
            border: 1px solid #fbbf24;
            color: #b45309;
            font-size: 0.8rem;
            padding: 0.15rem 0.9rem;
            border-radius: 30px;
            font-weight: 550;
            letter-spacing: 0.01em;
        }

        .badge-accepted {
            background: #dcfce7;
            border-color: #86efac;
            color: #166534;
        }

        .spacer {
            flex: 1;
        }

        /* 脚注样式 */
        .footnote {
            margin-top: 2rem;
            font-size: 0.9rem;
            color: #4b5563;
            background: #f1f4f9;
            padding: 1rem 1.5rem;
            border-radius: 60px;
            display: inline-block;
        }

        hr {
            border: none;
            border-top: 1px dashed #d1d9e6;
            margin: 0.5rem 0 1.5rem 0;
        }

        /* 响应式 */
        @media (max-width: 600px) {
            .paper-block {
                padding: 1.5rem 1.2rem;
            }
            .paper-title {
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <div class="publications-container">
        <div class="section-title">
            📄  Selected Publications
            <span>primary author highlighted</span>
        </div>

        <!-- 论文区块列表，遵循原始顺序，并根据第一作者是否为 Hongquan He 添加高亮 class "primary-highlight" 
             并且注意 * 标记 primary author 我自己 (Hongquan He) 作为第一作者且没有*标记共一的也算； 
             但第三条 Zhen Wang 和 Hongquan He 共一 (*) —— 按照要求 "Representative publications that I am a primary author on are highlighted"
             所以只要是第一作者或者共一作者(*) 都属于主要作者，应当高亮。 第一条、第二条、第三条、第六条都是本人主要作者。
             第四条(Kai Ma) 本人不是一作/共一, 不亮；第五条(Guojin Chen) 本人二作，但非一作/共一, 不高亮。
        -->

        <!-- 1. DAC 2026 (Hongquan He 一作) -->
        <div class="paper-block primary-highlight">
            <div class="paper-authors">
                <span class="author author-highlight"><strong>Hongquan He</strong></span>, <span class="author">Ziyang Yu</span>, <span class="author">Jiaqi Liu</span>, <span class="author">Bei Yu</span>, <span class="author">Jingyi Yu<sup>&dagger;</sup></span>, <span class="author">Hao Geng<sup>&dagger;</sup></span>
                <span class="corr-mark"><sup>&dagger;</sup>corresponding</span>
            </div>
            <div class="paper-title">
                CPW-SMO: Generating Mask Sets and Common Source for Maximum Common Process Window
            </div>
            <div class="paper-venue">
                <em>IEEE/ACM Proceedings Design Automation Conference (DAC)</em>, Long Beach, Jul. 26–29, 2026. (accepted)
            </div>
            <div class="paper-extra">
                <span class="badge badge-accepted">accepted</span>
            </div>
            <!-- 无链接，所以留空 -->
        </div>

        <!-- 2. NeurIPS 2025 (Hongquan He 一作) -->
        <div class="paper-block primary-highlight">
            <div class="paper-authors">
                <span class="author author-highlight"><strong>Hongquan He</strong></span>, <span class="author">Zhen Wang</span>, <span class="author">Jingya Wang</span>, <span class="author">Tao Wu</span>, <span class="author">Xuming He</span>, <span class="author">Bei Yu</span>, <span class="author">Jingyi Yu<sup>&dagger;</sup></span>, <span class="author">Hao Geng<sup>&dagger;</sup></span>
                <span class="corr-mark"><sup>&dagger;</sup>corresponding</span>
            </div>
            <div class="paper-title">
                LithoSim: A Large, Holistic Lithography Simulation Benchmark for AI-Driven Semiconductor Manufacturing
            </div>
            <div class="paper-venue">
                <em>Annular Conference on Neural Information Processing Systems (NeurIPS)</em>, San Diego, USA, Dec. 01-07, 2025.
            </div>
            <div class="paper-links">
                <a href="https://dw-hongquan.github.io/LithoSim/" target="_blank">🌐  Project Page</a>
                <a href="https://neurips.cc/virtual/2025/loc/san-diego/poster/121778" target="_blank">📝  Paper</a>
            </div>
        </div>

        <!-- 3. ICCAD 2025 (Zhen Wang 与 Hongquan He 共一，用*标记) 主要作者高亮 -->
        <div class="paper-block primary-highlight">
            <div class="paper-authors">
                <span class="author">Zhen Wang<sup>*</sup></span>, <span class="author author-highlight"><strong>Hongquan He<sup>*</sup></strong></span>, <span class="author">Tao Wu</span>, <span class="author">Xuming He</span>, <span class="author">Qi Sun</span>, <span class="author">Cheng Zhuo</span>, <span class="author">Bei Yu</span>, <span class="author">Jingyi Yu<sup>&dagger;</sup></span>, <span class="author">Hao Geng<sup>&dagger;</sup></span>
                <span class="equal-contrib">*Equal contribution</span>
                <span class="corr-mark"><sup>&dagger;</sup>corresponding</span>
            </div>
            <div class="paper-title">
                LMLitho: A Large Vision Model-Driven Lithography Simulation Framework
            </div>
            <div class="paper-venue">
                <em>IEEE/ACM International Conference on Computer-Aided Design (ICCAD)</em>, Munich, Oct. 26–30, 2025. (Best Paper Award Nomination)
            </div>
            <div class="paper-extra">
                <span class="badge" style="background:#fef3c7; color:#92400e; border-color:#fbbf24;">🏆 Best Paper Nomination</span>
            </div>
            <div class="paper-links">
                <a href="https://ieeexplore.ieee.org/document/11240940/" target="_blank">📄  IEEE Xplore</a>
            </div>
        </div>

        <!-- 4. DAC 2025 (Kai Ma 一作，本人四作) 不高亮 -->
        <div class="paper-block">
            <div class="paper-authors">
                <span class="author">Kai Ma</span>, <span class="author">Zhen Wang</span>, <span class="author">Hongquan He</span>, <span class="author">Qi Xu</span>, <span class="author">Tinghuan Chen</span>, <span class="author">Hao Geng<sup>&dagger;</sup></span>
                <span class="corr-mark"><sup>&dagger;</sup>corresponding</span>
            </div>
            <div class="paper-title">
                LMM-IR: Large-Scale Netlist-Aware Multi-modal Framework for Static IR-Drop Prediction
            </div>
            <div class="paper-venue">
                <em>IEEE/ACM Design Automation Conference (DAC)</em>, San Francisco, Jun. 22–25, 2025.
            </div>
            <div class="paper-links">
                <a href="https://ieeexplore.ieee.org/document/11133205" target="_blank">📄  IEEE Xplore</a>
            </div>
        </div>

        <!-- 5. DAC 2024 (Guojin Chen 一作，本人二作) 不是主要作者，不高亮 -->
        <div class="paper-block">
            <div class="paper-authors">
                <span class="author">Guojin Chen</span>, <span class="author">Hongquan He</span>, <span class="author">Peng Xu</span>, <span class="author">Hao Geng</span>, <span class="author">Bei Yu<sup>&dagger;</sup></span>
                <span class="corr-mark"><sup>&dagger;</sup>corresponding</span>
            </div>
            <div class="paper-title">
                Efficient Bilevel Source Mask Optimization
            </div>
            <div class="paper-venue">
                <em>IEEE/ACM Proceedings Design Automation Conference (DAC)</em>, San Francisco, Jun. 23–27, 2024.
            </div>
            <div class="paper-links">
                <a href="https://dl.acm.org/doi/10.1145/3649329.3656252" target="_blank">📄  ACM DL</a>
            </div>
        </div>

        <!-- 6. DATE 2024 (Hongquan He 一作) 高亮 -->
        <div class="paper-block primary-highlight">
            <div class="paper-authors">
                <span class="author author-highlight"><strong>Hongquan He</strong></span>, <span class="author">Guowen Kuang</span>, <span class="author">Qi Sun</span>, <span class="author">Hao Geng<sup>&dagger;</sup></span>
                <span class="corr-mark"><sup>&dagger;</sup>corresponding</span>
            </div>
            <div class="paper-title">
                PoLM: Point Cloud and Large Pre-trained Model Catch Mixed-type Wafer Defect Pattern Recognition
            </div>
            <div class="paper-venue">
                <em>IEEE/ACM Proceedings Design, Automation and Test in Europe (DATE)</em>, Valencia, Spain, Mar. 25–27, 2024.
            </div>
            <div class="paper-links">
                <a href="https://ieeexplore.ieee.org/document/10546714" target="_blank">📄  IEEE Xplore</a>
            </div>
        </div>

        <!-- 等贡献与通讯说明行 (已经内嵌在各卡片里，但为了完整，额外加一个注释区) -->
        <hr>
        <div style="display: flex; flex-wrap: wrap; gap: 2rem; align-items: center; justify-content: space-between;">
            <div style="display: flex; gap: 2rem; flex-wrap: wrap;">
                <div><small><sup>*</sup> Equal contribution</small></div>
                <div><small><sup>&dagger;</sup> Corresponding author</small></div>
            </div>
            <div class="footnote">
                ⭐ 蓝色高亮区块代表本人 (Hongquan He) 作为主要作者 (一作/共一) 的论文
            </div>
        </div>
    </div>
</body>
</html>

<!-- ## **Publications**

*   **Hongquan He**, Ziyang Yu, Jiaqi Liu, Bei Yu, Jingyi Yu<sup>&dagger;</sup>, Hao Geng<sup>&dagger;</sup>.  
    CPW-SMO: Generating Mask Sets and Common Source for Maximum Common Process Window.
    *IEEE/ACM Proceedings Design Automation Conference (DAC)*, Long Beach, Jul. 26–29, 2026. (accepted)

*   **Hongquan He**, Zhen Wang, Jingya Wang, Tao Wu, Xuming He, Bei Yu, Jingyi Yu<sup>&dagger;</sup>, Hao Geng<sup>&dagger;</sup>.
    LithoSim: A Large, Holistic Lithography Simulation Benchmark for AI-Driven Semiconductor Manufacturing.
    *Annular Conference on Neural Information Processing Systems (NeurIPS)*, San Diego, USA, Dec. 01-07, 2025. [[Link]](https://dw-hongquan.github.io/LithoSim/) [[Paper]](https://neurips.cc/virtual/2025/loc/san-diego/poster/121778)

*   Zhen Wang<sup>\*</sup>, **Hongquan He<sup>\*</sup>**, Tao Wu, Xuming He, Qi Sun, Cheng Zhuo, Bei Yu, Jingyi Yu<sup>&dagger;</sup>, Hao Geng<sup>&dagger;</sup>.  
    LMLitho: A Large Vision Model-Driven Lithography Simulation Framework.
    *IEEE/ACM International Conference on Computer-Aided Design (ICCAD)*, Munich, Oct. 26–30, 2025. (Best Paper Award Nomination) [[Paper]](https://ieeexplore.ieee.org/document/11240940/)

*   Kai Ma, Zhen Wang, **Hongquan He**, Qi Xu, Tinghuan Chen, Hao Geng<sup>&dagger;</sup>.  
    LMM-IR: Large-Scale Netlist-Aware Multi-modal Framework for Static IR-Drop Prediction.
    *IEEE/ACM Design Automation Conference (DAC)*, San Francisco, Jun. 22–25, 2025. [[Paper]](https://ieeexplore.ieee.org/document/11133205)

*   Guojin Chen, **Hongquan He**, Peng Xu, Hao Geng, Bei Yu<sup>&dagger;</sup>.  
    Effcient Bilevel Source Mask Optimization.
    *IEEE/ACM Proceedings Design Automation Conference (DAC)*, San Francisco, Jun. 23–27, 2024. [[Paper]](https://dl.acm.org/doi/10.1145/3649329.3656252)

*   **Hongquan He**, Guowen Kuang, Qi Sun, Hao Geng<sup>&dagger;</sup>.  
    PoLM: Point Cloud and Large Pre-trained Model Catch Mixed-type Wafer Defect Pattern Recognition.
    *IEEE/ACM Proceedings Design, Automation and Test in Europe (DATE)*, Valencia, Spain, Mar. 25–27, 2024. [[Paper]](https://ieeexplore.ieee.org/document/10546714)

<sup>\*</sup>Equal contribution  
<sup>&dagger;</sup>Corresponding author. -->

## **Simplified Design Pipeline**

                        ┌──────────────────────────┐
                        │     EDA Design Flow      │
                        └──────────────────────────┘
                                     │
                                     ▼
                       ┌─────────────────────────┐
                       │     Schematic Design    │
                       │  (Circuit Entry & Setup)│
                       └─────────────────────────┘
                                     │
                                     ▼
                       ┌─────────────────────────┐
                       │   Pre-layout Simulation │
                       │    (Functional / DC /   │
                       │      Transient / AC)    │
                       └─────────────────────────┘
                                     │
                                     ▼
                            ┌───────────────┐
                            │   Meet Spec?  │◄─────────────┐
                            └───────────────┘              │
                                     │ No                  │
                                 Yes │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │    Layout Generation    │         │
                       │   (Place & Route /      │         │
                       │    Manual Drawing)      │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │   Design Rule Checking  │         │
                       │         (DRC)           │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                            ┌───────────────┐              │
                            │   DRC Clean?  │◄─────────────┐
                            └───────────────┘              │
                                     │ No                  │
                                 Yes │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │  Layout vs. Schematic   │         │
                       │         (LVS)           │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                            ┌───────────────┐              │
                            │   LVS Match?  │◄─────────────┐
                            └───────────────┘              │
                                     │ No                  │
                                 Yes │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │   Critical Pattern      │         │
                       │     Selection &         │         │
                       │   Hotspot Detection     │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │ Source-Mask Optimization│         │
                       │        (SMO)            │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │  Optical Proximity      │         │
                       │  Correction (OPC)       │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │  Post-OPC Verification  │         │
                       │  (ORC / LRC / DRC+)     │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                            ┌───────────────┐              │
                            │    OPC Clean? │◄─────────────┐
                            └───────────────┘              │
                                     │ No                  │
                                 Yes │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │ Parasitic Extraction    │         │
                       │  (PEX / RCX) with       │         │
                       │  Post-OPC Geometry      │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                       ┌─────────────────────────┐         │
                       │  Post-layout Simulation │         │
                       │   (with Parasitics)     │         │
                       └─────────────────────────┘         │
                                     │                     │
                                     ▼                     │
                            ┌───────────────┐              │
                            │   Meet Spec?  │──────────────┘
                            └───────────────┘
                                     │ Yes
                                     ▼
                       ┌─────────────────────────┐
                       │   Tape-out / GDSII      │
                       │   (Mask Data Prep &     │
                       │     Manufacturing)      │
                       └─────────────────────────┘
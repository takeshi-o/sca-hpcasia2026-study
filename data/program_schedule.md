# SCA/HPCAsia 2026 プログラム詳細

> **注意**: プログラムは頻繁に更新されます。日程、時間、会場情報は変更される場合があります。

---

# 1月27日（火）January 27, 2026

## タイムスケジュール

| 時間 | 内容 | 発表者/担当者 |
|------|------|---------------|
| 09:00 - 09:30 | Opening Session | - |
| 09:30 - 17:00 | Exhibition | 3F Event Hall |
| 09:30 - 10:15 | Keynote: Ultra Ethernet for next-generation AI and HPC workloads | Torsten Hoefler (ETH Zurich) |
| 10:15 - 11:00 | Keynote: Toward High Performance Quantum Computing: From NISQ to FTQC | Keisuke Fujii (Osaka University) |
| 11:30 - 12:30 | Invited Session: Analyst Crossfire | Addison Snell (Intersect360 Research) |
| 11:30 - 12:30 | Invited Session: Architecting the future of AI infrastructure | Eric Van Hensbergen (Arm) |
| 11:30 - 17:00 | Invited Session: Vision and Strategy | Taisuke Boku, Andrew Rohl |
| 11:30 - 17:00 | Invited Session: HPC For Large-Scale Weather Prediction and Climate Modelling | Dale Barker, Shigenori Otsuka |
| 11:30 - 17:00 | Invited Session: AI-Powered Pandemic Preparedness | Arvind Ramanathan, Newton Wahome |
| 11:30 - 17:00 | Co-located Event: Trillion Parameter Consortium (TPC) | Rio Yokota, Charlie Catlett |
| 11:30 - 17:00 | Co-located Event: HANAMI | Kengo Nakajima, France Boillod-Cerneux |
| 11:30 - 12:30 | Paper Track 1: Quantum Simulation & Kernels | - |
| 11:30 - 12:30 | Paper Track 2: Using AI in HPC | - |
| 12:30 - 13:30 | Lunch Speaker Sessions | 各社スポンサー |
| 13:30 - 15:00 | Paper Track 3: Quantum Software & Tooling | - |
| 13:30 - 15:00 | Paper Track 4: Linear Algebra & Tensor-Core Techniques I | - |
| 13:30 - 17:00 | Invited Session: Connecting Global HPC Infrastructure with Grassroots Innovation | Worawan Diaz Carballo, Fabrizio Gagliardi |
| 13:30 - 17:00 | Invited Session: Hybrid Quantum–Classical HPC in Practice | Tommaso Macrì, Ayumu Imai |
| 13:30 - 17:00 | Invited Session: Converging Quantum and AI | Tatsuhiro Chiba, Hiroshi Horii |
| 13:30 - 17:00 | Invited Session: Ethernet for HPC/AI clusters | Mohan Kalkunte (Broadcom) |
| 13:30 - 17:00 | Poster Session | - |
| 15:30 - 17:00 | Paper Track 5: Quantum Algorithms & Data Access | - |
| 15:30 - 17:00 | Paper Track 6: Linear Algebra & Tensor-Core Techniques II | - |
| 15:30 - 18:00 | BoF: Slurm + Slinky for the AI and Supercomputer meeting | Howard Weiss, Brian Christiansen |
| 16:30 - 18:30 | BoF: Open OnDemand User Group Meeting | Julie Ma |
| 17:00 - 18:00 | Birds of a Feather Sessions (複数) | 各セッション担当者 |

---

## 基調講演 / Keynote Speeches

### Keynote 1: Ultra Ethernet for next-generation AI and HPC workloads

**時間**: 09:30 - 10:15
**会場**: 5F Main Hall

**発表者**: Torsten Hoefler
**所属**: Professor, ETH Zurich, Switzerland

**経歴 (Biography)**:

Torsten Hoefler is a Professor of Computer Science at ETH Zurich, a member of Academia Europaea, and a Fellow of the ACM, IEEE, and ELLIS. He received the 2024 ACM Prize in Computing, one of the highest honors in the field. Following a Performance as a Science vision, he combines mathematical models of architectures and applications to design optimized computing systems. Before joining ETH Zurich, he led the performance modeling and simulation efforts for the first sustained Petascale supercomputer, Blue Waters, at the University of Illinois at Urbana-Champaign. He is also a key contributor to the Message Passing Interface (MPI) standard where he chaired the "Collective Operations and Topologies" working group. Torsten won best paper awards at his field's top conference ACM/IEEE Supercomputing in 2010, 2013, 2014, 2019, 2022, 2023, 2024, and at other international conferences. He has published numerous peer-reviewed scientific articles and authored chapters of the MPI-2.2 and MPI-3.0 standards. For his work, Torsten received the IEEE CS Sidney Fernbach Memorial Award in 2022, the ACM Gordon Bell Prize in 2019, Germany's Max Planck-Humboldt Medal, the ISC Jack Dongarra award, the IEEE TCSC Award of Excellence (MCR), ETH Zurich's Latsis Prize, the SIAM SIAG/Supercomputing Junior Scientist Prize, the IEEE TCSC Young Achievers in Scalable Computing Award, and the BenchCouncil Rising Star Award. Following his Ph.D., he received the 2014 Young Alumni Award and the 2022 Distinguished Alumni Award of his alma mater, Indiana University. Torsten was elected to the first steering committee of ACM's SIGHPC in 2013 and he was re-elected for every term since then. He was the first European to receive many of those honors; he also received both an ERC Starting and Consolidator grant. His research interests revolve around the central topic of performance-centric system design and include scalable networks, parallel programming techniques, and performance modeling for large-scale simulations and artificial intelligence systems. Additional information about Torsten can be found on his homepage at htor.inf.ethz.ch.

**発表内容 (Abstract) - 英語**:

The Ultra Ethernet Consortium set out to redefine Ethernet-based interconnects for AI and high-performance computing (HPC), culminating in the recent release of its first specification (version 1.0). This talk will analyze HPC and AI workloads with respect to their networking requirements. We will then highlight key innovations that distinguish Ultra Ethernet from existing solutions, ranging from lossy operation—both with and without trimming—to fully hardware-offloaded rendezvous protocols. We will explore the architectural advancements and technical highlights that enhance efficiency, scalability, and performance, positioning Ultra Ethernet as a transformative force in next-generation computing.

**発表内容（日本語）**:

Ultra Ethernetコンソーシアムは、AIおよびハイパフォーマンスコンピューティング（HPC）向けのEthernetベースのインターコネクトを再定義することを目指し、最近その最初の仕様（バージョン1.0）をリリースしました。本講演では、HPCおよびAIワークロードをネットワーキング要件の観点から分析します。そして、ロッシー動作（トリミングあり・なし両方）から完全にハードウェアオフロードされたランデブープロトコルに至るまで、Ultra Ethernetを既存のソリューションと区別する主要なイノベーションを紹介します。効率性、スケーラビリティ、パフォーマンスを向上させるアーキテクチャの進歩と技術的なハイライトを探り、Ultra Ethernetが次世代コンピューティングにおける変革的な力となることを示します。

---

### Keynote 2: Toward High Performance Quantum Computing: From NISQ to FTQC

**時間**: 10:15 - 11:00
**会場**: 5F Main Hall

**発表者**: Keisuke Fujii（藤井啓祐）
**所属**: Distinguished Professor, Graduate School of Engineering Science, Osaka University

**経歴 (Biography)**:

Keisuke Fujii is a Distinguished Professor at the Graduate School of Engineering Science, Osaka University, where he also serves as Deputy Director of the Center for Quantum Information and Quantum Biology (QIQB). He concurrently leads a research team at the RIKEN Center for Quantum Computing and acts as Chief Technical Advisor at QunaSys Inc., a leading quantum computing software start-up in Japan. He received his Ph.D. in Engineering from Kyoto University in 2011, and has held academic positions at the University of Tokyo and Kyoto University before joining Osaka University in 2019.

Professor Fujii's research spans a broad spectrum of quantum information science, with a primary focus on the theory of fault-tolerant quantum computation, quantum error correction, quantum algorithms. His achievements have been recognized with the NISTEP Award (2020), the JSPS Prize (2022), and the Osaka University Distinguished Professor title (2022).

**発表内容 (Abstract) - 英語**:

The past decade has witnessed remarkable progress in the development of quantum computers, culminating in the current era of noisy intermediate-scale quantum (NISQ) devices. While NISQ hardware has enabled first demonstrations of quantum advantage in carefully chosen tasks, its limited qubit number and error rates severely restrict practical applications. Bridging the gap toward fault-tolerant quantum computing (FTQC) requires both architectural innovation and resource-efficient error correction strategies. In this talk, I will provide an overview of the state of the art, highlighting how recent advances in algorithms, quantum error correction, and partially fault-tolerant architectures can pave the way for scalable computation. I will discuss how algorithm design and resource estimation are evolving hand in hand with hardware progress, shaping a roadmap from proof-of-principle demonstrations to early fault-tolerant applications. Special emphasis will be placed on the notion of "early FTQC," which seeks to exploit partial fault tolerance to reduce overhead while delivering meaningful computational power. By connecting theoretical advances with experimental milestones, I aim to illustrate how high-performance quantum computing may emerge in the future and outline the key challenges and opportunities that lie ahead on the path from NISQ to FTQC.

**発表内容（日本語）**:

過去10年間、量子コンピュータの開発において目覚ましい進歩が見られ、現在のノイズのある中規模量子（NISQ）デバイスの時代に至りました。NISQハードウェアは慎重に選ばれたタスクにおいて量子優位性の最初の実証を可能にしましたが、限られた量子ビット数とエラー率が実用的なアプリケーションを大幅に制限しています。フォールトトレラント量子コンピューティング（FTQC）へのギャップを埋めるには、アーキテクチャの革新とリソース効率の良いエラー訂正戦略の両方が必要です。本講演では、最先端の状況を概観し、アルゴリズム、量子エラー訂正、部分的にフォールトトレラントなアーキテクチャにおける最近の進歩がスケーラブルな計算への道をどのように切り開くかを紹介します。アルゴリズム設計とリソース推定がハードウェアの進歩とともにどのように進化しているか、原理実証から初期のフォールトトレラントアプリケーションへのロードマップを形成しているかについて議論します。特に「初期FTQC」の概念に重点を置き、部分的なフォールトトレランスを活用してオーバーヘッドを削減しながら有意義な計算能力を提供することを目指します。理論的進歩と実験的マイルストーンを結びつけることで、高性能量子コンピューティングが将来どのように出現するかを示し、NISQからFTQCへの道のりにおける主要な課題と機会を概説します。

---

## Invited Sessions

### Analyst Crossfire

**時間**: 11:30 - 12:30

**発表者**: Addison Snell
**所属**: Intersect360 Research

**発表内容 (Abstract) - 英語**:

In this fast-paced panel format, Addison Snell invites four panelists – two from HPC and AI-using sites (ideally one lab, one industrial) and to from the vendor community (possibly SCA / HPC Asia sponsors) to play the role of the industry analyst by responding to forward-looking questions about the direction of the industry. The panel will address seven topics in 45 minutes. The audience will see the topic list and questions for the panelist on slides, with a timer, and the slides will auto-advance as the timer expires.

**発表内容（日本語）**:

このテンポの速いパネル形式では、Addison Snellが4名のパネリストを招待します。2名はHPCおよびAI利用サイトから（理想的には1つの研究機関と1つの産業界から）、2名はベンダーコミュニティから（おそらくSCA / HPC Asiaのスポンサー）、業界アナリストの役割を果たし、業界の方向性に関する将来志向の質問に回答します。パネルは45分間で7つのトピックを扱います。聴衆はスライド上でトピックリストとパネリストへの質問をタイマーとともに見ることができ、タイマーが切れるとスライドは自動的に進みます。

---

### Architecting the future of AI infrastructure

**時間**: 11:30 - 12:30

**発表者**: Eric Van Hensbergen
**所属**: Arm

**パネリスト**:
- Eric Van Hensbergen (Arm)
- Satoshi Matsuoka (RIKEN)
- Jay Boisseau (Google HPC)
- Jason Haga (AIST)
- Dan Ernst (Nvidia)
- Jennifer Glore (Rebellions)

**発表内容 (Abstract) - 英語**:

The exponential growth in compute demand from AI workloads has led to increasingly challenging infrastructure requirements. This panel brings together industry leaders to discuss how AI accelerators, compute racks, and AI clusters are evolving to address these requirements. In this panel session, panelists will highlight how future innovations in compute, accelerators, networking, optics, and cooling can enable greater compute capacity, efficiency, and performance at scale.

**発表内容（日本語）**:

AIワークロードからの計算需要の指数関数的な成長により、インフラストラクチャ要件はますます困難になっています。このパネルでは、業界のリーダーが集まり、AIアクセラレータ、計算ラック、AIクラスタがこれらの要件に対応するためにどのように進化しているかを議論します。このパネルセッションでは、パネリストが計算、アクセラレータ、ネットワーキング、光学、冷却における将来のイノベーションがスケールでの計算能力、効率性、パフォーマンスの向上をどのように可能にするかを強調します。

---

### Vision and Strategy: How will supercomputing centers contribute to the future development of HPC/AI+?

**時間**: 11:30 - 17:00（1/27）、11:00 - 17:00（1/28）

**発表者**:
- Taisuke Boku（朴泰祐）, University of Tsukuba
- Andrew Rohl, National Computational Infrastructure (NCI), Australian National University

**スピーカー一覧**:
- Andrew Rohl, NCI
- Satoshi Matsuoka, R-CCS
- Terence Hung, NSCC
- Chan-Yeol Park, KISTI
- Weicheng Huang, NCHC
- Bernd Mohr, JSC
- Takeshi Fukaya, Hokkaido University
- Hiroyuki Takizawa, Tohoku University
- Taisuke Boku, University of Tsukuba
- Kengo Nakajima, University of Tokyo
- Toshio Endo, Institute of Science Tokyo
- Susumu Date, Osaka University
- Kazuki Yoshizoe, Kyushu University
- Kento Aida, NII
- Hirotaka Ogawa, AIST
- Takumi Honda, JHPCN
- Anders Dam Jensen, EuroHPC JU

**発表内容 (Abstract) - 英語**:

As AI reshapes the global research and innovation landscape, national supercomputing centers across the Asia-Pacific and the world are evolving rapidly to meet new demands. Building on five years of dialogue through the SCAsia HPC Centre Leaders Forum and the growing collaboration within the Alliance of Supercomputing Centres (ASC), this session proposes the establishment of a dedicated HPC Centers Forum at SCAsia/HPCAsia 2026. Co-chaired by Taisuke Boku (Center for Computational Sciences, University of Tsukuba, Japan) and Andrew Rohl (National Computational Infrastructure, the Australian National University, Australia), the session will showcase how HPC centers across the region are pivoting in response to AI—reimagining infrastructure architectures, adapting research workflows, refining service delivery models, evolving resource allocation strategies, and engaging new user communities. The session will feature a curated selection of short presentations from regional HPC leaders, highlighting center-level strategies and national policy drivers. We will share the insights, cross-center learning, and discussion of future collaboration opportunities across APAC and the world. The HPC Centers Forum aims to become a recurring feature of SCAsia/HPCAsia, reinforcing regional leadership, enabling collective action, and fostering a coordinated response to the global HPC, AI and more convergence challenge.

**発表内容（日本語）**:

AIがグローバルな研究とイノベーションの風景を変革する中、アジア太平洋地域および世界中の国立スーパーコンピューティングセンターは、新しい需要に対応するために急速に進化しています。SCAsia HPCセンターリーダーズフォーラムを通じた5年間の対話と、スーパーコンピューティングセンター連合（ASC）内での協力の拡大を基盤として、このセッションはSCAsia/HPCAsia 2026での専用HPCセンターフォーラムの設立を提案します。筑波大学計算科学研究センターの朴泰祐とオーストラリア国立大学の国立計算インフラストラクチャのAndrew Rohlが共同議長を務め、このセッションでは、地域全体のHPCセンターがAIにどのように対応しているかを紹介します。

---

### HPC For Large-Scale Weather Prediction and Climate Modelling

**時間**: 11:30 - 17:00

**発表者**:
- Dale Barker, Centre for Climate Research Singapore (CCRS)
- Shigenori Otsuka（大塚成徳）, RIKEN R-CCS

**発表内容 (Abstract) - 英語**:

Numerical Weather Prediction (NWP) and climate modelling have for decades relied on traditional 'physical' models, which provide numerical approximations to the Navier Stokes, thermodynamics, and wider Earth System processes discretized and parameterized for solution on some of the world's largest supercomputers. The balance between model complexity, accuracy, uncertainty representation, time-to-solution etc. is an important consideration for weather/climate applications ranging from operationally 'nowcasting' local rainfall in the next 30 minutes, to simulating the global climate systems under various greenhouse gas emissions scenarios over coming decades.

Recent expansion of the use of data-driven (AI and machine learning) techniques to replace (or in the case of hybrid modelling – complement) physics-based approaches has instigated a revolution in NWP and climate modelling. ML-based approaches are now being considered across every stage of the weather/climate data processing chain, ranging from algorithm-specific (e.g. QC, data assimilation, process emulation, bias correction, post-processing, etc.) to full end-to-end (e.g. observation to forecast) approaches.

This session will draw together practitioners in computationally-intensive weather/climate science from world-leading research institutes, operational weather centres, national compute organisations, and the private sector. Speakers will outline their unique priorities and approaches to solving weather/climate challenges, and the specific role of large-scale compute and AI within these national and international endeavours.

**発表内容（日本語）**:

数値気象予測（NWP）と気候モデリングは、数十年にわたり伝統的な「物理的」モデルに依存してきました。最近のデータ駆動型（AIおよび機械学習）技術の使用の拡大は、NWPと気候モデリングに革命をもたらしました。このセッションでは、世界有数の研究機関、運用気象センター、国立計算機関、および民間セクターから、計算集約型の気象/気候科学の実践者が集まります。

---

### AI-Powered Pandemic Preparedness: Building a Global Supercomputing Infrastructure for Rapid Response

**時間**: 11:30 - 17:00

**発表者**:
- Arvind Ramanathan, Argonne National Laboratory
- Newton Wahome, Coalition for Epidemic Preparedness Innovations (CEPI)

**スピーカー一覧**:
- Arvind Ramanathan (Argonne National Laboratory)
- Matthew Doxey (Google)
- Martin Steinegger (Seoul National University)
- Newton Wahome (Coalition for Epidemic Preparedness Innovations)
- Minkyung Baek (Seoul National University)
- Biosecurity Expert (TBD) (Japan AI Safety Institute)

**プログラム**:
| 時間 | 内容 |
|------|------|
| 11:00-11:15 | Welcome and Introduction |
| 11:15-11:45 | Vision and Architecture of the Pandemic Preparedness Engine |
| 11:45-12:15 | European Perspective on Cross-Border HPC Coordination |
| 12:15-12:45 | Asia-Pacific AI Factories and Regional Strategy |
| 12:45-14:00 | Lunch Break |
| 14:00-14:30 | From Pathogen Detection to Vaccine Deployment |
| 14:30-15:00 | AI-Accelerated Protein Design and Foundation Models |
| 15:00-15:30 | Break |
| 15:30-16:00 | Responsible Innovation and Global Equity |
| 16:00-16:45 | Panel Discussion: Building a Sustainable Global Infrastructure |
| 16:45-17:00 | Audience Q&A and Closing Remarks |

**発表内容 (Abstract) - 英語**:

The COVID-19 pandemic revealed critical gaps in our ability to rapidly characterize emerging pathogens and design countermeasures. This session presents the Pandemic Preparedness Engine (PPX), an ambitious initiative by the Coalition for Epidemic Preparedness Innovations (CEPI) to establish a global network of "AI Factories" at leading supercomputing centers. These facilities will integrate high-performance computing, AI/ML, and automated experimental validation to compress vaccine development timelines from years to 100 days.

**発表内容（日本語）**:

COVID-19パンデミックは、新興病原体を迅速に特性評価し、対策を設計する能力における重大なギャップを明らかにしました。このセッションでは、主要なスーパーコンピューティングセンターに「AIファクトリー」のグローバルネットワークを確立するという、CEPIによるパンデミック準備エンジン（PPX）を紹介します。

---

### Trillion Parameter Consortium (TPC) - Co-located Event

**時間**: 11:30 - 17:00（1/27）、11:00 - 17:00（1/28）

**発表者**:
- Rio Yokota（横田理央）, Institute of Science Tokyo / RIKEN R-CCS
- Charlie Catlett

**発表内容 (Abstract) - 英語**:

The TPC is a global initiative that brings together scientists from government laboratories, academia, research institutes, and industry to tackle the immense challenges of building large-scale AI systems for scientific discovery. By focusing on the development of massive generative AI models, the consortium aims to advance trustworthy and reliable AI tools that address complex scientific and engineering problems.

**発表内容（日本語）**:

TPCは、科学的発見のための大規模AIシステムを構築するという膨大な課題に取り組むため、政府研究所、学術機関、研究機関、産業界の科学者を集めたグローバルなイニシアチブです。

---

### HANAMI - Co-located Event

**時間**: 11:30 - 17:00

**発表者**:
- Kengo Nakajima（中島研吾）, The University of Tokyo / RIKEN R-CCS
- France Boillod-Cerneux

**Website**: https://hanami-project.com/

**発表内容 (Abstract) - 英語**:

HANAMI is a collaborative initiative that fosters scientific partnerships between European and Japanese research institutions, with a focus on high-performance computing (HPC) and Artificial Intelligence (AI) at the exascale level and beyond. Bringing together leading research centers and supercomputing facilities, HANAMI targets key priority domains that are climate and weather modeling, biomedical research, and materials science.

**発表内容（日本語）**:

HANAMIは、エクサスケールレベル以上のHPCとAIに焦点を当て、欧州と日本の研究機関間の科学的パートナーシップを促進する協力的なイニシアチブです。

---

### Connecting Global HPC Infrastructure with Grassroots Innovation

**時間**: 13:30 - 17:00

**発表者**:
- Worawan Diaz Carballo, Thammasat University
- Fabrizio Gagliardi, Barcelona Supercomputing Center

**プログラム**:
| 時間 | 内容 | 発表者 |
|------|------|--------|
| 1:30–1:40 | Opening and Framing Talk | Worawan Diaz Carballo & Fabrizio Gagliardi |
| 1:40–2:00 | Building HPC Education Pipelines | Fabrizio Gagliardi (BSC) |
| 2:00–2:20 | Bridging Continents: HPC Education | Bernd Mohr (JSC) |
| 2:20–2:40 | Bridging Experts and Newcomers | Qingchun Song (HPC-AI Advisory Council) |
| 3:00–3:20 | AI-HPC Convergence in Education | Mohammad Wahib (RIKEN R-CCS) |
| 3:20–3:40 | Coordinating International HPC Training | Kengo Nakajima |
| 3:40–4:00 | From Supercomputers to Super Communities | Worawan Diaz Carballo |
| 4:00–4:50 | Panel Discussion | Moderators: Bernd Mohr & Fabrizio Gagliardi |
| 4:50-5:00 | Closing Synthesis | Worawan Diaz Carballo |

**発表内容 (Abstract) - 英語**:

High-Performance Computing (HPC), once confined to elite research centers, is now becoming more accessible through cloud integration and shared infrastructure. This democratization creates opportunities, but access alone is not enough. Training and mentoring are crucial for transforming resources into solutions.

**発表内容（日本語）**:

ハイパフォーマンスコンピューティング（HPC）は、かつてはエリート研究センターに限定されていましたが、クラウド統合と共有インフラストラクチャを通じてよりアクセスしやすくなっています。

---

### Hybrid Quantum–Classical HPC in Practice

**時間**: 13:30 - 17:00

**発表者**:
- Tommaso Macrì
- Ayumu Imai（今井歩）

**発表内容 (Abstract) - 英語**:

As quantum processors begin integrating with GPU/CPU supercomputers, HPC centers must chart a practical path from pilots to production. This invited session brings together QuEra, Pawsey, Deloitte Tohmatsu, LINKS Foundation and Jij, Inc to share lessons from real deployments and cross-regional initiatives.

**発表内容（日本語）**:

量子プロセッサがGPU/CPUスーパーコンピュータと統合され始める中、HPCセンターはパイロットから本番への実用的な道筋を描く必要があります。

---

### Converging Quantum and AI

**時間**: 13:30 - 17:00

**発表者**:
- Tatsuhiro Chiba（千葉立寛）
- Hiroshi Horii（堀井洋）

**発表内容 (Abstract) - 英語**:

The emergence of Quantum Computing and Artificial Intelligence (AI) is reshaping industries and redefining the boundaries of what is computationally possible. These two transformative technologies are not only advancing independently but are also beginning to converge, offering unprecedented opportunities to solve complex problems across domains.

**発表内容（日本語）**:

量子コンピューティングと人工知能（AI）の出現は、産業を再形成し、計算上可能なものの境界を再定義しています。

---

### Ethernet for HPC/AI clusters

**時間**: 13:30 - 17:00

**発表者**: Mohan Kalkunte (Broadcom)

**スピーカー一覧**:
- Mohan Kalkunte (Broadcom)
- Niranjan Vaidya (Broadcom)
- TBC (AMD)
- Koichi Hyodo (Arista)
- Yuichiro Ajima（安島雄一郎）(Fujitsu)
- Dr Panda (The Ohio State University)
- Daniele De Sensi (Sapienza Univ of Rome)

**発表内容 (Abstract) - 英語**:

The rapid growth of AI model sizes has shifted system bottlenecks from compute to communication, making interconnect scalability and efficiency critical for training performance. This work examines recent advances that position Ethernet as a viable interconnect for both AI scale-out and emerging scale-up environments.

**発表内容（日本語）**:

AIモデルサイズの急速な成長により、システムのボトルネックは計算から通信にシフトし、インターコネクトのスケーラビリティと効率がトレーニングパフォーマンスにとって重要になっています。

---

## Research Sessions (Paper Tracks)

### Paper Track 1: Quantum Simulation & Kernels

**時間**: 11:30 - 12:30

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 11:30 - 12:00 | GCAMPS: A Scalable Classical Simulator for Qudit Systems | Ben Harper, Azar Nakhl, Thomas Quella, Martin Sevior, Muhammad Usman |
| 12:00 - 12:30 | EmuPlat: A Framework-Agnostic Platform for Quantum Hardware Emulation with Validated Transpiler-to-Pulse Pipeline | Jun Ye, Jun Yong Khoo |

---

### Paper Track 2: Using AI in HPC

**時間**: 11:30 - 12:30

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 11:30 - 12:00 | ChatMPI: LLM-Driven MPI Code Generation for HPC Workloads | Pedro Valero-Lara, Aaron Young, Thomas Naughton III, Christian Engelmann, Al Geist, Jeffrey S. Vetter, Keita Teranishi, William F. Godoy |
| 12:00 - 12:30 | TRIOS: Reducing File-System Contention through Predictive Time-Resolved I/O Simulation in Job Scheduling | YuTsen Tseng, Masatoshi Kawai, Keichi Takahashi, Hiroyuki Takizawa |

---

### Paper Track 3: Quantum Software & Tooling

**時間**: 13:30 - 15:00

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 13:30 - 14:00 | Integrating Quantum Software Tools with(in) MLIR | Patrick Hopf, Erick Ochoa Lopez, Yannick Stade, Damian Rovara, Nils Quetschlich, Ioan Albert Florea, Josh Izaac, Robert Wille, Lukas Burgholzer |
| 14:00 - 14:30 | The X Quantum Software Stack | Lukas Burgholzer et al. |
| 14:30 - 15:00 | QPU Micro-Kernels for Stencil Computation | Stefano Markidis, Luca Pennati, Gilbert Netzer, Marco Pasquale, Ivy Peng |

---

### Paper Track 4: Linear Algebra & Tensor-Core Techniques I

**時間**: 13:30 - 15:00

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 13:30 - 14:00 | Optimization of a GEMM Implementation using Intel AMX | Yusuke Endo, Satoshi Ohshima, Takeshi Nanri |
| 14:00 - 14:30 | Guaranteed DGEMM Accuracy While Using Reduced Precision Tensor Cores Through Extensions of the Ozaki Scheme | Angelika Schwarz et al. |
| 14:30 - 15:00 | Towards Unified Acceleration: Weight-Stationary GEMM on HPC-oriented Elastic CGRAs | Chenlin Shi, Boma Adhi, Lin Teng, Jiaheng Liu, Shinobu Miwa, Kentaro Sano |

---

### Paper Track 5: Quantum Algorithms & Data Access

**時間**: 15:30 - 17:00

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 15:30 - 16:00 | Design of a Superposition-Based Approximate QRAM for Noise-Tolerant Quantum Machine Learning | Sohrab Sajadimanesh, Ehsan Atoofian |
| 16:00 - 16:30 | Deterministic Quantum Search for Index Retrieval | Harishankar Mishra, Asvija Balasubramanyam, Gudapati Naresh Raghava |
| 16:30 - 17:00 | Deep Learning-Integrated Pairwise-Qubit Subsystems for Highly Efficient Quantum Circuit Simulation | Santana Yuda Pradata et al. |

---

### Paper Track 6: Linear Algebra & Tensor-Core Techniques II

**時間**: 15:30 - 17:00

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 15:30 - 16:00 | Improved Implementation of Number Theoretic Transform on NVIDIA GPU with Tensor Cores | Yukimasa Sugizaki, Daisuke Takahashi |
| 16:00 - 16:30 | Tensor-Core-Optimized Strategies for BLR × Tall-Skinny Matrix Multiplication in BEM | Akihiro Ida, Kazuya Goto, Rio Yokota et al. |
| 16:30 - 17:00 | Mixed-precision Interpolative Decomposition on GPUs **[Best Paper Finalist]** | Qianxiang Ma, Toshiyuki Imamura |

---

## Lunch Speaker Sessions (1/27)

### DataDirect Networks
**時間**: 12:30 - 13:30
**タイトル**: TBA

### CORE MICRO SYSTEMS INC.
**時間**: 12:30 - 13:30
**タイトル**: Innovative AI HPC solutions that enable advanced, AI-intensive supercomputing

**スピーカー**: Dmitry Livshits (Xinnor CEO), Tsuyoshi Okawa, Kazuhiro Hirano, Chiaki Nishikawa

### Amazon Web Services
**時間**: 12:30 - 13:30
**タイトル**: HPC and Cloud ~challenges and future vision ~

**Speaker**: Kirti Devi, Head of Global HPC Go-To-Market

**経歴**: Kirti Devi is a dynamic and accomplished strategic leader with a track record of delivering business growth and innovation. With 15+ years of experience in business development, product management, and strategic alliances at HPE, Microsoft, and Intel across HPC, AI-ML and Enterprise Software segments.

**パネリスト**:
- Rio Yokota (Institute of Science Tokyo / RIKEN)
- Worawan Diaz Carballo (Thammasat University)
- Liew Chee Sun (Sunway University)

### GMO Internet, Inc.
**時間**: 12:30 - 13:30
**タイトル**: GMO Internet & NVIDIA ～The Challenge of Optimizing Supercomputers for Commercial Services～

### IBM Japan, Ltd.
**時間**: 12:30 - 13:30
**タイトル**: Toward Quantum Advantage: Quantum-Centric Supercomputing Software Architecture and Scientific Applications / Data-Centric Architecture

**スピーカー**: Hiroshi Horii (Head of IBM Quantum Japan), Chris Maestas (CTO, Data and AI Storage Solutions)

---

## Birds of a Feather (BoF) Sessions (1/27)

| 時間 | タイトル | 会場 | 発表者 |
|------|---------|------|--------|
| 17:00 - 18:00 | The State of Open-Source Simulation Software | Room 702 | Jack Jones |
| 17:00 - 18:00 | Real-Time Scientific Data Streaming to HPC Nodes | Room 1008 | Alex Upton |
| 17:00 - 18:00 | Frontiers of Quantum Scientific Computing | Room 802 | Tan Bui-Thanh, Yuki Sato |
| 17:00 - 18:00 | MLPerf: A Benchmark for Machine Learning | Room 1001 | Tom St John, Geoffrey Fox |
| 17:00 - 18:00 | Agriculture Empowered by Supercomputing | Room 1002 | Nicolas Erdody, Rio Yokota |
| 15:30 - 18:00 | Slurm + Slinky for the AI and Supercomputer meeting | Room 1003 | Howard Weiss, Brian Christiansen |
| 17:00 - 18:00 | The Symbiosis of Brain Science and Computing | Room 1007 | Lena Oden, Kenji Doya |
| 17:00 - 18:00 | Quantum Leap for HPC | Room 801 | Marwa Farag |
| 16:30 - 18:30 | Open OnDemand User Group Meeting | Room 1101 | Julie Ma |
| 17:00 - 18:00 | Building bridges between East and West in advancing Arm software ecosystem | Room 1102 | Filippo Spiga, Simon McIntosh-Smith |

---

# 1月28日（水）January 28, 2026

## タイムスケジュール

| 時間 | 内容 | 発表者/担当者 |
|------|------|---------------|
| 09:00 - 17:00 | Exhibition | 3F Event Hall |
| 09:00 - 09:45 | Keynote: AI as a Scientist | Hiroaki Kitano (Sony CSL) |
| 09:45 - 10:30 | Keynote: Quo Vadis Computer Architecture | Mateo Valero (BSC) |
| 11:00 - 12:30 | Invited Session: Fishbowl Panel | Addison Snell |
| 11:00 - 12:30 | Paper Track 7-9 | - |
| 11:00 - 17:00 | Vision and Strategy (continued) | Taisuke Boku, Andrew Rohl |
| 11:00 - 17:00 | Societal Impact of HPC and AI | Ryosuke Murayama et al. |
| 11:00 - 17:00 | TPC (continued) | Rio Yokota, Charlie Catlett |
| 11:00 - 17:50 | R-CCS International Symposium | Mitsunori Ikeguchi |
| 12:30 - 13:30 | Lunch Speaker Sessions | 各社スポンサー |
| 13:30 - 15:00 | Paper Track 10: MPI, Topology & Contention | - |

---

## 基調講演 / Keynote Speeches

### Keynote 3: AI as a Scientist

**時間**: 09:00 - 09:45
**会場**: 5F Main Hall

**発表者**: Hiroaki Kitano（北野宏明）
**所属**: President & CEO, Sony Computer Science Laboratories (Sony CSL), Japan

**経歴 (Biography)**:

Hiroaki Kitano is President and CEO of Sony Computer Science Laboratories, Inc. (Sony CSL). Kitano joined Sony CSL as a researcher in 1993 and has served as President and CEO since 2011. He served as Chief Technology Officer of Sony Group Corporation from 2022 to 2024 and has been Chief Technology Fellow since 2025.

As a researcher at Carnegie Mellon University, Kitano built large-scale data-driven AI systems on massively parallel computers, for which he received the Computers and Thought Award from IJCAI. At Sony CSL and California Institute of Technology, he pioneered the field of systems biology.

Outside Sony, Kitano is a member of the OECD Expert Group on AI Futures, Japan's AI Strategy Council and AI Safety Institute. Within academia, he serves as a professor at Okinawa Institute of Science and Technology (OIST). He is the Founding President of RoboCup Federation. In 2021, Kitano established the Nobel Turing Challenge, a grand challenge to develop a new engine for scientific discovery.

**発表内容 (Abstract) - 英語**:

Creating fully or highly autonomous AI and robotics systems to perform high-caliber scientific research will be the most important scientific accomplishment (1). The Nobel Turing Challenge is a grand challenge aiming at building AI scientists capable of making major scientific discoveries continuously at the level worthy of Nobel Prizes (2). The WARP Drive for scientific discoveries shall be created, initially based on the idea of Trillions of data, billions of hypotheses, millions of experiments, and thousands of discoveries. Establishing the cycle of massive extraction of knowledge, massive hypothesis generation, massive experiments by robotics, and massive verification and knowledge consolidation, is the critical first step. This approach is a total flip of conventional wisdom of how science can be performed. Rather than trying to ask an important question, AI scientists may ask every question and important answers are there to be discovered. Massive computing power to enable AI capabilities combined with sophisticated robotics systems for high-precision experiments are the key to the success.

**発表内容（日本語）**:

高度な科学研究を行うための完全または高度に自律的なAIおよびロボティクスシステムを作成することは、最も重要な科学的成果となるでしょう。ノーベル・チューリング・チャレンジは、ノーベル賞に値するレベルの主要な科学的発見を継続的に行うことができるAI科学者を構築することを目指すグランドチャレンジです。科学的発見のためのWARPドライブは、数兆のデータ、数十億の仮説、数百万の実験、数千の発見というアイデアに基づいて作成されます。

---

### Keynote 4: Quo Vadis Computer Architecture: Back to the Future

**時間**: 09:45 - 10:30
**会場**: 5F Main Hall

**発表者**: Mateo Valero
**所属**: Director/Professor, Barcelona Supercomputing Center (BSC) / Technical University of Catalonia (UPC)

**経歴 (Biography)**:

Mateo Valero is professor of Computer Architecture at Technical University of Catalonia (UPC) and is the Founding Director of the Barcelona Supercomputing Center, where his research focuses on high performance computing architectures. He has published approximately 700 papers, has served in the organization of more than 300 International Conferences and has given more than 800 invited talks. Prof. Valero has been honored with numerous awards: The Eckert-Mauchly Award 2007, the Seymour Cray Award 2015, and the Charles Babbage 2017 by IEEE. Prof. Valero is a "Hall of the Fame" member of the ICT European Program.

**発表内容 (Abstract) - 英語**:

The leitmotif of my talk will be the thesis that past advances in computer architecture continue to be relevant in our field today and will dictate the future. In that context, I will touch upon how the current AI accelerators are based on the systolic arrays, how the long vector processors of today are influenced by Cray supercomputers, and how past architecture ideas to support different data formats are reused for mixed precision support in HPC and for layer-by-layer optimization of energy-efficient AI accelerators.

**発表内容（日本語）**:

私の講演のライトモチーフは、コンピュータアーキテクチャにおける過去の進歩が今日の私たちの分野でも引き続き関連性があり、将来を決定するという命題です。現在のAIアクセラレータがシストリックアレイに基づいていること、今日のベクトルプロセッサがCrayスーパーコンピュータの影響を受けていることについて触れます。

---

## Invited Sessions (1/28)

### Fishbowl Panel: Big Questions for HPC-AI

**時間**: 11:00 - 12:30

**発表者**: Addison Snell (Intersect360 Research)

**発表内容 (Abstract) - 英語**:

Following the success and popularity of the "Fishbowl Panel" at ISC, we look forward to bringing the format to SCA / HPCAsia 2026. This panel will explore the disruptions and revolutions facing HPC and AI, seeking to separate out the true innovations and advancements from what is myth, hype, or marketing. Every eight minutes, one of the three panelists will be dismissed, replaced by a willing member of the audience.

**発表内容（日本語）**:

ISCでの「フィッシュボウルパネル」の成功と人気に続いて、このフォーマットをSCA / HPCAsia 2026に持ち込みます。8分ごとにパネリストが交代し、聴衆の希望者と入れ替わります。

---

### Societal Impact of HPC and AI

**時間**: 11:00 - 17:00

**発表者**:
- Ryosuke Murayama（村山良介）, R-CCS
- Earl Joseph, Hyperion Research
- Debra Goldfarb, Amazon Web Services

**プログラム**:
| 時間 | 内容 |
|------|------|
| 11:00-12:40 | Presentations: Earl Joseph, Makoto Tsubokura, Masahiro Kazumori |
| 12:40-13:30 | Lunch Break |
| 13:30-15:30 | Presentations: Nobuyasu Ito, Takane Hori, Anders Jensen, Debra Goldfarb |
| 16:00-16:55 | Plenary Discussion moderated by Earl Joseph |

**発表内容 (Abstract) - 英語**:

High-performance computing (HPC), increasingly combined with AI and cloud-scale resources, is becoming a critical enabler for addressing complex global challenges. This invited session will examine how advanced computational capabilities are transforming the ways governments, researchers, and industries design solutions for public health, environmental resilience, and sustainable development.

**発表内容（日本語）**:

ハイパフォーマンスコンピューティング（HPC）は、AIおよびクラウドスケールのリソースとますます組み合わされ、複雑なグローバルな課題に対処するための重要なイネーブラーとなっています。

---

### The 8th R-CCS International Symposium

**時間**: 11:00 - 17:50

**発表者**: Mitsunori Ikeguchi（池口満徳）, RIKEN R-CCS

**Website**: https://www.r-ccs.riken.jp/R-CCS-Symposium/2026/

**プログラム**:
| 時間 | 内容 | Chair |
|------|------|-------|
| 11:00-11:10 | Opening & MOU Signing Ceremony | Mitsunori Ikeguchi |
| 11:10-12:30 | Session-1: FugakuNEXT: HPC Applications | Yasumichi Aoki |
| 12:30-13:30 | Lunch Break | - |
| 13:30–15:00 | Session-2: FugakuNEXT: AI for Science | Rio Yokota, Mohamed Wahib |
| 15:00-15:30 | Break | - |
| 15:30–16:20 | Overview | Satoshi Matsuoka |
| 16:20–17:50 | Session-3: FugakuNEXT: Systems | Masaaki Kondo |
| 17:50 | Closing | Mitsunori Ikeguchi |
| 18:15–20:00 | Reception | - |

**発表内容 (Abstract) - 英語**:

The 8th R-CCS International Symposium will be held to discuss the outlook from Fugaku to FugakuNEXT and cutting-edge academic research on future-oriented computer science and computational science, including AI technology.

**発表内容（日本語）**:

第8回R-CCS国際シンポジウムは、「富岳」から「富岳NEXT」への展望と、AI技術を含む将来志向のコンピュータサイエンスおよび計算科学に関する最先端の学術研究について議論するために開催されます。

---

## Research Sessions (Paper Tracks) - 1/28

### Paper Track 7: Preconditioners & Multigrid at Scale

**時間**: 11:00 - 12:30

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 11:00 - 11:30 | Enhancing Stability and Optimizing Implementation of Mixed-Precision Block ε-Circulant Preconditioned Solvers | Ryo Yoda, Matthias Bolten |
| 11:30 - 12:00 | Task-decomposed Overlapped Preconditioner for Sustained Strong Scalability | Niclas Jansson, Martin Karp, Szilard Pall, Stefano Markidis, Philipp Schlatter |
| 12:00 - 12:30 | A Matrix-Free Algebraic hp-Multigrid Method for CFD **[Best Paper Finalist]** | Peter Ohm, Graham Harper, Niclas Jansson |

---

### Paper Track 8: Accelerators in Practice

**時間**: 11:00 - 12:30

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 11:00 - 11:30 | Beyond Exascale: Dataflow Domain Translation on a Cerebras Cluster **[Best Paper Finalist]** | Tomas Oppelstrup et al. |
| 11:30 - 12:00 | GPU Partitioning, Power, and Performance of the AMD MI300A | Amr Abouelmagd et al. |
| 12:00 - 12:30 | What Will the Grace Hopper-Powered Jupiter Supercomputer Bring for Sparse Linear Algebra? | Yu-Hsiang Tsai, Mathis Bode, Hartwig Anzt |

---

### Paper Track 9: Platforms, Clouds & Memory Systems

**時間**: 11:00 - 12:30

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 11:00 - 11:30 | Performance analysis of Arm-based processors across multiple compilers for HPC workloads | Chigusa Kobayashi et al. |
| 11:30 - 12:00 | Cloud-Hardware Co-Design for Memory Bandwidth-Bound HPC Workloads: Azure HBv5 | Amirreza Rastegari et al. |
| 12:00 - 12:30 | Modeling the Potential of Message-Free Communication via CXL.mem | Stepan Vanecek et al. |

---

### Paper Track 10: MPI, Topology & Contention

**時間**: 13:30 - 15:00

| 時間 | 論文タイトル | 著者 |
|------|-------------|------|
| 13:30 - 14:00 | Toward unprivileged, portable and generic network topology discovery | Thibaut Pepin, Julien Jaeger, Guillaume Mercier, Brice Goglin |
| 14:00 - 14:30 | Revisiting Communication Software Offloading for MPI+Threads | Sergej Breiter, Minh Chung, Karl Furlinger, Josef Weidendorfer |

---

## Lunch Speaker Sessions (1/28)

### NEC Corporation
**時間**: 12:30 - 13:30
**タイトル**: Next Vector project based on proven NEC Vector and RISC-V architecture
**Speaker**: Shintaro MOMOSE, Ph.D., NEC HPC Department

### nVent Japan/Kawamura Electric Inc
**時間**: 12:30 - 13:30
**タイトル**: Fluid Management in Technology Cooling Systems
**Speaker**: Matt Archibald, Director of Technical Architecture at nVent

**経歴**: Matt Archibald is deeply focused on liquid cooling, unified infrastructure management, and data center monitoring. He holds over 100 patents for various data center and hypervisor technologies.

### Hewlett Packard Enterprise
**時間**: 12:30 - 13:30
**タイトル**: TBA

### Vertiv
**時間**: 12:30 - 13:30
**タイトル**: TBA

### Quantinuum
**時間**: 12:30 - 13:30
**タイトル**: TBA

### Mitsubishi Heavy Industries, Ltd.
**時間**: 12:30 - 13:30
**タイトル**: Advanced Cooling and Power Solutions for Overcoming HPC Barriers

**スピーカー**:
- Akira Fujita, P.E. Jp (Elec.), Director
- Hisashi Nakaya, Director
- Kewal Dharamshi, Program Manager

**発表内容**: HPCおよびAIインフラストラクチャがデジタルインフラストラクチャの中核となる中、MHIは高度な冷却および電力技術を組み合わせたソリューションを開発し、系統電力容量、水利用、冷却・熱回収、再生可能エネルギー統合などの課題に取り組んでいます。

---

# 1月29日（木）January 29, 2026

## タイムスケジュール

| 時間 | 内容 | 発表者/担当者 |
|------|------|---------------|
| 09:00 - 15:30 | Exhibition | 3F Event Hall |
| (追加情報あり次第更新) | 各種セッション | TBA |

**注記**: 1月29日のプログラム詳細については、公式ウェブサイト（https://www.sca-hpcasia2026.jp/program.html）で最新情報をご確認ください。

---

# 付録: 展示会情報

## Exhibition

**日程・時間**:
- 1月27日（火）: 9:30 - 17:00
- 1月28日（水）: 9:00 - 17:00
- 1月29日（木）: 9:00 - 15:30

**会場**: 3F Event Hall

**出展者リスト・フロアプラン**: https://www.sca-hpcasia2026.jp/data/ExhibitorList-FloorPlan_SCA-HPCAsia2026.pdf

---

# 付録: 併催イベント (Co-located Events)

1. **ADAC18 Symposium** - https://adac.ornl.gov/18th-adac-symposium-workshop-january-29-february-2-4-2026/
2. **HANAMI (EU-Japan Alliance in HPC)** - https://hanami-project.com/
3. **R-CCS International Symposium** - https://www.r-ccs.riken.jp/R-CCS-Symposium/2026/
4. **Trillion Parameter Consortium (TPC)** - https://www.anl.gov/cels/trillion-parameter-consortium
5. **2026 ACM Asian School on HPC and AI** - https://europe.acm.org/seasonal-schools/asean/2026

---

# 参考情報

**公式ウェブサイト**: https://www.sca-hpcasia2026.jp/

**プログラム詳細**: https://www.sca-hpcasia2026.jp/program.html

**注意**: プログラムは頻繁に更新されます。日程、時間、会場情報は変更される場合がありますので、最新情報は公式サイトでご確認ください。

# 📚 Ethernet for HPC/AI clusters
## SCA/HPC Asia 2026 事前勉強資料

---

## 📋 発表情報

| 項目 | 内容 |
|------|------|
| **セッション名** | Invited Session: Ethernet for HPC/AI clusters |
| **日時** | 2026年1月27日（火）13:30 - 17:00 |
| **会場** | グランキューブ大阪（詳細TBA） |
| **セッションリーダー** | Mohan Kalkunte（Broadcom） |
| **スピーカー** | Mohan Kalkunte (Broadcom), Niranjan Vaidya (Broadcom), TBC (AMD), Koichi Hyodo (Arista), Yuichiro Ajima（安島雄一郎）(Fujitsu), Dr. DK Panda (OSU), Daniele De Sensi (Sapienza Univ of Rome) |
| **関連度** | ⭐⭐⭐⭐⭐（AI/HPC基盤技術として最重要） |

### 発表概要（公式）

> AIモデルサイズの急速な成長により、システムのボトルネックは計算から通信にシフトし、インターコネクトのスケーラビリティと効率がトレーニングパフォーマンスにとって重要になっています。本セッションでは、EthernetをAIスケールアウトおよび新興スケールアップ環境の両方に適したインターコネクトとして位置づける最近の進歩を検証します。

---

## 🎯 この発表を理解するための前提知識

### 1️⃣ インターコネクト（Interconnect）とは

**概念**: コンピュータ同士を接続し、データをやり取りするための「通信網」のことです。

```
日常の例で理解する:
┌─────────────────────────────────────────────────────────────┐
│  インターコネクト = 高速道路ネットワーク                      │
│                                                             │
│  ┌─────┐     ┌─────┐     ┌─────┐     ┌─────┐              │
│  │GPU 1│────→│     │────→│     │────→│GPU 8│              │
│  └─────┘     │     │     │     │     └─────┘              │
│              │Switch│     │Switch│                          │
│  ┌─────┐     │     │     │     │     ┌─────┐              │
│  │GPU 2│←────│     │←────│     │←────│GPU 7│              │
│  └─────┘     └─────┘     └─────┘     └─────┘              │
│                                                             │
│  道路が広い（高帯域）= 一度に多くの車（データ）が通れる      │
│  渋滞しない（低レイテンシ）= 目的地に早く着く               │
└─────────────────────────────────────────────────────────────┘
```

**なぜ重要か**: AIの学習では、何千台ものGPUが協力して計算を行います。GPUは「計算が速い」だけでなく、「計算結果を素早く共有」できなければ意味がありません。

---

### 2️⃣ Ethernet（イーサネット）の基礎

**概念**: 世界で最も広く使われているコンピュータネットワーク規格です。

```
Ethernetの進化:
┌─────────────────────────────────────────────────────────────┐
│  速度の進化（約50年の歴史）                                  │
│                                                             │
│  1973年: 2.94 Mbps（最初のEthernet）                        │
│    ↓                                                        │
│  1983年: 10 Mbps（標準化）                                  │
│    ↓                                                        │
│  1995年: 100 Mbps（Fast Ethernet）                          │
│    ↓                                                        │
│  1999年: 1 Gbps（Gigabit Ethernet）                         │
│    ↓                                                        │
│  2010年: 100 Gbps                                           │
│    ↓                                                        │
│  2024年: 400 Gbps / 800 Gbps                                │
│    ↓                                                        │
│  将来: 1.6 Tbps → 3.2 Tbps                                  │
└─────────────────────────────────────────────────────────────┘
```

**Ethernetの特徴**:
- **普遍性**: オフィス、家庭、データセンターどこでも使われている
- **低コスト**: 大量生産により機器が安価
- **相互運用性**: 異なるメーカーの機器が問題なく接続可能
- **標準化**: IEEE（電気電子技術者協会）が規格を管理

---

### 3️⃣ InfiniBand（インフィニバンド）との比較

**概念**: HPCで長年使われてきた高性能ネットワーク技術です。

```
Ethernet vs InfiniBand:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  ┌─────────────────┐     ┌─────────────────┐               │
│  │   InfiniBand    │     │    Ethernet     │               │
│  ├─────────────────┤     ├─────────────────┤               │
│  │ 専用設計        │     │ 汎用設計        │               │
│  │ 超低レイテンシ  │     │ 標準レイテンシ  │               │
│  │ 高コスト        │     │ 低コスト        │               │
│  │ 限定ベンダー    │     │ 多数ベンダー    │               │
│  │ HPC特化        │     │ 汎用           │               │
│  └─────────────────┘     └─────────────────┘               │
│                                                             │
│  例え: F1マシン vs 高性能スポーツカー                       │
│        最速だが高価で      十分速くて                       │
│        専門整備が必要      どこでも整備可能                 │
└─────────────────────────────────────────────────────────────┘
```

**最新動向（2025年）**:
- InfiniBandスイッチの売上は急増（NVIDIA Blackwell需要）
- しかしEthernetが市場シェアでリード（2年前は20%未満が今や過半数）
- Meta等の大手がRoCE（Ethernet上のRDMA）で同等性能を達成

---

### 4️⃣ RDMA（Remote Direct Memory Access）

**概念**: あるコンピュータのメモリから別のコンピュータのメモリへ、CPUを介さずに直接データを転送する技術です。

```
従来の通信 vs RDMA:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  【従来方式】荷物を手渡しで運ぶ                             │
│                                                             │
│  GPU → CPU → OS → NIC → ネットワーク → NIC → OS → CPU → GPU │
│        ↑     ↑                               ↑     ↑        │
│        コピー コピー                         コピー コピー   │
│                                                             │
│  ─────────────────────────────────────────────────────────  │
│                                                             │
│  【RDMA方式】直通トンネルで運ぶ                             │
│                                                             │
│  GPU → NIC ═══════ ネットワーク ═══════ NIC → GPU           │
│             ↑                           ↑                   │
│             CPUを通らない（ゼロコピー）                      │
│             OSも介在しない                                   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**RDMAの利点**:
1. **低レイテンシ**: CPUやOSを経由しないため超高速
2. **CPU負荷軽減**: CPUは計算に専念できる
3. **高スループット**: メモリ帯域を最大限活用

**RDMAを実現する3つのプロトコル**:
| プロトコル | 説明 |
|-----------|------|
| **InfiniBand** | 専用ネットワーク。最高性能だが高コスト |
| **RoCE (RoCEv2)** | Ethernet上でRDMAを実現。現在AIクラスタで急成長 |
| **iWARP** | TCP/IP上でRDMAを実現。互換性重視 |

---

### 5️⃣ RoCE（RDMA over Converged Ethernet）

**概念**: 標準的なEthernet上でRDMAを実現する技術です。

```
RoCEv2のパケット構造:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  ┌──────────────────────────────────────────────────────┐  │
│  │ Ethernet │ IP │ UDP │ RDMA Payload │ ICRC │          │  │
│  │ Header   │    │     │              │      │          │  │
│  └──────────────────────────────────────────────────────┘  │
│                                                             │
│  RoCEv1: L2のみ（同一VLAN内限定）                          │
│  RoCEv2: L3対応（ルーティング可能、スケーラブル）          │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**採用事例**:
- **Meta**: 24,000 GPU クラスタでRoCE採用、「InfiniBandと同等性能に調整済み」
- **Google Cloud**: A3 Ultra、A4でRoCEv2採用
- **Microsoft Azure**: NDv5シリーズでRoCE対応

---

### 6️⃣ 集団通信（Collective Communication）

**概念**: 複数のプロセス（GPU）間でデータを効率的に共有・集約する通信パターンです。

```
AllReduce（全削減）の例:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  【初期状態】各GPUが自分の勾配を持つ                        │
│                                                             │
│  GPU 0: [1, 2, 3]                                           │
│  GPU 1: [4, 5, 6]                                           │
│  GPU 2: [7, 8, 9]                                           │
│  GPU 3: [10,11,12]                                          │
│                                                             │
│          ↓ AllReduce（全GPUで合計を計算）                   │
│                                                             │
│  【結果】全GPUが同じ合計値を持つ                            │
│                                                             │
│  GPU 0: [22, 26, 30]  ← 全員が同じ結果を持つ                │
│  GPU 1: [22, 26, 30]                                        │
│  GPU 2: [22, 26, 30]                                        │
│  GPU 3: [22, 26, 30]                                        │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**AIトレーニングでの役割**:
1. 各GPUがミニバッチで勾配を計算
2. AllReduceで全GPUの勾配を平均
3. 全GPUが同じ重み更新を適用
4. モデルの一貫性を維持

**なぜネットワークが重要か**:
- 大規模GPUクラスタでは、通信時間が計算時間の10倍以上になることも
- 集団通信の効率がトレーニング速度を直接決定

---

### 7️⃣ 輻輳制御（Congestion Control）

**概念**: ネットワークが混雑したときに、データの流れを調整してパケットロスを防ぐ仕組みです。

```
輻輳制御の仕組み:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  【ECN: 明示的輻輳通知】                                    │
│                                                             │
│  送信側 ───→ [スイッチ] ───→ 受信側                         │
│              ↓混雑検知                                      │
│              パケットに「混雑マーク」を付ける               │
│                        ↓                                    │
│              受信側が送信側に「速度落として」と通知         │
│                        ↓                                    │
│              送信側が送信レートを下げる                     │
│                                                             │
│  ─────────────────────────────────────────────────────────  │
│                                                             │
│  【PFC: 優先度別フロー制御】                                │
│                                                             │
│  送信側 ───→ [スイッチ] ───→ 受信側                         │
│              ↓バッファ満杯                                  │
│              「一時停止」フレームを送信                     │
│                        ↓                                    │
│              送信側が該当優先度の送信を一時停止             │
│                        ↓                                    │
│              混雑解消後、送信再開                           │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**DCQCN（Data Center Quantized Congestion Notification）**:
- ECNとPFCを組み合わせたロスレスEthernet向けプロトコル
- RoCEv2ネットワークの標準的な輻輳制御方式
- AI/MLワークロードでパケットロスゼロを実現

---

### 8️⃣ Ultra Ethernet Consortium（UEC）

**概念**: AI/HPC向けにEthernetを最適化するための業界標準化団体です。

```
UECの組織構造と目標:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  【設立】2023年中頃                                         │
│  【メンバー】97社以上（2025年時点）                         │
│  【主要メンバー】Broadcom, Intel, Cisco, Arista, HPE,       │
│                 AMD, NVIDIA, Meta, Microsoft, Google 等     │
│                                                             │
│  【UEC 1.0仕様】2025年6月リリース                          │
│                                                             │
│  ┌─────────────────────────────────────────────────────┐   │
│  │ 560ページ以上の包括的仕様書                          │   │
│  │ ・新しいRDMAトランスポートプロトコル                 │   │
│  │ ・先進的輻輳制御メカニズム                           │   │
│  │ ・数百万エンドポイントへのスケーラビリティ          │   │
│  │ ・マルチベンダー相互運用性                           │   │
│  └─────────────────────────────────────────────────────┘   │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

**UECの革新ポイント**:
1. **Lossy Operation**: パケットロスを許容しつつ高効率を維持
2. **Trimming**: 部分的なパケット転送で効率向上
3. **Hardware-offloaded Rendezvous**: ハードウェアでのプロトコル処理

---

## 📖 発表概要

### 🎯 セッションの目的

本セッションでは、AIとHPCにおけるEthernetの役割と最新技術動向について、業界をリードする専門家が包括的に解説します。

### 📊 期待される発表内容

1. **Broadcomの視点**（Mohan Kalkunte, Niranjan Vaidya）
   - Ultra Ethernetの技術仕様と実装
   - Tomahawkシリーズスイッチの最新動向
   - スケールアウト/スケールアップ両対応のネットワーク設計

2. **スイッチベンダーの視点**（Arista: Koichi Hyodo）
   - Etherlink製品ラインのUEC 1.0対応
   - 実運用環境での性能実績

3. **システムインテグレーターの視点**（Fujitsu: Yuichiro Ajima）
   - Tofu InterconnectからEthernetへの展望
   - 次世代スパコンでのネットワーク戦略

4. **学術研究の視点**（OSU: DK Panda, Rome: Daniele De Sensi）
   - MVAPICH/MPI over Ethernet の最適化
   - 集団通信アルゴリズムの最新研究

---

## 🔬 技術的詳細

### 🧪 評価対象技術

| 技術 | 説明 | 主要製品例 |
|------|------|-----------|
| **Ultra Ethernet** | UEC 1.0準拠の新世代Ethernet | 各社対応製品（2025年〜） |
| **Tomahawk Ultra** | 51.2Tbps、250ns遅延 | Broadcom BCM78900 |
| **Tomahawk 6** | 102.4Tbps、スケールアウト向け | Broadcom BCM78920 |
| **RoCEv2** | Ethernet上のRDMA | NVIDIA Spectrum-X、AMD Pensando |
| **Tofu Interconnect D** | 富岳のインターコネクト | Fujitsu独自 |

### 📈 性能比較データ

```
MLPerf Training Benchmark（BERT-Large）:
┌─────────────────────────────────────────────────────────────┐
│                                                             │
│  Ethernet:   10,886秒  ████████████████████████████████     │
│  InfiniBand: 10,951秒  █████████████████████████████████    │
│                                                             │
│  → Ethernetが僅かに高速（約0.6%差）                         │
│                                                             │
│  MLPerf Inference（LLAMA2-70B-99.9）:                       │
│  InfiniBandが1.66%高速だが、ほぼ同等性能                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 🔍 技術課題と解決アプローチ

| 課題 | 従来の問題 | 解決アプローチ |
|------|-----------|---------------|
| **レイテンシ** | Ethernetはソフトウェア処理が多い | ハードウェアオフロード、NIC最適化 |
| **パケットロス** | 輻輳時にパケット破棄 | ECN/PFC、DCQCN |
| **スケーラビリティ** | 大規模時の性能劣化 | 適応型ルーティング、負荷分散 |
| **相互運用性** | ベンダー独自実装 | UEC標準化 |

---

## 👤 発表者プロフィール

### Mohan Kalkunte（セッションリーダー）

| 項目 | 内容 |
|------|------|
| **所属** | Broadcom Inc. |
| **役職** | Vice President, Network Switching Architecture |
| **称号** | Broadcom Fellow, IEEE Fellow |
| **経験** | 30年以上のネットワーキング・半導体業界経験 |
| **特許** | 150件以上の特許を保有 |
| **学歴** | オハイオ州立大学 博士（産業工学・OR） |

**主な業績**:
- Tomahawkシリーズの開発を主導
- IEEE Fellow選出（2015年）：Ethernetスイッチングアーキテクチャへの貢献
- SC24でも講演実績あり

---

### Yuichiro Ajima（安島雄一郎）

| 項目 | 内容 |
|------|------|
| **所属** | Fujitsu Ltd. |
| **役職** | Global Fujitsu Distinguished Engineer, Senior Architect |
| **専門** | スーパーコンピュータ向けインターコネクト |

**主な業績**:
- 京コンピュータ、富岳のインターコネクト開発を主導
- Tofu Interconnectシリーズの必須特許を保有
- ISC High Performance 2022等で講演多数

---

### Dhabaleswar K. (DK) Panda

| 項目 | 内容 |
|------|------|
| **所属** | The Ohio State University |
| **役職** | Professor, University Distinguished Scholar |
| **称号** | ACM Fellow, IEEE Fellow |
| **受賞** | IEEE Charles Babbage Award (2022), IEEE TCPP Outstanding Service Award (2024) |

**主な業績**:
- MVAPICHプロジェクト創設者：世界93カ国3,475以上の組織で利用
- 197万回以上のダウンロード実績
- 500以上の論文発表

---

### Daniele De Sensi

| 項目 | 内容 |
|------|------|
| **所属** | Sapienza University of Rome |
| **役職** | Associate Professor |
| **前職** | ETH Zurich SPCL (PostDoc) |
| **専門** | HPC、インターコネクション、省電力コンピューティング |

**主な業績**:
- 「Swing」アルゴリズム：AllReduce通信の最適化
- OSMOSIS：SmartNICのマルチテナント化
- NSDI'24、ATC'24等トップ会議で論文発表

---

## 🔗 関連研究

### 📄 主要論文

| 論文タイトル | 著者 | 発表 | 概要 |
|-------------|------|------|------|
| RDMA over Ethernet for Distributed AI Training at Meta Scale | Meta Engineering | SIGCOMM 2024 | 24,000 GPU規模でのRoCE実装詳細 |
| Swing: Short-cutting Rings for Higher Bandwidth Allreduce | De Sensi et al. | NSDI 2024 | トーラスネットワーク上のAllReduce最適化 |
| The MVAPICH project | Panda et al. | JPDC 2020 | 高性能MPI over InfiniBand/RoCE |
| The Tofu Interconnect D | Ajima et al. | IEEE HPCC 2018 | 富岳インターコネクトの設計 |

### 🛠️ 関連ツール・ライブラリ

| ツール名 | 概要 | URL |
|---------|------|-----|
| **MVAPICH2** | 高性能MPI実装（InfiniBand/RoCE対応） | http://mvapich.cse.ohio-state.edu/ |
| **NCCL** | NVIDIA集団通信ライブラリ | https://developer.nvidia.com/nccl |
| **libfabric** | OpenFabricsのRDMA抽象化層 | https://github.com/ofiwg/libfabric |
| **UCX** | 統一通信フレームワーク | https://github.com/openucx/ucx |

---

## 💭 聴講のポイント

### ❓ 質問候補

| 質問 | 意図 |
|------|------|
| Ultra Ethernet 1.0とRoCEv2の具体的な違いは？ | 新規格の優位性を理解 |
| Tomahawk UltraとTomahawk 6の使い分け基準は？ | スケールアップ vs スケールアウトの選択指針 |
| InfiniBandからEthernetへの移行で注意すべき点は？ | 実運用への適用可能性 |
| Tofu InterconnectとEthernetの共存は可能か？ | 既存HPC資産との統合 |
| 1000GPU規模でのEthernetベース構成の実績は？ | 中規模クラスタでの適用可能性 |
| 輻輳制御パラメータのチューニング指針は？ | 運用ノウハウの獲得 |

### 🏭 マツダAI駆動開発への示唆

| 観点 | 示唆 |
|------|------|
| **コスト最適化** | InfiniBandよりEthernetが低コスト。中規模AIクラスタならEthernet/RoCEで十分な可能性 |
| **インフラ統合** | 既存データセンターのEthernet基盤を活用可能。専用ネットワーク不要 |
| **ベンダーロックイン回避** | マルチベンダー対応のUEC準拠製品を選定することで柔軟性確保 |
| **将来拡張性** | 400Gbps→800Gbps→1.6Tbpsへのスムーズな移行パス |
| **技術者育成** | Ethernetスキルは汎用性が高く、採用・育成コストを抑制 |
| **クラウド連携** | AWS、Azure、GCPいずれもRoCE対応。ハイブリッド構成が容易 |

---

## 📅 関連セッション（同カンファレンス内）

| セッション名 | 日時 | 関連性 |
|-------------|------|-------|
| **Keynote: Ultra Ethernet for next-generation AI and HPC workloads** | 1/27 09:30-10:15 | Torsten HoeflerによるUltra Ethernet基調講演 |
| **Architecting the future of AI infrastructure** | 1/27 11:30-12:30 | AI基盤アーキテクチャのパネル |
| **Paper Track 10: MPI, Topology & Contention** | 1/28 13:30-15:00 | ネットワークトポロジー・競合の研究発表 |
| **Paper Track 9: Platforms, Clouds & Memory Systems** | 1/28 11:00-12:30 | CXL.memによるメッセージフリー通信 |
| **BoF: Building bridges between East and West in advancing Arm software ecosystem** | 1/27 17:00-18:00 | Armエコシステムとネットワーク |

---

## 📚 参考資料

### 📖 論文・プレプリント

- [UEC 1.0 Whitepaper (Intersect360 Research)](https://ultraethernet.org/wp-content/uploads/sites/20/2025/06/UEC1.0Whitepaper.pdf)
- [RDMA over Ethernet for Distributed AI Training at Meta Scale (Stanford)](https://cs.stanford.edu/~keithw/sigcomm2024/sigcomm24-final246-acmpaginated.pdf)
- [The Tofu Interconnect D (Fujitsu)](https://www.fujitsu.com/global/imagesgig5/the-tofu-interconnect-d-for-supercomputer-fugaku.pdf)

### 🌐 Webリソース

- [Ultra Ethernet Consortium 公式](https://ultraethernet.org/)
- [Broadcom Networking for AI](https://news.broadcom.com/networking-for-ai-ethernet-scale-up-scale-out-2025-media-kit)
- [Meta Engineering: RoCE networks for distributed AI training](https://engineering.fb.com/2024/08/05/data-center-engineering/roce-network-distributed-ai-training-at-scale/)
- [MVAPICH Project](https://mvapich.cse.ohio-state.edu/)
- [Daniele De Sensi Homepage](https://danieledesensi.github.io/)
- [DK Panda Lab](https://web.cse.ohio-state.edu/~panda.2/)

### 💻 GitHub

- [MVAPICH2](https://github.com/pmodels/mpich) - 参照実装
- [Open UCX](https://github.com/openucx/ucx) - 統一通信フレームワーク
- [libfabric](https://github.com/ofiwg/libfabric) - RDMA抽象化レイヤー

---

## 📖 用語集（高校生向け解説付き）

| 用語 | 読み方 | 説明 |
|------|--------|------|
| **Ethernet** | イーサネット | コンピュータをつなぐ世界標準の「道路」。家庭のLANケーブルも、データセンターの高速回線も同じEthernet規格。高速道路網のように、どこでも同じルールで走れる。 |
| **InfiniBand** | インフィニバンド | スパコン専用の「超特急専用線」。最速だが高価で、専門の運転手（エンジニア）が必要。 |
| **RDMA** | アールディーエムエー | Remote Direct Memory Access。2台のコンピュータ間で、CPUを介さずにメモリ同士が直接データをやり取りする技術。郵便局を通さない「ドア・トゥ・ドア宅配便」のようなもの。 |
| **RoCE** | ロッキー | RDMA over Converged Ethernet。普通のEthernetケーブルでRDMAを実現する技術。「普通の道路で宅配便を直接届ける」イメージ。 |
| **レイテンシ** | れいてんしー | データが届くまでの遅延時間。LINEのメッセージが送信から既読になるまでの時間のようなもの。短いほど良い。 |
| **スループット** | すーるーぷっと | 単位時間あたりに転送できるデータ量。高速道路で1時間に何台の車が通れるか、のようなもの。大きいほど良い。 |
| **帯域幅** | たいいきはば | データの「通り道」の太さ。4車線道路は2車線より多くの車が同時に走れる。Gbps（ギガビット毎秒）で表す。 |
| **スイッチ** | すいっち | ネットワークの「交差点」。どのデータをどこに送るか振り分ける装置。 |
| **NIC** | ニック | Network Interface Card。コンピュータをネットワークに接続するための「窓口」カード。 |
| **GPU** | ジーピーユー | Graphics Processing Unit。元々は画像処理用だが、AI計算に最適。何千もの簡単な計算を同時にできる「大人数のチーム」。 |
| **AllReduce** | オールリデュース | 全員の持っている数値を足し合わせて、その結果を全員に配る集団作業。クラス全員のテスト点数を合計して、平均点を全員に伝える感じ。 |
| **集団通信** | しゅうだんつうしん | 複数のコンピュータ間でデータを一斉に送受信するパターン。「全校放送」や「連絡網」のデジタル版。 |
| **輻輳** | ふくそう | ネットワークの渋滞。データが多すぎて通れなくなる状態。朝の通勤ラッシュのイメージ。 |
| **ECN** | イーシーエヌ | Explicit Congestion Notification。「渋滞してます」という標識をパケットに付けて、送信側に速度を落とすよう伝える仕組み。 |
| **PFC** | ピーエフシー | Priority Flow Control。渋滞時に「赤信号」を出して、一時的に送信を止めてもらう仕組み。 |
| **DCQCN** | ディーシーキューシーエヌ | ECNとPFCを組み合わせた輻輳制御方式。「渋滞予報」と「信号制御」の合わせ技。 |
| **Lossy** | ロッシー | パケットを捨てることがある通信方式。普通のインターネット通信はこれ。少し情報が欠けても動画は見られる。 |
| **Lossless** | ロスレス | パケットを絶対に捨てない通信方式。AI計算では1ビットも欠けると結果が狂うので必須。 |
| **スケールアウト** | すけーるあうと | サーバの台数を増やして処理能力を上げる方法。「人手を増やす」アプローチ。 |
| **スケールアップ** | すけーるあっぷ | 1台のサーバを高性能化して処理能力を上げる方法。「一人を鍛える」アプローチ。 |
| **Tomahawk** | トマホーク | Broadcom社のEthernetスイッチチップシリーズ名。Tomahawk 6は102.4Tbpsの超高速。 |
| **Tofu Interconnect** | とうふ | Fujitsu開発のスパコン向け独自インターコネクト。「豆腐」が名前の由来（Torus Fusionの略）。 |
| **UEC** | ユーイーシー | Ultra Ethernet Consortium。AI/HPC向けにEthernetを改良する97社以上の業界団体。 |
| **MPI** | エムピーアイ | Message Passing Interface。複数のコンピュータが協力して計算するための「共通言語」。LINEのグループチャットのように、メッセージを送り合って情報を共有する。 |
| **MVAPICH** | エムヴァピッチ | オハイオ州立大学が開発した高性能MPI実装。InfiniBandやRoCE上で動作。 |
| **NCCL** | エヌシーシーエル | NVIDIA Collective Communications Library。NVIDIA GPU間の集団通信を超高速化するライブラリ。 |
| **CPO** | シーピーオー | Co-Packaged Optics。スイッチチップと光学部品を一体化して省電力・小型化する技術。 |

---

*作成日: 2025-12-25*
*SCA/HPC Asia 2026 事前勉強資料*

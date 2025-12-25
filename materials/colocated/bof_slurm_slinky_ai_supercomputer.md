# 📚 BoF: Slurm + Slinky for the AI and Supercomputer Meeting
## SCA/HPC Asia 2026 事前勉強資料

---

## 📋 発表情報

| 項目 | 内容 |
|------|------|
| **セッション種別** | Birds of a Feather (BoF) |
| **タイトル** | Slurm + Slinky for the AI and Supercomputer meeting |
| **日時** | 2026年1月27日（火）15:30 - 18:00 |
| **会場** | Room 1003 |
| **発表者** | Howard Weiss, Brian Christiansen (SchedMD) |
| **難易度** | ⭐⭐⭐（中級〜上級） |
| **関連分野** | ジョブスケジューリング、ワークロード管理、HPC、AI/ML基盤 |

---

## 🎯 この発表を理解するための前提知識

### 1️⃣ ワークロードマネージャー（ジョブスケジューラー）とは

スーパーコンピュータやHPCクラスタでは、多くのユーザーが同時に計算を実行したいと考えます。しかし、計算機の資源（CPU、GPU、メモリなど）は有限です。そこで「**ワークロードマネージャー**」が交通整理の役割を果たします。

```
   ユーザーA ──┐
              │      ┌─────────────────┐      ┌──────────────┐
   ユーザーB ──┼─────▶│ ワークロード      │─────▶│ 計算ノード群   │
              │      │ マネージャー      │      │ (CPU/GPU)     │
   ユーザーC ──┘      │ (Slurm等)        │      └──────────────┘
                     └─────────────────┘
                           │
                           ▼
                     ・ジョブの順番待ち管理
                     ・資源の割り当て
                     ・公平性の確保
```

**日常的な比喩**: ワークロードマネージャーは、遊園地のアトラクションの「ファストパス」システムのようなものです。人気のアトラクション（計算機資源）に対して、誰がいつ乗れるか（計算できるか）を効率よく管理します。

### 2️⃣ Slurm（スラーム）とは

**Slurm**（Simple Linux Utility for Resource Management）は、世界で最も広く使われているオープンソースのワークロードマネージャーです。

#### Slurmの主な機能

```
┌────────────────────────────────────────────────────────────┐
│                    Slurm の3つの役割                        │
├────────────────────────────────────────────────────────────┤
│                                                            │
│  1. 資源割当 ─────▶ ユーザーにCPU/GPUを配分               │
│                                                            │
│  2. ジョブ実行 ───▶ 割り当てたノードでプログラムを起動     │
│                                                            │
│  3. キュー管理 ───▶ 待ち行列を効率的に処理                │
│                                                            │
└────────────────────────────────────────────────────────────┘
```

#### 基本的なSlurmコマンド

```bash
# ジョブを投入する
sbatch my_job.sh

# 現在のジョブ状態を確認
squeue

# 4つのGPUを使ったインタラクティブジョブ
srun --gres=gpu:4 -N 1 --mem=1T --time 1:00:00 -I --pty /bin/bash

# クラスタの状態を確認
sinfo
```

#### Slurmジョブスクリプトの例

```bash
#!/bin/bash
#SBATCH --job-name=ai_training      # ジョブ名
#SBATCH --nodes=2                   # 使用ノード数
#SBATCH --ntasks-per-node=4         # ノードあたりのタスク数
#SBATCH --gres=gpu:4                # GPU数
#SBATCH --time=24:00:00             # 最大実行時間
#SBATCH --partition=gpu             # パーティション名

# AIモデルの分散学習を実行
python train_model.py --distributed
```

**日常的な比喩**: Slurmは、大きなレストランの予約管理システムのようなものです。テーブル（計算ノード）の空き状況を管理し、お客さん（ジョブ）を適切な時間に適切な席に案内します。

### 3️⃣ Kubernetes（クバネティス）とは

**Kubernetes**（K8s）は、コンテナ化されたアプリケーションの自動デプロイ、スケーリング、管理を行うオープンソースプラットフォームです。

```
┌─────────────────────────────────────────────────────────────┐
│                    Kubernetes クラスタ                       │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│   ┌─────────────┐   ┌─────────────┐   ┌─────────────┐      │
│   │   Pod       │   │   Pod       │   │   Pod       │      │
│   │ ┌─────────┐ │   │ ┌─────────┐ │   │ ┌─────────┐ │      │
│   │ │Container│ │   │ │Container│ │   │ │Container│ │      │
│   │ └─────────┘ │   │ └─────────┘ │   │ └─────────┘ │      │
│   └─────────────┘   └─────────────┘   └─────────────┘      │
│         ▲                 ▲                 ▲               │
│         └─────────────────┼─────────────────┘               │
│                           │                                 │
│                    ┌──────┴──────┐                          │
│                    │ K8s Master  │                          │
│                    │ (Control)   │                          │
│                    └─────────────┘                          │
└─────────────────────────────────────────────────────────────┘
```

**日常的な比喩**: Kubernetesは、コンビニのフランチャイズ本部のようなものです。各店舗（コンテナ）がどこで何を売るか、在庫が足りなくなったら自動で補充する、繁忙期には店員を増やすといった管理を自動で行います。

### 4️⃣ HPC と クラウドネイティブ の違い

| 観点 | HPC（Slurm） | クラウドネイティブ（Kubernetes） |
|------|-------------|-------------------------------|
| **主な用途** | 科学計算、シミュレーション | Webサービス、マイクロサービス |
| **ジョブ特性** | 長時間、大規模並列 | 短時間、多数の小さなジョブ |
| **リソース管理** | ノード単位、静的割当 | コンテナ単位、動的スケーリング |
| **ユーザー層** | 研究者、科学者 | 開発者、運用エンジニア |
| **ネットワーク** | 低遅延重視（InfiniBand等） | 汎用ネットワーク |

### 5️⃣ Slinky（スリンキー）とは

**Slinky**は、SchedMDが開発したSlurmとKubernetesを統合するオープンソースプロジェクトです。HPCの世界とクラウドネイティブの世界を「橋渡し」します。

```
┌──────────────────────────────────────────────────────────────┐
│                    Slinky アーキテクチャ                      │
├──────────────────────────────────────────────────────────────┤
│                                                              │
│   ┌─────────────┐                      ┌─────────────┐       │
│   │   Slurm     │◀───── Slinky ───────▶│ Kubernetes  │       │
│   │   World     │       Bridge         │   World     │       │
│   └─────────────┘                      └─────────────┘       │
│         │                                    │               │
│         ▼                                    ▼               │
│   ┌─────────────┐                      ┌─────────────┐       │
│   │ HPC Jobs    │                      │ AI Pods     │       │
│   │ MPI並列計算 │                      │ 推論サービス│       │
│   │ シミュレーション│                   │ APIサーバー │       │
│   └─────────────┘                      └─────────────┘       │
│                                                              │
│   ┌──────────────────────────────────────────────────────┐   │
│   │            共有 GPU/CPU クラスタ                       │   │
│   └──────────────────────────────────────────────────────┘   │
└──────────────────────────────────────────────────────────────┘
```

#### Slinkyの主要コンポーネント

| コンポーネント | 役割 |
|--------------|------|
| **Slurm Operator** | Kubernetes内でSlurmクラスタを自動管理・スケーリング |
| **Slurm Bridge** | SlurmジョブとKubernetes Podを統合スケジューリング（2025年6月リリース予定） |
| **Client Library** | プログラムからSlurmを操作するためのライブラリ |
| **Metrics Exporter** | 監視用メトリクスの出力 |

**日常的な比喩**: Slinkyは、異なる言語を話す2つの国の間を行き来する「通訳」のようなものです。HPCの研究者が使う言葉（Slurmコマンド）とクラウドエンジニアが使う言葉（Kubernetes YAML）を相互に翻訳し、両者が同じ計算機資源を共有できるようにします。

---

## 📖 発表概要

### 🎯 セッションの目的

このBirds of a Feather（BoF）セッションは、**AIワークロードとスーパーコンピューティングが融合する時代**において、Slurmワークロードマネージャーと新しいSlinkyプロジェクトがどのような役割を果たすかを議論する場です。

参加者同士が経験や課題を共有し、開発チームと直接対話できる貴重な機会です。

### 📊 期待される発表内容

1. **Slurm最新動向**
   - Slurm 25.05/25.11の新機能
   - GPU/AIワークロード向けの最適化
   - NVIDIA買収後の開発方針

2. **Slinkyプロジェクトの紹介**
   - Slurm OperatorによるKubernetes統合
   - Slurm Bridgeの技術詳細
   - 実際のユースケースとデモ

3. **コミュニティディスカッション**
   - ユーザーからのフィードバック収集
   - 機能リクエストの共有
   - ベストプラクティスの議論

---

## 🔬 技術的詳細

### 🧪 Slinkyの3つの統合モデル

```
┌─────────────────────────────────────────────────────────────┐
│              Slurm + Kubernetes 統合モデル                  │
├─────────────────────────────────────────────────────────────┤
│                                                             │
│  【Over モデル】                                            │
│  ┌─────────────────┐                                        │
│  │ Slurm (制御側)   │───▶ Kubernetesを一時的に起動           │
│  └─────────────────┘                                        │
│                                                             │
│  【Adjacent モデル】                                        │
│  ┌─────────────────┐  ┌─────────────────┐                   │
│  │ Slurm           │──│ Kubernetes     │ 同一ノード上で共存  │
│  └─────────────────┘  └─────────────────┘                   │
│                                                             │
│  【Under モデル】 ← Slinkyが採用                            │
│  ┌─────────────────────────────────────┐                    │
│  │ Kubernetes (制御側)                  │                    │
│  │  └── Slurm Pods (仮想クラスタ)      │                    │
│  └─────────────────────────────────────┘                    │
│                                                             │
└─────────────────────────────────────────────────────────────┘
```

### 📈 SlurmがAI/MLワークロードに適している理由

1. **GPUトポロジー認識**
   - NVLinkやNVSwitch接続を考慮したスケジューリング
   - 物理的に近いGPU同士を割り当て

2. **大規模分散学習への対応**
   - 数千GPUにまたがるジョブ管理
   - MPI/NCCLとの深い統合

3. **フェアシェアスケジューリング**
   - 複数チーム間での公平なリソース配分
   - プライオリティベースのキュー管理

4. **高スループット**
   - 毎秒数百ジョブの処理能力
   - 世界最大級のスーパーコンピュータでの実績

### 🔍 NVIDIA による SchedMD 買収の影響

2025年12月、NVIDIAはSchedMD（Slurm開発元）を買収しました。

| 項目 | 詳細 |
|------|------|
| **買収発表** | 2025年12月15日 |
| **オープンソース維持** | Slurmは引き続きオープンソース、ベンダー中立を維持 |
| **期待される改善** | NCCL統合強化、InfiniBand/RoCE最適化、GPU MIG対応向上 |
| **SchedMD CEO Danny Aubleのコメント** | 「NVIDIAとの統合により、次世代AI・スーパーコンピューティングの需要に対応したSlurm開発が加速する」 |

---

## 👤 発表者プロフィール

### Brian Christiansen

| 項目 | 内容 |
|------|------|
| **役職** | Vice President of Engineering, SchedMD |
| **所在地** | Lehi, Utah, USA |
| **学歴** | Brigham Young University, B.S. Computer Science (2003-2008) |
| **専門分野** | HPC、ワークロード管理、分散システム |
| **主なスキル** | C++, Perl, Linux, Scrum, Subversion |

#### 経歴

- **SchedMD** - VP of Engineering（現職）
  - Slurmプロジェクトの技術的方向性を統括
  - Slurm 18.08以降の主要リリースに貢献

- **AI Vector** - Senior Software Engineer
  - ITマネジメント・モニタリングサービス開発

- **Adaptive Computing** - Senior Software Engineer
  - Moab最適化スケジューラソフトウェア開発

- **Cluster Resources** - Software Developer

- **Novell** - QA Engineer

#### 登壇実績

- SC14: "Slurm Workload Manager Overview"（Danny Aubleと共同）
- SLUG19: "Slurm + GCP"
- SLUG24: "Step Management Enhancements"

### Howard Weiss

| 項目 | 内容 |
|------|------|
| **所属** | SchedMD（推定） |
| **役割** | Slurm/Slinky開発者 |

※詳細なプロフィール情報は公開されていませんが、SchedMDの技術者としてSlurm/Slinkyの開発に携わっていると推測されます。

---

## 🔗 関連研究

### 📄 主要プレゼンテーション・ドキュメント

| タイトル | 発表場所 | 年 | リンク |
|---------|---------|-----|-------|
| Slinky: The Missing Link Between Slurm and Kubernetes | SC24 | 2024 | [PDF](https://slurm.schedmd.com/MISC25/Slinky-CUG2025.pdf) |
| Slinky - CANOPIE-HPC | SC24 | 2024 | [PDF](https://slurm.schedmd.com/SC24/Slinky-CANOPIE.pdf) |
| Slinky: Slurm in Kubernetes | KubeCon Europe | 2025 | [PDF](https://slurm.schedmd.com/MISC25/Slinky-KubeConEurope2025.pdf) |
| Slurm Community BoF | SC24 | 2024 | [PDF](https://slurm.schedmd.com/SC24/Slurm-BoF.pdf) |

### 🛠️ 関連プロジェクト・ツール

| プロジェクト | 説明 | リンク |
|-------------|------|-------|
| **Slinky** | SchedMD公式のSlurm-Kubernetes統合 | [GitHub](https://github.com/SlinkyProject) |
| **SUNK** | CoreWeaveによるSlurm on Kubernetes実装 | [CoreWeave Blog](https://www.coreweave.com/blog/sunk-slurm-on-kubernetes-implementations) |
| **Soperator** | NebiusによるKubernetes Operator for Slurm | [HPCwire](https://www.hpcwire.com/off-the-wire/nebius-open-sources-soperator-to-optimize-slurm-for-ai-and-hpc-workloads/) |
| **HPK** | High-Performance Kubernetes | [arXiv](https://arxiv.org/html/2409.16919v1) |

---

## 💭 聴講のポイント

### ❓ 質問候補

| 質問 | 意図 |
|------|------|
| Slinky BridgeはどのようにしてSlurm ジョブとKubernetes Podの優先度を統一的に管理するのか？ | 異なるシステム間の公平性確保の仕組みを理解 |
| NVIDIA買収後、Slurmのオープンソースガバナンスはどう変化するか？ | 長期的な技術選定のリスク評価 |
| 既存のSlurm環境からSlinkyへの移行パスは？ | 実際の導入を検討する際の参考情報 |
| GPUトポロジー認識スケジューリングの実装詳細は？ | AI学習の効率化につながる技術詳細の把握 |
| Slurm vs 他のKubernetesスケジューラ（Volcano, Kueue等）との違いは？ | 技術選定の判断材料 |

### 🏭 マツダAI駆動開発への示唆

| 観点 | Slurm + Slinkyの活用可能性 |
|------|---------------------------|
| **AI学習基盤** | 社内GPU クラスタでの大規模モデル学習のジョブ管理に活用可能 |
| **資源の効率利用** | 研究開発チームとプロダクション推論の資源を統合管理 |
| **ハイブリッド環境** | オンプレミスHPCとクラウドKubernetesの両方を活用 |
| **コスト最適化** | フェアシェアスケジューリングによる部門間の公平なコスト配分 |
| **運用効率** | 既存のKubernetes運用ノウハウを活かしつつHPC機能を追加 |

---

## 📅 関連セッション（同カンファレンス内）

| セッション名 | 日時 | 関連度 |
|-------------|------|--------|
| Keynote: Ultra Ethernet for next-generation AI and HPC workloads | 1/27 09:30-10:15 | ⭐⭐⭐ |
| Architecting the future of AI infrastructure | 1/27 11:30-12:30 | ⭐⭐⭐ |
| Ethernet for HPC/AI clusters | 1/27 13:30-17:00 | ⭐⭐⭐ |
| Paper Track 2: Using AI in HPC | 1/27 11:30-12:30 | ⭐⭐ |
| Vision and Strategy: HPC Centers Forum | 1/27-28 | ⭐⭐ |
| R-CCS International Symposium (FugakuNEXT) | 1/28 11:00-17:50 | ⭐⭐ |
| BoF: Open OnDemand User Group Meeting | 1/27 16:30-18:30 | ⭐⭐ |

---

## 📚 参考資料

### 📖 公式ドキュメント

- [Slurm公式ドキュメント](https://slurm.schedmd.com/documentation.html)
- [Slinkyドキュメント](https://slinky.schedmd.com/)
- [SchedMD公式サイト](https://www.schedmd.com/)

### 🌐 Webリソース

- [NVIDIA SchedMD買収発表](https://blogs.nvidia.com/blog/nvidia-acquires-schedmd/)
- [Why Choose Slinky - SchedMD](https://www.schedmd.com/slinky/why-slinky/)
- [Introducing Slinky - SchedMD Blog](https://www.schedmd.com/introducing-slinky-slurm-kubernetes/)
- [Slurm for AI/ML - SchedMD](https://www.schedmd.com/slurm-industries/artificial-intelligence-machine-learning/)
- [LLNL Slurm Tutorial](https://hpc.llnl.gov/banks-jobs/running-jobs/slurm)

### 💻 GitHub

- [SchedMD/slurm](https://github.com/SchedMD/slurm)
- [SlinkyProject](https://github.com/SlinkyProject)
- [SchedMD GitLab](https://gitlab.com/SchedMD)

### 📺 動画

- [Slinky: Slurm in Kubernetes - Performant AI and HPC Workload Management](https://www.classcentral.com/course/youtube-slinky-slurm-in-kubernetes-performant-ai-and-hpc-workload-management-in-kubernetes-tim-wickberg-444911) (CNCF / Tim Wickberg)

---

## 📖 用語集（高校生向け解説付き）

| 用語 | 読み方 | 説明 |
|------|--------|------|
| **Slurm** | スラーム | Simple Linux Utility for Resource Management の略。世界中のスーパーコンピュータで使われている「仕事の順番管理システム」。遊園地の整理券システムのように、誰がいつコンピュータを使えるかを管理する。 |
| **Kubernetes** | クバネティス / クーバネティス | コンテナ化されたアプリを自動管理するプラットフォーム。K8s（ケーエイツ）とも呼ばれる。コンビニのフランチャイズ本部のように、多数の「店舗」を一括管理する。 |
| **Slinky** | スリンキー | SlurmとKubernetesを連携させるSchedMDのプロジェクト。異なる言語を話す2つの国の間の「通訳」のような役割を果たす。 |
| **ワークロードマネージャー** | わーくろーどまねーじゃー | 計算機の仕事（ワークロード）を管理するソフトウェア。レストランの予約管理システムのように、限られた席（計算資源）を効率的に割り振る。 |
| **ジョブスケジューラー** | じょぶすけじゅーらー | 計算の仕事（ジョブ）の実行順序を決めるソフトウェア。電車の運行ダイヤのように、何をいつ実行するかを計画する。 |
| **HPC** | エイチピーシー | High Performance Computing の略。スーパーコンピュータを使った高性能計算のこと。 |
| **クラスタ** | くらすた | 複数のコンピュータを束ねて1つの大きなコンピュータのように使う構成。蜂の巣のように多数の個体が協力して動く。 |
| **ノード** | のーど | クラスタを構成する個々のコンピュータ。蜂の巣の個々の部屋のようなもの。 |
| **Pod** | ポッド | Kubernetesでの最小実行単位。1つ以上のコンテナをまとめたもの。豆のさやのように、関連するコンテナをまとめて管理する。 |
| **コンテナ** | こんてな | アプリケーションとその実行環境を一緒にパッケージ化したもの。お弁当箱のように、必要なものがすべて詰まっている。 |
| **GPU** | ジーピーユー | Graphics Processing Unit の略。もともとゲームの画像処理用だったが、AI計算でも大活躍。多数の簡単な計算を同時にできる「人海戦術」が得意。 |
| **分散学習** | ぶんさんがくしゅう | AIモデルの学習を複数のGPU/コンピュータで分担して行うこと。大きなジグソーパズルを友達と分担して組み立てるようなもの。 |
| **MPI** | エムピーアイ | Message Passing Interface の略。複数のコンピュータが協力して計算するための「共通言語」。LINEのグループチャットのように、メッセージを送り合って情報を共有する。 |
| **NCCL** | ニックル | NVIDIA Collective Communications Library の略。NVIDIA GPU間で効率よくデータをやり取りするためのライブラリ。GPU専用の高速道路のようなもの。 |
| **フェアシェア** | ふぇあしぇあ | 複数のユーザー/グループ間で計算資源を公平に分配する仕組み。ケーキを公平に切り分けるルールのようなもの。 |
| **バッチジョブ** | ばっちじょぶ | 人が見ていなくても自動で実行される計算の仕事。洗濯機のように、スタートボタンを押したら放っておいても完了する。 |
| **インタラクティブジョブ** | いんたらくてぃぶじょぶ | リアルタイムで操作しながら実行する計算の仕事。ゲームのように、操作に対して即座に反応する。 |
| **パーティション** | ぱーてぃしょん | 計算ノードをグループ分けしたもの。スーパーの売り場（野菜コーナー、肉コーナー等）のように、用途別に区分けする。 |
| **キュー** | きゅー | 待ち行列のこと。銀行の整理券のように、順番待ちの仕組み。 |
| **スケーリング** | すけーりんぐ | 需要に応じてリソースを増減させること。繁忙期にアルバイトを増やし、閑散期に減らすようなもの。 |
| **オートスケーリング** | おーとすけーりんぐ | 自動的にスケーリングを行うこと。エアコンの自動温度調節のように、必要に応じて自動で調整する。 |
| **BoF** | ビーオーエフ | Birds of a Feather の略。「同じ羽の鳥は集まる」という意味で、共通の関心を持つ人々が集まる非公式なミーティング。 |
| **Operator** | オペレーター | Kubernetesで特定のアプリケーションを自動管理するためのプログラム。マンションの管理人さんのように、日常的な管理作業を代行する。 |
| **Helm Chart** | ヘルムチャート | Kubernetesアプリケーションのインストール手順をパッケージ化したもの。料理のレシピのように、必要な材料と手順がまとまっている。 |
| **SchedMD** | スケッドエムディー | Slurmの開発・サポートを行う企業。2010年設立、2025年にNVIDIAが買収。 |
| **InfiniBand** | インフィニバンド | 高性能コンピューティング向けの超高速ネットワーク技術。一般道ではなく、専用の高速道路のようなもの。 |
| **RoCE** | ロス / アールオーシーイー | RDMA over Converged Ethernet の略。Ethernetでも高速通信できるようにする技術。 |
| **TOP500** | トップ500 | 世界のスーパーコンピュータの性能ランキング。毎年6月と11月に更新される。 |

---

*作成日: 2025年12月25日*
*SCA/HPC Asia 2026 事前勉強資料*

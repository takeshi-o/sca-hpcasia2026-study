# 📚 SCA/HPC Asia 2026 事前勉強資料作成ツール

SCA/HPC Asia 2026（2026年1月26日〜29日、グランキューブ大阪）の各セッションについて、Claude Codeを使って**高校生でも理解できる詳細な事前勉強資料**を自動生成するツールです。

## 🚀 クイックスタート

### 1. プロジェクトディレクトリに移動

```bash
cd sca-hpcasia2026-study
```

### 2. Claude Codeを起動

```bash
claude
```

### 3. スラッシュコマンドで勉強資料を生成

```
/study ChatMPI
```

これだけで、ChatMPIに関する詳細な勉強資料が自動生成されます！

## 📂 ディレクトリ構造

```
sca-hpcasia2026-study/
├── CLAUDE.md                 # プロジェクトコンテキスト（Claude Code用）
├── README.md                 # このファイル
├── .claude/
│   └── commands/
│       └── study.md          # /study コマンド定義
├── data/
│   └── program_schedule.md   # 公式プログラム情報
└── materials/                # 生成された勉強資料
    ├── keynotes/             # 基調講演
    ├── sessions/             # 研究発表トラック
    ├── workshops/            # ワークショップ
    └── tutorials/            # チュートリアル
```

## 🎯 使い方

### 基本コマンド

```
/study {発表タイトルまたはキーワード}
```

### 使用例

| コマンド | 説明 |
|---------|------|
| `/study ChatMPI` | ChatMPI発表の勉強資料を作成 |
| `/study Torsten Hoefler` | Hoefler氏の基調講演の勉強資料を作成 |
| `/study Ozaki scheme` | Ozakiスキーム関連セッションの勉強資料を作成 |
| `/study quantum tutorial` | 量子コンピューティングチュートリアルの勉強資料を作成 |
| `/study FugakuNEXT` | FugakuNEXT関連セッションの勉強資料を作成 |

### 複数候補がある場合

キーワードが曖昧な場合、Claude Codeが候補を提示します:

```
> /study quantum

以下の発表が見つかりました:
1. Keynote: From NISQ to FTQC (藤井啓祐)
2. Keynote: Beyond Quantum Advantage (Jay Gambetta)
3. Tutorial: Quantum Computing with Qiskit
4. Workshop: Hybrid Quantum-Classical HPC

どの発表の勉強資料を作成しますか？（番号で指定）
```

## 📝 生成される勉強資料の構成

| セクション | 内容 |
|-----------|------|
| 📋 発表情報 | 日時、発表者、会場、関連度 |
| 🎯 前提知識 | 高校生向けの基礎概念説明（図解付き） |
| 📖 発表概要 | 研究の目的、期待される内容 |
| 🔬 技術的詳細 | 評価対象、先行研究、課題 |
| 👤 発表者プロフィール | 経歴、受賞歴、専門分野 |
| 🔗 関連研究 | 論文、ツール |
| 💭 聴講のポイント | 質問候補、マツダへの示唆 |
| 📅 関連セッション | 同カンファレンス内の関連発表 |
| 📚 参考資料 | 論文、Web、GitHub |
| 📖 用語集 | 高校生向け解説（30語以上） |

## ⚙️ カスタマイズ

### フォーマットの変更

`CLAUDE.md` の「勉強資料のフォーマット要件」セクションを編集することで、出力フォーマットをカスタマイズできます。

### 新しいコマンドの追加

`.claude/commands/` ディレクトリに新しいMarkdownファイルを追加することで、カスタムコマンドを作成できます。

例: `/speaker {発表者名}` コマンドを追加

```bash
# .claude/commands/speaker.md を作成
```

## 📊 対象カンファレンス情報

| 項目 | 内容 |
|------|------|
| **イベント名** | SupercomputingAsia 2026 & HPC Asia 2026 |
| **開催日** | 2026年1月26日（月）〜29日（木） |
| **会場** | グランキューブ大阪（大阪国際会議場） |
| **公式サイト** | https://www.sc-asia.org/ |

### 主要セッション

- 🎤 **基調講演**: 4件（Torsten Hoefler, 藤井啓祐, 北野宏明, Mateo Valero）
- 📊 **研究発表**: Paper Track 1-10（量子、AI in HPC、線形代数、MPI等）
- 🎯 **招待セッション**: Vision and Strategy, Ethernet for HPC/AI, Hybrid Quantum-Classical等
- 🤝 **併催イベント**: TPC, HANAMI, R-CCS International Symposium
- 🐦 **BoF**: 多数

## 🔧 トラブルシューティング

### Web検索が失敗する場合

ネットワーク接続を確認してください。また、検索クエリが具体的すぎる場合は、より一般的なキーワードで再試行されます。

### 発表が見つからない場合

`data/program_schedule.md` にその発表が含まれているか確認してください。含まれていない場合は、手動で情報を追加するか、タイトルの正確なスペルを確認してください。

### 出力が短すぎる場合

Claude Codeに「もっと詳しく」と依頼するか、特定のセクションについて追加情報を求めてください。

## 📄 ライセンス

このプロジェクトは個人利用を目的としています。生成された勉強資料の著作権は作成者に帰属します。引用された論文・Webリソースの著作権は各権利者に帰属します。

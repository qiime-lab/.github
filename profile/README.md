<h1 align="center">qiime-lab</h1>

<p align="center">
  <b>QIIME 2 マイクロバイオーム解析のためのオープンソースツール群</b><br>
  16S rRNA アンプリコンシーケンス解析を、より簡単に・より再現性高く・より自動的に。
</p>

<p align="center">
  <a href="https://github.com/qiime-lab/seq2pipe"><img src="https://img.shields.io/badge/seq2pipe-v1.0.0-blue?style=flat-square" alt="seq2pipe"></a>
  <a href="https://github.com/qiime-lab/qiime2-assistant"><img src="https://img.shields.io/badge/qiime2--assistant-v1.0.0-green?style=flat-square" alt="qiime2-assistant"></a>
  <a href="https://github.com/qiime-lab/qiime2-manual"><img src="https://img.shields.io/badge/qiime2--manual-v2.0.0-orange?style=flat-square" alt="qiime2-manual"></a>
</p>

---

## About

**qiime-lab** は、QIIME 2 による腸内細菌叢・マイクロバイオーム解析をローカル環境で完結させるためのツール群を開発・公開しています。

マイクロバイオーム研究では、シーケンスデータの取得後に多くの解析ステップが必要です。QIIME 2 は強力なフレームワークですが、コマンド体系の学習コスト・パラメータの選定・下流統計解析・可視化・レポート作成まで含めると、初学者にとっても経験者にとっても大きな負担になります。

qiime-lab では、この課題に対して 3 つのアプローチで取り組んでいます：

1. **自動化** — AI エージェントが解析パイプライン全体を自律的に設計・実行
2. **対話** — わからないことをチャットで即座に質問できる AI アシスタント
3. **ドキュメント** — コピー＆ペーストで実行可能な、実験室発の日本語マニュアル

すべてのツールは **完全ローカル動作** を基本としており、クラウド API や外部サービスへのデータ送信は一切ありません。

---

## Projects

### [seq2pipe](https://github.com/qiime-lab/seq2pipe) — 自動解析パイプライン

[![release](https://img.shields.io/github/v/release/qiime-lab/seq2pipe?style=flat-square)](https://github.com/qiime-lab/seq2pipe/releases)
[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/qiime-lab/seq2pipe/blob/master/LICENSE)

ローカル LLM (Ollama) を搭載した AI エージェントが、生の FASTQ データから QIIME 2 解析・統計図・レポートまでを全自動で生成します。

**主な機能：**
- **3 ステップ自動パイプライン** (`--auto` モード)
  - STEP 1: QIIME 2 コアパイプライン (DADA2 → 系統樹 → 多様性 → 分類)
  - STEP 1.5: 決定論的包括解析 — LLM 非依存で **29 種の出版品質図** を確実に生成
  - STEP 2: LLM 適応型自律解析 — データ特性に応じた応用解析を自動設計
  - STEP 3: HTML レポート自動生成
- **スマート自動検出** — DADA2 パラメータ・プライマー配列・入力データ種別・sampling depth を自動推定
- **vibe-local 方式コード生成** — LLM がデータ構造を読み取ってからコードを書くため精度が高く、エラー時は自動修正
- **対話型修正** — 生成図に対して「色を変えて」「凡例を移動して」など自然言語で修正指示
- **クロスプラットフォーム** — macOS (Intel / Apple Silicon) · Linux · Windows (WSL2 / Docker)

```bash
git clone https://github.com/qiime-lab/seq2pipe.git && cd seq2pipe
./setup.sh && ./launch.sh --fastq-dir ~/your_data --auto
```

---

### [qiime2-assistant](https://github.com/qiime-lab/qiime2-assistant) — 対話式 AI アシスタント

[![release](https://img.shields.io/github/v/release/qiime-lab/qiime2-assistant?style=flat-square)](https://github.com/qiime-lab/qiime2-assistant/releases)
[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/qiime-lab/qiime2-assistant/blob/main/LICENSE)

qiime2-manual の全 22 章をナレッジベースとして、QIIME 2 に関する質問にチャット形式で回答する AI アシスタントです。

**主な機能：**
- **RAG (検索拡張生成)** — マニュアルの記述に基づいた正確な回答、コマンドをそのまま引用
- **Streamlit Web UI** — ストリーミング応答、ワンクリック質問例、サイドバーでモデル選択
- **完全ローカル** — Ollama でローカル LLM を実行、API キー不要、オフライン対応
- **日本語対応** — UI・回答ともに日本語 (推奨モデル: `qwen2.5:7b`)
- **幅広いトピック** — インストールから DADA2、多様性解析、分類器作成、IS 除去、PERMANOVA、R/phyloseq 連携、トラブルシューティングまで

```bash
git clone https://github.com/qiime-lab/qiime2-assistant.git && cd qiime2-assistant
pip install -r requirements.txt && streamlit run app.py
```

---

### [qiime2-manual](https://github.com/qiime-lab/qiime2-manual) — 日本語マニュアル

[![release](https://img.shields.io/github/v/release/qiime-lab/qiime2-manual?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/releases)
[![license](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-lightgrey?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/blob/main/LICENSE)

QIIME 2 による 16S rRNA 遺伝子解析を **コピー＆ペーストで実行可能** にすることを目指した、実験室発の包括的日本語マニュアルです。

**主な特徴：**
- **QIIME 2 2026.1 / SILVA 138.2 対応** — 最新の amplicon distribution に準拠
- **22 章 + 付録** — データインポートからトラブルシューティングまで全工程をカバー
- **内部標準 (IS) 絶対定量** — 検量線・LINEST 関数を用いた絶対定量ワークフローを完全収録
- **クロスプラットフォーム** — macOS (Intel / Apple Silicon)・Linux・Windows (WSL2)・Docker
- **旧マニュアルからの大幅更新** — QIIME 2 2019.7 → 2026.1、SILVA 132 → 138.2、VirtualBox → WSL2、RESCRIPt・R/phyloseq 連携・Provenance tracking 等を新規追加
- **実用的な付属ファイル** — `rename.R`（ファイル名一括変更）、`setup_dirs.sh`（ディレクトリ作成）、メタデータテンプレート

---

## How They Work Together

```
┌─────────────────────────────────────────────────────┐
│                    qiime2-manual                     │
│          22章の包括的日本語ドキュメント                  │
│      (QIIME 2 2026.1 / SILVA 138.2 対応)             │
└──────────┬──────────────────────┬────────────────────┘
           │ ナレッジベース         │ 解析プロトコル準拠
           ▼                      ▼
┌─────────────────────┐ ┌─────────────────────────────┐
│  qiime2-assistant   │ │         seq2pipe            │
│                     │ │                             │
│  わからないことを     │ │  FASTQ を渡すだけで          │
│  チャットで質問       │ │  全自動で解析・作図・         │
│                     │ │  レポート生成                 │
│  Ollama + Streamlit │ │  Ollama + QIIME 2           │
└─────────────────────┘ └─────────────────────────────┘
```

- **学びながら使う** → `qiime2-manual` を読み、わからないことは `qiime2-assistant` に質問
- **すぐに結果が欲しい** → `seq2pipe --auto` で全自動解析
- **両方** → `seq2pipe` で自動解析した後、結果の解釈を `qiime2-assistant` に質問

---

## Tech Stack

`QIIME 2` · `DADA2` · `SILVA 138.2` · `Ollama` · `Streamlit` · `Python` · `pandas` · `scipy` · `scikit-learn` · `matplotlib` · `seaborn` · `NetworkX`

## License

| Repository | License |
|:--|:--|
| seq2pipe | [MIT License](https://github.com/qiime-lab/seq2pipe/blob/master/LICENSE) |
| qiime2-assistant | [MIT License](https://github.com/qiime-lab/qiime2-assistant/blob/main/LICENSE) |
| qiime2-manual | [CC BY-NC-SA 4.0](https://github.com/qiime-lab/qiime2-manual/blob/main/LICENSE) |

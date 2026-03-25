<h1 align="center">qiime-lab</h1>

<h4 align="center">QIIME 2 マイクロバイオーム解析のためのオープンソースツール群</h4>

<p align="center">
  16S rRNA アンプリコンシーケンス解析を、より簡単に・より再現性高く・より自動的に。<br>
  すべて<b>ローカル完結</b> — クラウド API・外部送信なし。
</p>

<p align="center">
  <a href="https://github.com/qiime-lab/seq2pipe/releases"><img src="https://img.shields.io/github/v/release/qiime-lab/seq2pipe?label=seq2pipe&style=flat-square&color=0969da" alt="seq2pipe"></a>
  <a href="https://github.com/qiime-lab/qiime2-assistant/releases"><img src="https://img.shields.io/github/v/release/qiime-lab/qiime2-assistant?label=assistant&style=flat-square&color=2da44e" alt="assistant"></a>
  <a href="https://github.com/qiime-lab/qiime2-manual/releases"><img src="https://img.shields.io/github/v/release/qiime-lab/qiime2-manual?label=manual&style=flat-square&color=e16f24" alt="manual"></a>
</p>

---

## About

**qiime-lab** は、QIIME 2 による腸内細菌叢・マイクロバイオーム解析をローカル環境で完結させるためのツール群を開発・公開しています。

マイクロバイオーム研究では、シーケンスデータの取得後に多くの解析ステップが必要です。QIIME 2 は強力なフレームワークですが、コマンド体系の学習コスト・パラメータの選定・下流統計解析・可視化・レポート作成まで含めると、初学者にとっても経験者にとっても大きな負担になります。

qiime-lab では、この課題に対して 3 つのアプローチで取り組んでいます：

1. **自動化** — AI エージェントが解析パイプライン全体を自律的に設計・実行
2. **対話** — わからないことをチャットで即座に質問できる AI アシスタント
3. **ドキュメント** — 初学者が QIIME 2 を学ぶための、実験室発の日本語マニュアル

すべてのツールは **完全ローカル動作** を基本としており、クラウド API や外部サービスへのデータ送信は一切ありません。

---

## Projects

### [seq2pipe](https://github.com/qiime-lab/seq2pipe) — 自動解析パイプライン

[![release](https://img.shields.io/github/v/release/qiime-lab/seq2pipe?style=flat-square)](https://github.com/qiime-lab/seq2pipe/releases)
[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/qiime-lab/seq2pipe/blob/master/LICENSE)

ローカル LLM (Ollama) を搭載した AI エージェントが、生の FASTQ データから QIIME 2 解析・統計図・レポートまでを全自動で生成します。

- **3 ステップ自動パイプライン** (`--auto`) — DADA2 → 多様性 → 分類 → 29 図自動生成 → HTML レポート
- **スマート自動検出** — DADA2 パラメータ・プライマー配列・入力データ種別・sampling depth を自動推定
- **vibe-local 方式** — LLM がデータ構造を読み取ってからコードを書く。エラー時は自動修正
- **対話型修正** — 生成図に対して自然言語で修正指示
- **クロスプラットフォーム** — macOS (Intel / Apple Silicon) · Linux · Windows (WSL2 / Docker)

```bash
git clone https://github.com/qiime-lab/seq2pipe.git && cd seq2pipe
./setup.sh && ./launch.sh --fastq-dir ~/your_data --auto
```

---

### [qiime2-assistant](https://github.com/qiime-lab/qiime2-assistant) — 対話式 AI アシスタント

[![release](https://img.shields.io/github/v/release/qiime-lab/qiime2-assistant?style=flat-square)](https://github.com/qiime-lab/qiime2-assistant/releases)
[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/qiime-lab/qiime2-assistant/blob/main/LICENSE)

qiime2-manual の全 25 章をナレッジベースとして、QIIME 2 に関する質問にチャット形式で回答する AI アシスタントです。

- **RAG ベース** — マニュアルの記述に基づいた正確な回答、コマンドをそのまま引用
- **Streamlit Web UI** — ストリーミング応答、ワンクリック質問例、サイドバーでモデル選択
- **完全ローカル** — Ollama でローカル LLM を実行、API キー不要、オフライン対応
- **日本語対応** — UI・回答ともに日本語 (推奨モデル: `qwen2.5:7b`)

```bash
git clone https://github.com/qiime-lab/qiime2-assistant.git && cd qiime2-assistant
pip install -r requirements.txt && streamlit run app.py
```

---

### [qiime2-manual](https://github.com/qiime-lab/qiime2-manual) — 日本語学習マニュアル

[![release](https://img.shields.io/github/v/release/qiime-lab/qiime2-manual?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/releases)
[![license](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-lightgrey?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/blob/main/LICENSE)

初学者が QIIME 2 を学ぶための 25 章構成の包括的日本語ガイドです。

- **各手法のメリット・デメリットを解説** — 何をしているのか・なぜ必要か・どのような選択肢があるか
- **QIIME 2 2026.5 / SILVA 138.2 対応** — ANCOM-BC2・q2-boots 等の最新手法を収録
- **内部標準 (IS) 絶対定量** — 検量線・LINEST 関数を用いた絶対定量ワークフローを完全収録
- **クロスプラットフォーム** — macOS (Intel / Apple Silicon)・Linux・Windows (WSL2)・Docker

---

## How They Work Together

```
         qiime2-manual
        /              \
  ナレッジベース      解析プロトコル
      /                  \
 assistant         seq2pipe --auto
 質問して学ぶ         結果をすぐ得る
```

- **学びながら使う** → `qiime2-manual` を読み、わからないことは `qiime2-assistant` に質問
- **すぐに結果が欲しい** → `seq2pipe --auto` で全自動解析
- **両方** → `seq2pipe` で自動解析した後、結果の解釈を `qiime2-assistant` に質問

---

## Tech Stack

<p align="center">
  <img src="https://img.shields.io/badge/QIIME_2-2026.5-44aa99?style=for-the-badge" alt="QIIME 2">
  <img src="https://img.shields.io/badge/Python-3.10-3776ab?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Ollama-LLM-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama">
  <img src="https://img.shields.io/badge/Streamlit-UI-ff4b4b?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit">
</p>
<p align="center">
  <img src="https://img.shields.io/badge/DADA2-denoising-88aa55?style=flat-square" alt="DADA2">
  <img src="https://img.shields.io/badge/SILVA_138.2-reference-55aa88?style=flat-square" alt="SILVA">
  <img src="https://img.shields.io/badge/pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="pandas">
  <img src="https://img.shields.io/badge/scikit--learn-f7931e?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn">
  <img src="https://img.shields.io/badge/scipy-8caae6?style=flat-square&logo=scipy&logoColor=white" alt="scipy">
  <img src="https://img.shields.io/badge/matplotlib-11557c?style=flat-square" alt="matplotlib">
  <img src="https://img.shields.io/badge/seaborn-4c72b0?style=flat-square" alt="seaborn">
  <img src="https://img.shields.io/badge/NetworkX-aab71b?style=flat-square" alt="NetworkX">
</p>

---

## License

| Repository | License |
|:--|:--|
| seq2pipe / qiime2-assistant | MIT |
| qiime2-manual | CC BY-NC-SA 4.0 |

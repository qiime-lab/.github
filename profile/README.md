<h1 align="center">
  <br>
  🧬 qiime-lab
  <br>
</h1>

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

## 3 つのアプローチ

|  | リポジトリ | ひとこと |
|:--:|:--|:--|
| ⚡ | **[seq2pipe](https://github.com/qiime-lab/seq2pipe)** | FASTQ を渡すだけ → 全自動で解析・29図・レポート生成 |
| 💬 | **[qiime2-assistant](https://github.com/qiime-lab/qiime2-assistant)** | マニュアルを読み込んだ AI とチャットで質問 |
| 📖 | **[qiime2-manual](https://github.com/qiime-lab/qiime2-manual)** | 初学者が QIIME 2 を学ぶための 25 章構成の日本語ガイド |

---

### ⚡ seq2pipe — 全自動解析パイプライン

```
FASTQ → DADA2 → 系統樹 → 多様性 → 分類 → 29図 → HTML レポート
```

- `--auto` で完全無人実行。DADA2 パラメータ・プライマー・sampling depth を自動検出
- LLM がデータ構造を読んでからコードを書く **vibe-local 方式**。エラー時は自動修正
- 生成図に「色を変えて」「凡例を外に」など自然言語で修正を指示可能

```bash
git clone https://github.com/qiime-lab/seq2pipe.git && cd seq2pipe
./setup.sh && ./launch.sh --fastq-dir ~/your_data --auto
```

### 💬 qiime2-assistant — 対話式 AI アシスタント

- qiime2-manual 全 25 章をナレッジベースとした **RAG** ベースの回答
- Streamlit Web UI — ストリーミング応答、ワンクリック質問例
- 推奨モデル: `qwen2.5:7b`（日本語性能が高い）

```bash
git clone https://github.com/qiime-lab/qiime2-assistant.git && cd qiime2-assistant
pip install -r requirements.txt && streamlit run app.py
```

### 📖 qiime2-manual — 日本語学習マニュアル

- 各解析が **何をしているのか**・**なぜ必要か**・**メリット・デメリット** を解説
- QIIME 2 2026.5 / SILVA 138.2 対応、ANCOM-BC2・q2-boots 等の最新手法を収録
- 内部標準（IS）絶対定量、ネガコン除去、マルチラン統合まで実験室の実務をカバー

---

## つながり

```
         📖 qiime2-manual
        ╱                ╲
  ナレッジベース       解析プロトコル
      ╱                    ╲
💬 assistant    ⚡ seq2pipe --auto
  質問して学ぶ        結果をすぐ得る
```

---

## Tech Stack

<p align="center">
  <img src="https://img.shields.io/badge/QIIME_2-2026.5-44aa99?style=for-the-badge&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHRleHQgeD0iNCIgeT0iMTgiIGZvbnQtc2l6ZT0iMTYiIGZpbGw9IndoaXRlIj5RMjwvdGV4dD48L3N2Zz4=&logoColor=white" alt="QIIME 2">
  <img src="https://img.shields.io/badge/Python-3.10-3776ab?style=for-the-badge&logo=python&logoColor=white" alt="Python">
  <img src="https://img.shields.io/badge/Ollama-LLM-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama">
  <img src="https://img.shields.io/badge/Streamlit-UI-ff4b4b?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit">
</p>
<p align="center">
  <img src="https://img.shields.io/badge/DADA2-denoising-88aa55?style=flat-square" alt="DADA2">
  <img src="https://img.shields.io/badge/SILVA_138.2-reference-55aa88?style=flat-square" alt="SILVA">
  <img src="https://img.shields.io/badge/pandas-data-150458?style=flat-square&logo=pandas&logoColor=white" alt="pandas">
  <img src="https://img.shields.io/badge/scikit--learn-ML-f7931e?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn">
  <img src="https://img.shields.io/badge/scipy-stats-8caae6?style=flat-square&logo=scipy&logoColor=white" alt="scipy">
  <img src="https://img.shields.io/badge/matplotlib-viz-11557c?style=flat-square" alt="matplotlib">
  <img src="https://img.shields.io/badge/seaborn-viz-4c72b0?style=flat-square" alt="seaborn">
  <img src="https://img.shields.io/badge/NetworkX-graph-aab71b?style=flat-square" alt="NetworkX">
</p>

---

## License

| | License |
|:--|:--|
| seq2pipe / qiime2-assistant | MIT |
| qiime2-manual | CC BY-NC-SA 4.0 |

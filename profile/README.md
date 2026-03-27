<h1 align="center">qiime-lab</h1>
<div align="center">
  <a href=https://raw.githubusercontent.com/qiime-lab/.github/main/qiimelab.png">
    <img src="main/qiimelab.png" width="215" alt="qiime-lab logo" />
  </a>
</div>
<h4 align="center">QIIME 2 マイクロバイオーム解析を学ぶためのオープンソースプラットフォーム</h4>

<p align="center">
  <a href="https://github.com/qiime-lab/seq2pipe/releases"><img src="https://img.shields.io/github/v/release/qiime-lab/seq2pipe?label=seq2pipe&style=flat-square&color=0969da" alt="seq2pipe"></a>
  <a href="https://github.com/qiime-lab/qiime2-assistant/releases"><img src="https://img.shields.io/github/v/release/qiime-lab/qiime2-assistant?label=assistant&style=flat-square&color=2da44e" alt="assistant"></a>
  <a href="https://github.com/qiime-lab/qiime2-manual/releases"><img src="https://img.shields.io/github/v/release/qiime-lab/qiime2-manual?label=manual&style=flat-square&color=e16f24" alt="manual"></a>
</p>

---

## About

**qiime-lab** は、16S rRNA アンプリコンシーケンス解析を学ぶための場です。

マニュアルで基礎から体系的に学び、わからないことはアシスタントに質問し、実際の解析はパイプラインが自動でやってくれる。学習から実践までをローカル環境で完結できるツール群を公開しています。

---

## Projects

### [qiime2-manual](https://github.com/qiime-lab/qiime2-manual) — まず読む

[![release](https://img.shields.io/github/v/release/qiime-lab/qiime2-manual?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/releases)
[![license](https://img.shields.io/badge/license-All%20Rights%20Reserved-red?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/blob/main/LICENSE)

QIIME 2 による 16S rRNA 解析の全体像を 25 章で体系的に解説した日本語マニュアル。各ステップが何をしているのか、なぜ必要なのか、どんな選択肢があるのかをメリット・デメリットとともに学べる。DADA2 からANCOM-BC2、q2-boots まで、QIIME 2 2026.1 の最新手法を網羅。内部標準による絶対定量やネガコン除去など実験室の実務もカバー。

---

### [qiime2-assistant](https://github.com/qiime-lab/qiime2-assistant) — わからなければ聞く

[![release](https://img.shields.io/github/v/release/qiime-lab/qiime2-assistant?style=flat-square)](https://github.com/qiime-lab/qiime2-assistant/releases)
[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/qiime-lab/qiime2-assistant/blob/main/LICENSE)

マニュアル全 25 章をナレッジベースに持つ、ローカル LLM チャットアシスタント。「DADA2 のパラメータの決め方は?」「PERMANOVA の実行方法は?」など、マニュアルの内容に基づいた正確な回答がチャット形式で返ってくる。Ollama + Streamlit で動作、API キー不要。

```bash
git clone https://github.com/qiime-lab/qiime2-assistant.git && cd qiime2-assistant
pip install -r requirements.txt && streamlit run app.py
```

---

<img src="https://raw.githubusercontent.com/qiime-lab/seq2pipe/master/seq2pipe.png" width="80" align="right">

### [seq2pipe](https://github.com/qiime-lab/seq2pipe) — 全部自動でやる

[![release](https://img.shields.io/github/v/release/qiime-lab/seq2pipe?style=flat-square)](https://github.com/qiime-lab/seq2pipe/releases)
[![license](https://img.shields.io/badge/license-MIT-blue?style=flat-square)](https://github.com/qiime-lab/seq2pipe/blob/master/LICENSE)

マニュアルに書いてあること、アシスタントに聞くようなこと、全部まとめて自動でやるパイプライン。FASTQ を渡すだけで DADA2 デノイジング、系統樹構築、多様性解析、分類、29 種の統計図、HTML レポートまで一気通貫。パラメータもプライマーも sampling depth も自動検出。ローカル LLM がデータを読んでコードを書き、エラーが出ても自動で直す。

```bash
git clone https://github.com/qiime-lab/seq2pipe.git && cd seq2pipe
./setup.sh && ./launch.sh --fastq-dir ~/your_data --auto
```

---

## Tech Stack

<p align="center">
  <a href="https://qiime2.org"><img src="https://img.shields.io/badge/QIIME_2-2026.1-44aa99?style=for-the-badge&logo=data:image/svg%2Bxml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PGNpcmNsZSBjeD0iMTAiIGN5PSIxMCIgcj0iNyIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIzIiBmaWxsPSJub25lIi8+PGxpbmUgeDE9IjE1IiB5MT0iMTUiIHgyPSIyMiIgeTI9IjIyIiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjMiLz48L3N2Zz4K&logoColor=white" alt="QIIME 2"></a>
  <a href="https://python.org"><img src="https://img.shields.io/badge/Python-3.10-3776ab?style=for-the-badge&logo=python&logoColor=white" alt="Python"></a>
  <a href="https://ollama.com"><img src="https://img.shields.io/badge/Ollama-LLM-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama"></a>
  <a href="https://streamlit.io"><img src="https://img.shields.io/badge/Streamlit-UI-ff4b4b?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"></a>
</p>
<p align="center">
  <a href="https://benjjneb.github.io/dada2/"><img src="https://img.shields.io/badge/DADA2-denoising-88aa55?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTQgMmMwIDYgMTYgNiAxNiAxMnMtMTYgNi0xNiAxMiIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyLjUiIGZpbGw9Im5vbmUiLz48cGF0aCBkPSJNMjAgMmMwIDYtMTYgNi0xNiAxMnMxNiA2IDE2IDEyIiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjIuNSIgZmlsbD0ibm9uZSIgb3BhY2l0eT0iMC41Ii8+PC9zdmc+Cg==&logoColor=white" alt="DADA2"></a>
  <a href="https://www.arb-silva.de/"><img src="https://img.shields.io/badge/SILVA_138.2-reference-55aa88?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PGVsbGlwc2UgY3g9IjEyIiBjeT0iNiIgcng9IjkiIHJ5PSI0IiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjIiIGZpbGw9Im5vbmUiLz48cGF0aCBkPSJNMyA2djZjMCAyLjIgNCA0IDkgNHM5LTEuOCA5LTRWNiIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyIiBmaWxsPSJub25lIi8+PHBhdGggZD0iTTMgMTJ2NmMwIDIuMiA0IDQgOSA0czktMS44IDktNHYtNiIgc3Ryb2tlPSJ3aGl0ZSIgc3Ryb2tlLXdpZHRoPSIyIiBmaWxsPSJub25lIi8+PC9zdmc+Cg==&logoColor=white" alt="SILVA"></a>
  <a href="https://pandas.pydata.org"><img src="https://img.shields.io/badge/pandas-data-150458?style=flat-square&logo=pandas&logoColor=white" alt="pandas"></a>
  <a href="https://scikit-learn.org"><img src="https://img.shields.io/badge/scikit--learn-ML-f7931e?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn"></a>
  <a href="https://scipy.org"><img src="https://img.shields.io/badge/SciPy-stats-8caae6?style=flat-square&logo=scipy&logoColor=white" alt="SciPy"></a>
  <a href="https://matplotlib.org"><img src="https://img.shields.io/badge/matplotlib-viz-11557c?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHJlY3QgeD0iMyIgeT0iMTQiIHdpZHRoPSI0IiBoZWlnaHQ9IjgiIHJ4PSIxIiBmaWxsPSJ3aGl0ZSIvPjxyZWN0IHg9IjEwIiB5PSI4IiB3aWR0aD0iNCIgaGVpZ2h0PSIxNCIgcng9IjEiIGZpbGw9IndoaXRlIi8+PHJlY3QgeD0iMTciIHk9IjMiIHdpZHRoPSI0IiBoZWlnaHQ9IjE5IiByeD0iMSIgZmlsbD0id2hpdGUiLz48L3N2Zz4K&logoColor=white" alt="matplotlib"></a>
  <a href="https://seaborn.pydata.org"><img src="https://img.shields.io/badge/seaborn-viz-4c72b0?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PHBhdGggZD0iTTIgMTZjMy04IDYgNCAxMC00czUgMiAxMC00IiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjIuNSIgZmlsbD0ibm9uZSIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIi8+PHBhdGggZD0iTTIgMjBjMy04IDYgNCAxMC00czUgMiAxMC00IiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjIuNSIgZmlsbD0ibm9uZSIgc3Ryb2tlLWxpbmVjYXA9InJvdW5kIiBvcGFjaXR5PSIwLjQiLz48L3N2Zz4K&logoColor=white" alt="seaborn"></a>
  <a href="https://networkx.org"><img src="https://img.shields.io/badge/NetworkX-graph-aab71b?style=flat-square&logo=data:image/svg+xml;base64,PHN2ZyB4bWxucz0iaHR0cDovL3d3dy53My5vcmcvMjAwMC9zdmciIHZpZXdCb3g9IjAgMCAyNCAyNCI+PGNpcmNsZSBjeD0iNiIgY3k9IjYiIHI9IjMiIGZpbGw9IndoaXRlIi8+PGNpcmNsZSBjeD0iMTgiIGN5PSI2IiByPSIzIiBmaWxsPSJ3aGl0ZSIvPjxjaXJjbGUgY3g9IjEyIiBjeT0iMTgiIHI9IjMiIGZpbGw9IndoaXRlIi8+PGxpbmUgeDE9IjYiIHkxPSI2IiB4Mj0iMTgiIHkyPSI2IiBzdHJva2U9IndoaXRlIiBzdHJva2Utd2lkdGg9IjEuNSIvPjxsaW5lIHgxPSI2IiB5MT0iNiIgeDI9IjEyIiB5Mj0iMTgiIHN0cm9rZT0id2hpdGUiIHN0cm9rZS13aWR0aD0iMS41Ii8+PGxpbmUgeDE9IjE4IiB5MT0iNiIgeDI9IjEyIiB5Mj0iMTgiIHN0cm9rZT0id2hpdGUiIHN0cm9rZS13aWR0aD0iMS41Ii8+PC9zdmc+Cg==&logoColor=white" alt="NetworkX"></a>
</p>

---

## License

| Repository | License |
|:--|:--|
| seq2pipe / qiime2-assistant | MIT |
| qiime2-manual | All Rights Reserved |

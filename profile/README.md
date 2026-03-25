<h1 align="center">qiime-lab</h1>

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
[![license](https://img.shields.io/badge/license-CC%20BY--NC--SA%204.0-lightgrey?style=flat-square)](https://github.com/qiime-lab/qiime2-manual/blob/main/LICENSE)

QIIME 2 による 16S rRNA 解析の全体像を 25 章で体系的に解説した日本語マニュアル。各ステップが何をしているのか、なぜ必要なのか、どんな選択肢があるのかをメリット・デメリットとともに学べる。DADA2 からANCOM-BC2、q2-boots まで、QIIME 2 2026.5 の最新手法を網羅。内部標準による絶対定量やネガコン除去など実験室の実務もカバー。

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
  <a href="https://qiime2.org"><img src="https://img.shields.io/badge/QIIME_2-2026.5-44aa99?style=for-the-badge" alt="QIIME 2"></a>
  <a href="https://python.org"><img src="https://img.shields.io/badge/-Python-3776ab?style=for-the-badge&logo=python&logoColor=white" alt="Python"></a>
  <a href="https://ollama.com"><img src="https://img.shields.io/badge/-Ollama-000000?style=for-the-badge&logo=ollama&logoColor=white" alt="Ollama"></a>
  <a href="https://streamlit.io"><img src="https://img.shields.io/badge/-Streamlit-ff4b4b?style=for-the-badge&logo=streamlit&logoColor=white" alt="Streamlit"></a>
</p>
<p align="center">
  <a href="https://benjjneb.github.io/dada2/"><img src="https://img.shields.io/badge/-DADA2-88aa55?style=flat-square" alt="DADA2"></a>
  <a href="https://www.arb-silva.de/"><img src="https://img.shields.io/badge/-SILVA_138.2-55aa88?style=flat-square" alt="SILVA"></a>
  <a href="https://pandas.pydata.org"><img src="https://img.shields.io/badge/-pandas-150458?style=flat-square&logo=pandas&logoColor=white" alt="pandas"></a>
  <a href="https://scikit-learn.org"><img src="https://img.shields.io/badge/-scikit--learn-f7931e?style=flat-square&logo=scikitlearn&logoColor=white" alt="scikit-learn"></a>
  <a href="https://scipy.org"><img src="https://img.shields.io/badge/-SciPy-8caae6?style=flat-square&logo=scipy&logoColor=white" alt="SciPy"></a>
  <a href="https://matplotlib.org"><img src="https://img.shields.io/badge/-matplotlib-11557c?style=flat-square" alt="matplotlib"></a>
  <a href="https://seaborn.pydata.org"><img src="https://img.shields.io/badge/-seaborn-4c72b0?style=flat-square" alt="seaborn"></a>
  <a href="https://networkx.org"><img src="https://img.shields.io/badge/-NetworkX-aab71b?style=flat-square" alt="NetworkX"></a>
</p>

---

## License

| Repository | License |
|:--|:--|
| seq2pipe / qiime2-assistant | MIT |
| qiime2-manual | CC BY-NC-SA 4.0 |

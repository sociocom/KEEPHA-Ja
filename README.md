# KEEPHA Japanese Dataset

An annotated corpora for adverse drug reaction (ADR) detection in Japanese.

## Overview / 概要

The Japanese portion of the multilingual corpus of texts, created by the work below, concerning ADRs gathered from diverse sources, including patient fora, social media, and clinical reports in German, French, and Japanese.

以下の論文によって作成された、 ADR に関する多言語テキストコーパスの日本語部分。
ドイツ語、フランス語、日本語の患者フォーラム、ソーシャルメディア、臨床レポートなど、さまざまなソースから収集した。

Lisa Raithel, Hui-Syuan Yeh, Shuntaro Yada, Cyril Grouin, Thomas Lavergne, Aurélie Névéol, Patrick Paroubek, Philippe Thomas, Tomohiro Nishiyama, Sebastian Möller, Eiji Aramaki, Yuji Matsumoto, Roland Roller, and Pierre Zweigenbaum. 2024. [A Dataset for Pharmacovigilance in German, French, and Japanese: Annotating Adverse Drug Reactions across Languages](https://aclanthology.org/2024.lrec-main.36/). In Proceedings of the 2024 Joint International Conference on Computational Linguistics, Language Resources and Evaluation (LREC-COLING 2024), pages 395–414, Torino, Italia. ELRA and ICCL.

This repository contains two more additional corpora not reported in the work above.

本リポジトリには上記論文では報告していない2種類の日本語コーパスサブセットも含む。

## Contents / 内容

- `chiebukuro_brat-202211r`: Yahoo! JAPAN Q&A regarding breast cancer treatments and their adverse reactions / Yahoo!知恵袋の乳がん関連質問のうち副作用に関するQ&A
    - `chiemap.tsv`: A table to link the file names (`qa_NNN`) and the original URL on Yahoo! Q&A. The first 40 characters of the questions are also included to validate the hydration / ファイル名 (`qa_NNN`)とYahoo!知恵袋上のURLとを紐つけた表．復元の検証に使えるよう，質問文の最初40文字も記載されている
- `lexapro_ade-202211r-split`: Tweets regarding a drug Lexapro and its adverse reactions. / レクサプロと関連副作用について言及のあるツイート
- `medner-sc-sm-ja-train-split`: (NEW) Model-generated pseudo-tweets used as the training data in the [MedNLP-SC](https://sociocom.naist.jp/mednlp-sc/) Task of NTCIR-17 / （追加） NTCIT-17 [MedNLP-SC](https://sociocom.naist.jp/mednlp-sc/)のtrainデータセットである擬似ツイート（生成テキスト）
- `MedTxt-CR-Ja-ADE-202211r`: (NEW) Case reports that mention adverse effects among the [MedTxt-CR-JA](https://sociocom.naist.jp/medtxt-en/cr/) corpus / （追加） [MedTxt-CR-Ja](https://sociocom.naist.jp/medtxt/cr/)のうち，副作用に関する記述がある症例報告

## Specs

### Data format

All files follow the [brat standoff format](https://brat.nlplab.org/standoff.html)

### Annotation Scheme

The [annotation guidelines](https://github.com/DFKI-NLP/keepha_annotation_guidelines) (in English) are available.

### Body Text Hydration / 本文の復元

`lexapro_ade-202211r-split` is a tweet corpus from Twitter (currently X) and cannot be redistributed, so the body text is not included.
Please note that you will need to use the Twitter API to get the body text.

`lexapro_ade-202211r-split` は Twitter (現 X) のツイートであり，再配布できないため，本文テキストは含まれていない．
Twitter APIを用いて本文を取得する必要があることに注意されたい．

Also, `chiebukuro_brat-202211r` derives from Yahoo! Chiebukuro (Q&A), [the original corpus of which you need to contract to download](https://www.nii.ac.jp/dsc/idr/yahoo/chiebkr3/Y_chiebukuro.html).
For each URL, the body text can be hydrated by concatenating the question text and its best answer with three new lines.

また，`chiebukuro_brat-202211r` はYahoo!知恵袋から構築しているが，[元コーパスのダウンロードは契約が必要](https://www.nii.ac.jp/dsc/idr/yahoo/chiebkr3/Y_chiebukuro.html)である．
各URLにつき，その本文は質問文とベストアンサーとを改行3個で結合することで復元できる．

## Contributor

- [Shuntaro Yada](https://shuntaroy.com) 
- Narumi Tokunaga
- Yuji Matsumoto
- Eiji Aramaki
- All the KEEPHA team members

## License

MIT

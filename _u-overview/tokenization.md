---
layout: base
title:  'Tokenization and Word Segmentation'
permalink: u/overview/tokenization.html
udver: '2'
---

# Tokenization and Word Segmentation

UDのタグ付けは統語論における語彙主義 (lexicalist) の観点に基づいており，依存関係 (dependency relations) が _words_ 間で保持されている．よって，形態論的な素性 (morphological features) は語の属性として符号化されており，語を形態素 (morpheme) に分割することはしない. ただし，タグ付けの基本単位 (basic unit) は, _syntactic_ な語 (音韻，書記ではなく) であることに注意されたい．これは， スペイン語を _dámelo_ = _da me lo_ のように接語 (clitics) を分割し，さらに，フランス語 _au_ = _à le_ のように縮約 (contraction) を元に戻したい，といった理由に基づく．このような事例は_multiword tokens_  と呼ばれるが，それは，単一の書記  _token_ が複数の (統語的)  _words_ に対応するからである．例外として，他の方法を採り，複数の書記トークン (orthographic tokens) を単一の統語的な語へ統合する必要があるかもしれない．UDのガイドラインのv2以降では，_20 000_ などの数的表現や _e. g._ などの略語といった，特定の現象クラスに_multitoken words_ が適用されるが，これは，当該の現象が広く認められ，かつ言語固有のドキュメンテーションで特定された場合に限られる．

Since word segmentation in general is a non-trivial task in many languages, and since the usefulness of tools trained on treebank data ultimately depends on how well the word segmentation can be reproduced for new data, it is important to document the principles of word segmentation for each language.
The nature of this documentation will vary from one language to the next, depending on properties of the language and
the writing system. For languages where word segmentation can be performed by a simple script given white-space and 
punctuation, only the words need to be represented in the treebank. 
For languages not using white-space at all, such as Chinese and Japanese, a complex word segmentation algorithm has 
to be employed, but there is no need to represent the basic character sequence in the treebank since it is completely 
recoverable from the word representation. By contrast, in languages where the mapping between white-space delimited 
_tokens_ and syntactic _words_ is highly ambiguous, such as Arabic and Hebrew, we provide the option of including 
both tokens and words in the treebank using a two-level indexing scheme described in the 
<a href="../../format.html">CoNLL-U format</a> section. 
The morphological and syntactic annotation is only defined at the word level, but a heuristic mapping to the token level
can usually be provided. 

多くの言語において，語の分割 (word segmentation) は概して容易な作業ではなく，究極的には，新規のデータに対して語の分割をどれだけ再現できるかがツリーバンクの道具立ての有用性を決定づけるため，語の分割に関する原則を各言語についてドキュメントしておくことが重要である．
当該言語の特徴と筆記体系によって，ドキュメンテーションのあり方は言語によって変わる．語の分割が単に空白や句読点で済ませられる言語は，語のみをツリーバンクに表示すればよい．空白を入れない中国語や日本語といった言語では，分割に関する複雑なアルゴリズムを援用しなければならないが，語を表示したものから復元が完全に可能であるため，基本的な語の並びを改めて表示する必要はない．その一方で，空白によって特定できる _tokens_ と，統語的な _words_ が多分に曖昧であるようなアラビア語やヘブライ語といった言語では，ツリーバンク内のトークンと語の両方を包括するような措置が取られ，これには， <a href="../../format.html">CoNLL-U format</a> のセクションに示される，２段階のインデックス・スキーマ (indexing scheme) が用いられる．
形態論・統語論のタグ付けの定義は語レベルでのみ行われるが，利便性のため，トークンレベルでも行うことが慣例である．
<!--The morphological and syntactic annotation is only defined at the word level, but a heuristic mapping to the token level
can usually be provided. -->

このドキュメンテーションを言語固有のものに拡張する場合，トークン化 (tokenization) と語の分割がどのように各言語で行われたかを記載する必要がある (トークン化の標準的なスキーマがあれば，それを参照)．さらには，以下の疑問にも答えるべきである．

* 語の内部に空白が規則的に発生するだろうか?  (これは，ベトナム語といった，空白が語の境界ではなく音節 (syllable) の境界を示すのに用いられる言語に限られる.)
* 空白が例外的に (複数トークンの) 語に発生するだろうか? そうであれば，どの場合に起こるかを特定しよう (例えば，数や略語など)．
* ツリーバンクには語と同様，(複数語から成る) トークンを含めるだろうか? そうであれば，どの場合に含むのかを特定しよう (例えば，接語や縮約など).
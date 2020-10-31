---
layout: postag
title: 'SYM'
shortdef: 'symbol'
udver: '2'
---

### Definition

シンボル (symbol) は語のようなものを指し，形式や機能が通常の語とは異なる．

シンボルの多くは，[punctuation](PUNCT) のようなアルファベット・数字ではない特殊文字を含む．句読点とシンボルの違いは，通常の語と置き換え可能か否にある．通貨のシンボル (e.g. _$ 75_) は，_seventy-five dollars_と同一である．

数学の演算子は他のシンボルとは異なるグループを形成する．

他のシンボルのグループには顔文字 (emoticons) や絵文字 (emoji) がある

アルファベット・数字のみから成る文字列はシンボルではなく，[proper nouns](PROPN) である: _130XE_, _DC10_; 他の場合は，特殊文字を文字を含んでいても (`SYM`ではなく) `PROPN`としてタグ付けされる: _DC-10_. 
同様に，略語 (abbreviations) はシンボルではなく，完全な形式の品詞として分析される．例えば，_Mr._ (mister), _kg_ (kilogram), _km_ (kilometer) や_Dr_ (Doctor) は [nouns](NOUN) としてタグ付けされる．_UN_や_NATO_のように頭文字語 (acronym) で表される固有名は [proper nouns](PROPN) としてタグ付けされる．

箇条書きに用いられる記号 _(•, ‣)_ はシンボルではなく，句読点である．

### Examples

- _$, %, §, ©_
- _+, −, ×, ÷, =, <, >_
- :), ♥‿♥, 😝
- _john.doe@universal.org, http://universaldependencies.org/, 1-800-COMPANY_

---
layout: postag
title: 'PUNCT'
shortdef: 'punctuation'
udver: '2'
---

### Definition

句読点 (punctuations) はアルファベットでない文字で，印刷物にある言語ユニットを限定するのに用いられる文字のグループを指す．

句読点は_$_，_%_や_§_といった記号を含めず，これらは代わりに [SYM]() としてタグ付けされる．(ヒント: _dollar_や_percent_のように，発音したものに相当する語である場合，`PUNCT`ではなく`SYM`としてタグ付けされる．)

話し言葉コーパスにはポーズを表す記号があり，笑い声や他の音が含まれる; これらは同様に句読点として扱われるが，トークンの文字が全てアルファベット以外である必要は必ずしもない.

### Examples

- ピリオド (period): _<b>.</b>_
- カンマ (comma): _<b>,</b>_
- 括弧 (parentheses): _<b>()</b>_
 
### References

- [Wikipedia](http://en.wikipedia.org/wiki/Punctuation)

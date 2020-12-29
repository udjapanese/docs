---
layout: feature
title: 'Poss'
shortdef: 'possessive'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Yes">Yes</a></td>
</tr>
</table>

この素性はブール型であり，代名詞か限定詞もしくは形容詞かを決定する．また，この素性は当該の語が所有格 (possessive) かどうかを判別する.

多くのタグセットでは複数ある代名詞のタイプの1つとして"possessive"を備えるが，`Poss`は他の代名詞のタイプから独立していため[PronType]()とは意図的に区別される．複数の代名詞のタイプは任意的に所有格をとり，形容詞も同様である．

### <a name="Yes">`Yes`</a>: 所有格である

値`No`は存在しない．当該の語が所有格でなければ，素性`Poss`はそもそも`FEAT`カラムに記載されないからである (空の値は`No`の意味をもつ)

#### 例

* [en] _my, your, his, mine, yours, whose_
* [cs] possessive determiners: _můj, tvůj, jeho, její, náš, váš, svůj, čí, jejichž_
* [cs] possessive adjectives: _otcův_ "father's", _matčin_ "mother's"

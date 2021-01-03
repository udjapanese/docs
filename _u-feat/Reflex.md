---
layout: feature
title: 'Reflex'
shortdef: 'reflexive'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Yes">Yes</a></td>
</tr>
</table>

素性`Reflex`はブール型であり，典型的には[代名詞 (pronouns)](u-pos/PRON) や[限定詞 (determiners)](u-pos/DET) に適用される．この素性は当該の語が再帰的 (reflexive) であるかどうかを判別する (i.e. 節主語を指示するかどうか).

多くのタグセットは代名詞のタイプとして"reflexive"を備えるが，その素性は[PronType]() とは意図的に区別される．この素性が代名詞と限定詞で用いられる場合，[Person]() の素性に関して区別するかどうかに関わらず (区別する言語としない言語がある)，それは`PronType=Prs`に結合されるだろう.

いくつかの言語には再帰動詞 (reflexive verbs) が存在するが，それは実際には再帰代名詞と融合した動詞 (fused verbs) である (その例にはスペイン語の_despertarse_やロシア語の_проснуться_があり，両者は“to wake up”を意味する)．よって，これらの事例は，融合したトークンが2つの統語的な語に分離される．そのうち1つは再帰代名詞である．

### <a name="Yes">`Yes`</a>: 再帰的である

この素性には`No`の値が存在しない．当該の語が再帰的でなければ，素性`Reflex`はそもそも`FEAT`カラムに記載されないからである．(すなわち，空の値が`No`を意味する.)

#### 例

* [cs] 再帰人称代名詞: _se, si_; 再帰所有代名詞: _svůj_

---
layout: feature
title: 'Polarity'
shortdef: 'polarity'
redirect_from:
  - "u/feat/Negativeness.html"
  - "u/feat/Negative.html"
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Neg">Neg</a></td>
  <td><a href="#Pos">Pos</a></td>
</tr>
</table>

極性 (polarity) は，典型的には[動詞 (verbs)](u-pos/VERB)，[形容詞 (adjectives)](u-pos/ADJ) の素性であるが, 拘束形態素を用いて否定を表す言語においては[副詞 (adverbs)](u-pos/ADV) や[名詞(nouns)](u-pos/NOUN) も極性の素性を持つ．機能語を用いて否定を表す言語において，`PronType=Neg`の標示をうけるpro-form (下記参照) を持たない限り，`Polarity`はその機能語を標示するのに用いられる．

正の極性 (肯定) が形態素によって明示的に符号化されるのは稀である．値 `Polarity=Pos` は通常，見出し語 (lemma) に否定形を持つものの，否定形式として使っていないこと示すために用いられる．否定が可能であるが，否定形の使用が稀であるような語に対して，`Polarity=Pos`を用いるかどうかは任意である．

例えば，チェコ語のあらゆる動詞と形容詞は接頭辞 (prefix) _ne-_を用いて否定が可能である．理論的には名詞も"当該名詞が指示するもの以外"という意味で否定が可能であるが，あまり見られない用法であるため，肯定形をとる名詞すべてに`Polarity=Pos`タグを施す必要はない．言語固有のドキュメンテーションにおいては，どの状況下で正の極性がタグ付けされるかを定めておくべきである．

英語では，動詞は[不変化詞 (particle)](u-pos/PART) の_not_を用いて否定される．形容詞は接頭辞 (prefix) によっても否定されるが，チェコ語ではこのようなプロセスの生産的が低い _(wise &ndash; unwise, probable &ndash; improbable)_.

`Polarity=Neg`は[PronType]()`=Neg`とは異なることに注意されたい．代名詞や代名詞的な品詞では，動詞や形容詞のような2値の対立が存在しない ("肯定代名詞 (affirmative pronoun)" のようなものは存在しない).

素性`Polarity`は素性[間投詞 (interjections)](u-pos/INTJ) について，_yes_ と _no_ の返答を区別する役割も持つ.

### <a name="Pos">`Pos`</a>: 肯定 (positive, affirmative)

#### 例

* [cs] _<b>přišel</b>_ “he came”
* [cs] _<b>velký</b>_ “big”
* [en] _<b>yes</b>_

### <a name="Neg">`Neg`</a>: 否定

#### 例

* [cs] _<b>nepřišel</b>_ “he did not come”
* [cs] _<b>nevelký</b>_ “not big”
* [en] _<b>not</b>_
* [en] _<b>no</b>_ as in _no, I don't think so;_ but not as in _we have no bananas_

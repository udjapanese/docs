---
layout: feature
title: 'Gender'
shortdef: 'gender'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Com">Com</a></td>
  <td><a href="#Fem">Fem</a></td>
  <td><a href="#Masc">Masc</a></td>
  <td><a href="#Neut">Neut</a></td>
</tr>
</table>

`Gender` は[名詞 (nouns)](u-pos/NOUN) の語彙的素性であり，名詞との一致を標示する他の品詞 ([代名詞 (pronouns)](u-pos/PRON)，[形容詞 (adjectives)](u-pos/ADJ)，[限定詞 (determiners)](u-pos/DET)，[数詞 (numerals)](u-pos/NUM)，[動詞 (verbs)](u-pos/VERB)) における屈折素性でもある．英語では，性 (gender) は人称代名詞 _(he / she / it)_ の選択についてにのみ影響を与えるため，素性`Gender`は英語のタグセットでエンコードしないのが通例である．

これに関連する素性として，[有生性 (Animacy)]() も参照されたい．

アフリカの言語は[名詞クラス (noun classes)](NounClass) に類似した素性をもつ: 平たい物体や細長い物体といったものでも文法範疇から区別されるかもしれない．

### <a name="Masc">`Masc`</a>: 男性 (masculine gender)

男性の人物を指示する名詞は男性 (masculine) の性 (gender) をとる．他の名詞も，性別 (sex) について無関係だが文法的に男性をとることがある．

#### 例

* [cs] _<b>hrad</b>_ "castle"

### <a name="Fem">`Fem`</a>: 女性 (feminine gender)

女性の人物を指示する名詞は女性 (feminine) の性 (gender) をとる．他の名詞も，性別 (sex) について無関係だが文法的に女性をとることがある．

#### 例

* [de] _<b>Burg</b>_ "castle"

### <a name="Neut">`Neut`</a>: 中性 (neuter gender)

性 (gender) を男性/女性についてのみ区別する言語がある一方で，(文法的に) そのどちらでもない3番目の性を持つ言語もある．

#### 例

* [en] _<b>castle</b>_
* [cs] _<b>dítě</b>_ "child"

### <a name="Com">`Com`</a>: 汎性 (common gender)

いくつかの言語では，大抵の場合で男性/女性の区別を設けないが，中性 (neuter) かそうでないか (non-neuter) については区別するものがある (スウェーデン語における neutrum/utrum の区別)．非中性的なものは汎性 (common gender) と呼ばれる．

汎性は結合した値`Gender=Fem,Masc`として表現できるだろうが，`Com`の独立性は保持される．結合した値は例外的に用いられるべきであって，文法内で体系的に起こるものに対しては適用すべきでない．上記のガイドラインを特定の言語向けに拡張するのであれば，当該言語において値`Com`の使用が適切かどうかを決定すべきである．

値`Com`について注意が必要なのは，`Masc`と`Fem`を区別する言語において (コンテクストを参照しない限り) 語単体からは性が分からないような事例へ適用するようには意図されていない，ということである．

例えば，スペイン語では名詞を男性と女性に区別するため，全ての名詞は`Masc`もしくは`Fem`として分類される．形容詞は性 (および数) について名詞と一致し，_-o / -a_を交替させることで区別される．ただし，_grande_ もしくは _feliz_ のように，両方の性に対して１つの形式しかもたないような名詞も存在し，これらはコンテクストを参照しない限りどちらか性であるかが判明しない．とはいえ，それらの形容詞は必ず男性か女性かのどちらかをとる (_una ciudad grande_では女性，_un puerto grande_では男性) ため，_grande_を`Gender=Com`とタグ付けするわけにはいかない．代替案としては，そもそも性の素性を仮定しない (_grande_が性に関して屈折しないと考える) か，コンテクスト上に生起する_grande_のインスタンスを男性または女性としてタグ付けすることが考えられる．

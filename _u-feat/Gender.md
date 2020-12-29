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

`Gender` は[名詞 (nouns)](u-pos/NOUN)の語彙的素性であり，名詞との一致を標示する他の品詞 ([代名詞 (pronouns)](u-pos/PRON), [形容詞 (adjectives)](u-pos/ADJ), [限定詞 (determiners)](u-pos/DET), [数詞 (numerals)](u-pos/NUM), [動詞 (verbs)](u-pos/VERB)) における屈折素性でもある．英語では性 (gender) が影響を及ぼすのは人称代名詞 _(he / she / it)_ の選択のみに限定されるため，素性`Gender`は英語のタグセットでエンコードしないのが通例である．

これに関連する素性として，[有生性 (Animacy)]()も参照されたい．

アフリカの言語は[名詞クラス (noun classes)](NounClass)に類似した素性をもつ: 平たい物体や細長い物体といったものでも文法範疇から区別されるかもしれない．

### <a name="Masc">`Masc`</a>: 男性 (masculine gender)

男性 (male person) を指示する名詞は性 (gender) として男性 (masculine) をとる．他の名詞も，性別 (sex) には関係せず文法的に男性をとることがある．

#### 例

* [cs] _<b>hrad</b>_ "castle"

### <a name="Fem">`Fem`</a>: 女性 (feminine gender)

女性 (female person) を指示する名詞は性 (gender) として女性 (feminine) をとる．他の名詞も，性別 (sex) には関係せず文法的に女性をとることがある．

#### 例

* [de] _<b>Burg</b>_ "castle"

### <a name="Neut">`Neut`</a>: 中性 (neuter gender)

性 (gender) を男性/女性についてのみ区別する言語がある一方で，(文法的に) そのどちらでもない3番目の性を持つ言語もある．

#### 例

* [en] _<b>castle</b>_
* [cs] _<b>dítě</b>_ "child"

### <a name="Com">`Com`</a>: 汎性 (common gender)

いくつかの言語では，男性/女性の区別を大抵の場合で行わないが中性 (neuter) かそうでないか (non-neuter) については区別するものがある．非中性的なものは汎性 (common gender) と呼ばれる．

汎性は結合した値`Gender=Fem,Masc`として表現できるだろうが，`Com`を独立した値として保持しておく．結合した値は例外的に用いられるべきであって，文法内で体系的に起こるものに対しては適用すべきでない．上記のガイドラインを特定の言語向けに拡張するのであれば，当該言語において値`Com`が適切かどうかを決定すべきである．

注意が必要なことだが，値`Com`は，`Masc`と`Fem`を区別する言語において，(コンテクストを参照しない限り) 語単体からは性が分からないような事例へ適用するようには意図されていない．<!--日本語ダサいな．．-->

例えば，スペイン語では名詞は男性と女性に区別されるため，全ての名詞は`Masc`もしくは`Fem`として分類される．形容詞は性 (および数) について名詞と一致し，_-o / -a_を交替させることで区別される．ただし，_grande_ もしくは _feliz_ のように，両方の性に対して１つの形式しかもたないような名刺が存在する．この場合，コンテクストを参照しない限りそれが男性か女性のどちらかが分からない．とはいえ，それらの形容詞は男性か女性かのどちらかである (_una ciudad grande_では女性，_un puerto grande_では男性) ため，_grande_を`Gender=Com`とタグ付けするわけにはいかない．代替案としては，そもそも性素性を仮定しない (_grande_が性に関して屈折しないと考える) か，コンテクスト上に現れる_grande_のインスタンスを男性または女性としてタグ付けすることが考えられる．

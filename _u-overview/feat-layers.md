---
layout: base
title:  'Layered universal features'
generated: 'false'
permalink: u/overview/feat-layers.html
udver: '2'
---

# Layered universal features

言語によっては，同一の語に対して複数の素性 (features)  が標示される (marked) 場合があり，これを，素性の _layers_ が存在するものと考える． 個々のレイヤー (layers) の正確な意味は，言語に依存する．

例えば，所有形容詞 (possessive adjectives) ，限定詞 (determiners) や代名詞 (pronouns) は [u-feat/Gender]() で2つの異なる値 (values) を持ち， [u-feat/Number]() でも2つの異なる値を持つことがある．値の1つは修飾された (所有された) 名詞 (noun) との一致 (agreement) によって決定される．これは，他の (所有を表さない) 形容詞や限定詞といった，性 (gender) と数 (number) に関して修飾した名詞と一致を起こさないものと並行的に考えることができる．他の値は語彙的に決定されるが，これは，所有者 (possessor) 自身の性質である．
以下の表では，次のことを示している；英語では所有者の性と数のみを区別する；ヒンディー語は性の一致を区別し，数は一致と所有者の両方から区別される (ヒンディー語には中性 (neuter) が存在しない)；ドイツ語では，性と数のどちらも，一致と所有者の両方から区別される (ドイツ語において，主格 (nominative) だけではなく与格 (dative) や対格 (accusative) 形をみたとき，変化はより鮮明となる)．

<table>
  <tr>
    <td>Possessor / Agreement</td>
    <td>&nbsp;</td>
    <td>Sing Masc</td>
    <td>Sing Fem</td>
    <td>Sing Neut</td>
    <td>Plur Masc</td>
    <td>Plur Fem</td>
  </tr>
  <tr>
    <td>Sing Masc</td>
    <td>[en]<br/>[de]<br/>[hi]</td>
    <td><span style='color:red'>his</span> son<br/><span style='color:red'>sein</span> Sohn<br/><span style='color:red'>usakā</span> bēṭā</td>
    <td><span style='color:red'>his</span> daughter<br/><span style='color:red'>seine</span> Tochter<br/><span style='color:red'>usakī</span> bēṭī</td>
    <td><span style='color:red'>his</span> house<br/><span style='color:red'>sein</span> Haus<br/>&nbsp;</td>
    <td><span style='color:red'>his</span> sons<br/><span style='color:red'>seine</span> Söhne<br/><span style='color:red'>usakē</span> bēṭē</td>
    <td><span style='color:red'>his</span> daughters<br/><span style='color:red'>seine</span> Töchter<br/><span style='color:red'>usakī</span> bēṭiyām̐</td>
  </tr>
  <tr>
    <td>Sing Fem</td>
    <td>[en]<br/>[de]<br/>[hi]</td>
    <td><span style='color:red'>her</span> son<br/><span style='color:red'>ihr</span> Sohn<br/><span style='color:red'>usakā</span> bēṭā</td>
    <td><span style='color:red'>her</span> daughter<br/><span style='color:red'>ihre</span> Tochter<br/><span style='color:red'>usakī</span> bēṭī</td>
    <td><span style='color:red'>her</span> house<br/><span style='color:red'>ihr</span> Haus<br/>&nbsp;</td>
    <td><span style='color:red'>her</span> sons<br/><span style='color:red'>ihre</span> Söhne<br/><span style='color:red'>usakē</span> bēṭē</td>
    <td><span style='color:red'>her</span> daughters<br/><span style='color:red'>ihre</span> Töchter<br/><span style='color:red'>usakī</span> bēṭiyām̐</td>
  </tr>
  <tr>
    <td>Sing Neut</td>
    <td>[en]<br/>[de]<br/>&nbsp;</td>
    <td><span style='color:red'>its</span> son<br/><span style='color:red'>sein</span> Sohn<br/>&nbsp;</td>
    <td><span style='color:red'>its</span> daughter<br/><span style='color:red'>seine</span> Tochter<br/>&nbsp;</td>
    <td><span style='color:red'>its</span> house<br/><span style='color:red'>sein</span> Haus<br/>&nbsp;</td>
    <td><span style='color:red'>its</span> sons<br/><span style='color:red'>seine</span> Söhne<br/>&nbsp;</td>
    <td><span style='color:red'>its</span> daughters<br/><span style='color:red'>seine</span> Töchter<br/>&nbsp;</td>
  </tr>
  <tr>
    <td>Plur</td>
    <td>[en]<br/>[de]<br/>[hi]</td>
    <td><span style='color:red'>their</span> son<br/><span style='color:red'>ihr</span> Sohn<br/><span style='color:red'>unakā</span> bēṭā</td>
    <td><span style='color:red'>their</span> daughter<br/><span style='color:red'>ihre</span> Tochter<br/><span style='color:red'>unakī</span> bēṭī</td>
    <td><span style='color:red'>their</span> house<br/><span style='color:red'>ihr</span> Haus<br/>&nbsp;</td>
    <td><span style='color:red'>their</span> sons<br/><span style='color:red'>ihre</span> Söhne<br/><span style='color:red'>unakē</span> bēṭē</td>
    <td><span style='color:red'>their</span> daughters<br/><span style='color:red'>ihre</span> Töchter<br/><span style='color:red'>unakī</span> bēṭiyām̐</td>
  </tr>
</table>

ある言語で素性がレイヤーを成すとき，素性の名前はレイヤーを示す必要がある．また，レイヤーを区別するため，例えば所有者の性を `Gender[psor]` のようにして，大括弧 [ ] に表される識別子が用いられる. レイヤーの識別子は，小文字の英字 `[a-z]` か，もしくは `[0-9]` から構成することが推奨される．レイヤー，レイヤーの意味や識別子は，本ドキュメンテーションで用いられる言語固有の拡張子 (language-specific extension) <!--extensionはUDのタグを指すと思ったので，拡張子と呼ぶことにしています--> によって定義されなければならない．各レイヤーにある素性に関して，1つのレイヤーはデフォルトとして定義されることがあり，その場合は，例えば  `Gender=Masc|Gender[psor]=Fem` のように，対応する素性が識別子なしで現れることになる．

<strong>以下，実際のコーパスで確認されたレイヤーの素性の例を列挙しておく．<!--These may be used as inspiration or they may be used _as-is_ in treebanks for which they are found appropriate.--> また，ツリーバンクが本セクションで示したレイヤーの素性を用いたとしても，特定言語のドキュメンテーションにおいては，レイヤーが何なのかを説明することが望ましい．

## Gender[psor]

所有形容詞や代名詞は2つの異なる <a href="u/feat/Gender.html">性</a> を持つことがある: 1つは所有物 (被修飾名詞との性の一致) であり，もう1つは所有者 (語彙的素性，固有の性) である．

素性  `Gender[psor]` は所有者の性を表す．

以下のチェコ語の例では，男性 (masuline) の Gender[psor] が 接尾辞 <I>-</I><I>ův, -ova, -ovo,</I> をいずれかを用いることを示しており，女性 (feminine) の Gender[psor] が <I>-</I><I>in, -ina, -ino</I> のいずれかを用いることを示している．

### Masc: masculine possessor

例:
[cs]
<span style='color: red'><I>otcův syn</I></span> (father's son; `Gender=Masc|Gender[psor]=Masc`);
<span style='color: red'><I>otcova dcera</I></span> (father's daughter; `Gender=Fem|Gender[psor]=Masc`);
<span style='color: red'><I>otcovo dítě</I></span> (father's child; `Gender=Neut|Gender[psor]=Masc`).

### Fem: feminine possessor

例:
[cs]
<span style='color: red'><I>matčin syn</I></span> (mother's son; `Gender=Masc|Gender[psor]=Fem`);
<span style='color: red'><I>matčina dcera</I></span> (mother's daughter; `Gender=Fem|Gender[psor]=Fem`);
<span style='color: red'><I>matčino dítě</I></span> (mother's child; `Gender=Neut|Gender[psor]=Fem`).

他の言語 (ヘブライ語，アラビア語) では，所有者の性と数は語彙自体の素性よりも，一致によって決定される．

例: [he] <i><span style='color:red'>HKPH</span> FL HARC</i> (国の周囲 (perimeter of country) ).
2つの名詞の素性は以下の通り:
perimeter.`Gender=Masc|Gender[psor]=Fem|Number=Sing|Number[psor]=Sing`
country.`Definite=Def|Gender=Fem|Number=Sing`.


_perimeter_  の素性 [psor]  は，所有者である _country._ との一致から決定される．

(これは，上記の例の部分的な記述である．_HKPH_ は多数の形態論的分析が行われ，男性・単数のレイヤーと，女性・単数のレイヤーに分かれる．2つの一致素性のレイヤーを見つけて個々の一致パターンに同定できれば，正しい形態分析が可能となる．<!-- right morphosyntactic analysis-->)
## Number[psor]

所有形は2つの異なった <a href="u/feat/Number.html">数</a> を持つことがある: 1つは所有物 (被修飾名詞との数の一致) であり，もう1つは所有者である．
素性 `Number[psor]` は所有者の数を表す．

### Sing: singular possessor

例:
[en]
<i><span style='color: red'>my, his, her, its</span>;</i>
[cs]
<i><span style='color: red'>můj</span> pes</i>
(my dog; `Number=Sing|Number[psor]=Sing`);
<i><span style='color: red'>mí</span> psi</i>
(my dogs; `Number=Plur|Number[psor]=Sing`).

### Plur: plural possessor

例:
[en]
<i><span style='color: red'>our, their</span>;</i>
[cs]
<i><span style='color: red'>náš</span> pes</i>
(our dog; `Number=Sing|Number[psor]=Plur`);
<i><span style='color: red'>naši</span> psi</i>
(our dogs; `Number=Plur|Number[psor]=Plur`).

## Person[psor]

所有者の人称 (person) はハンガリー語の名詞などには標示される．これらの名詞形は，所有代名詞 + 名詞 として英語に翻訳されるだろう．

これは、デフォルトの <a href="u/feat/Person.html">人称</a> が通常，名詞に標示されないとしても，レイヤー素性と考えることが合理的だろう．名詞は，動詞との関係 (名詞と人称の一致を行う場合がある) により，常に3人称として現れる．よって，デフォルトの人称が表層で形態的に標示されず，デフォルトの  `Person` が名詞の素性に現れなかったとしても，所有者を標示するためにデフォルトのレイヤーを用いるべきではない．デフォルトのレイヤーを濫用することで，名詞が置き換わる人称代名詞と並行的にタグ付けを扱えなくなるからである． 

一方で，所有形の限定詞/代名詞の人称に対して独立した `[psor]` のレイヤーを設けることは行わないだろう． それらは動詞ではなく名詞を修飾し，おそらく `Person` を一つしか持たず，その素性は語彙的なものであろう (ハンガリー語の名詞では，`Person[psor]`  は屈折する (inflectional) であるが) . また，通常それらは動詞ではなく名詞を修飾するため，動詞との一致は役割をもたない．さらに，いくつかの言語では，所有代名詞が人称代名詞の属格 (genitive) <a href="u/feat/Case.html">case</a> と同一であり，これらは当然，主格 (nominative) においても同じ  `Person` を持っている．

### 1: first person possessor

例:
[hu]
<I>kutya</I> = dog;
<span style='color: red'><I>kutyám</I></span> = my dog;
<span style='color: red'><I>kutyánk</I></span> = our dog.

### 2: second person possessor

例:
[hu]
<I>kutya</I> = dog;
<span style='color: red'><I>kutyád</I></span> = your.Sing dog;
<span style='color: red'><I>kutyátok</I></span> = your.Plur dog.

### 3: third person possessor

例:
[hu]
<I>kutya</I> = dog;
<span style='color: red'><I>kutyája</I></span> = his/her/its dog;
<span style='color: red'><I>kutyájuk</I></span> = their dog.

<i>János <span style='color:red'>csontja</span></i><br/>
lit. John <span style='color:red'>his-bone</span><br/>
John's bone

<i>János <span style='color:red'>csontjai</span></i><br/>
lit. John <span style='color:red'>his-bones</span><br/>
John's bones

<i>Péternek sok <span style='color:red'>pénze</span> van.</i><br/>
lit. to-Peter much <span style='color:red'>his-money</span> there-is<br/>
Peter has a lot of money.

## Number[psee]

この素性はハンガリー語に特有であり，所有物の (所有された名詞句の) 数を示す．ハンガリー語は名詞の屈折に関して3タイプの数がある．:

* 名詞の数 (屈折し，一致を行わない). 
* 名詞を所有する，その所有者の数 (屈折し，発音されるかもしれない<!--表層に現れるかもしれない?-->所有者と一致を行う).
* 所有物の名詞を表す，文脈から与えられた指示対象 (referent) の数 (これを照応所有 (anaphoric possessive) と呼ぶ; ある意味で，これは一致素性であるが，主辞の名詞 (所有物) は文において発音されない)．
 
Multext-East にあるハンガリー語のレキシコンからの例:

* <I>könnyedén</I> (SSS)
  * <I>könny</I> = a tear (singular)
  * <I>könnyed</I> = your tear (singular owner)
  * <I>könnyedé</I> = (possession) of your tear (singular possession)
  * <I>könnyedén</I> = (on the possession) of your tear (superessive case)
* <I>ellenfeleié</I> (PSS)
  * <I>ellenfél</I> = an opponent (singular)
  * <I>ellenfele</I> = his/her/its opponent (singular owner)
  * <I>ellenfelei</I> = his/her/its opponents (core plural, singular owner)
  * <I>ellenfeleié</I> = (possession) of his/her/its opponents (singular possession)
* <I>életeké</I> (SPS)
  * <I>él</I> = point (singular)
  * <I>élek</I> = points (plural)
  * <I>élén</I> = his/her/its point (singular owner)
  * <I>élünk</I> = our point (plural owner)
  * <I>életeké</I> = (possession) of our point (singular possession)
* <I>tárgyalópartnereinkét</I> (PPS)
  * <I>tárgyalópartner</I> = negotiator (singular)
  * <I>tárgyalópartnerei</I> = his/her/its negotiators (plural, singular owner)
  * <I>tárgyalópartnereinkét</I> = (possession) of our negotiators (plural, plural owner, singular possession, accusative case)

ただし，複数の所有 (plural possession) <!--照応所有の例なので，この訳だとわかりづらいかも-->が標示された語は極めて稀である．以下はMultext-Eastからの例であるが，Columbusにある標示は所有者を表すのではなく，複数の所有を表していることに注意されたい．

* <I>Kolumbuszéinál</I>
  * <I>Kolumbusz</I> = Columbus (singular)
  * <I>Kolumbuszéi</I> = (possessions) of Columbus (plural possession)
  * <I>Kolumbuszéinál</I> = (at the possessions) of Columbus (adessive case)

詳しくは <a href="http://ling.auf.net/lingbuzz/002042/current.pdf">Éva Dékány (2014): The syntax of anaphoric possessives in Hungarian</a> を参照されたい:

In anaphoric possessives the possessed noun, the head of the whole nominal phrase,
is not pronounced, and its reference has to be recovered from the context.
The possessor in Hungarian anaphoric possessives has to bear the _-é_ suffix.

Since `Number[psee]=Plur` is extremely rare, this feature is not so important
for distinguishing singular and plural possessions. However, the mere presence
of `Number[psee]=Sing` informs that there is the _-é_ suffix and thus that
there is an unpronounced possession.

## Layered verb agreement in Basque

印欧語 (Indo-European languages) の多くの言語では，動詞は主語 (subject) の人称と数に一致しなければらない．これは，動詞の [u-feat/Person]() と [u-feat/Number]() によって示される． 

バスク語 (Basque) のいくつかの動詞では，最大3つの項 (arguments) の数と人称に一致する必要がある: 絶対格 (absolutive) の項 (自動詞の主語，他動詞の目的語)，能格 (ergative) の項 (他動詞の主語)，与格 (dative) の項 (間接目的語). 

絶対格の一致をデフォルトとして扱い，`Person` and `Number` を識別子なしに用いることが可能である．そのとき，他の2つの項のいずれかがある場合は `Person[erg]`， `Number[erg]` ，`Person[dat]`， `Number[dat]` をそれぞれ用いる．　

Example: <i><span style='color:red'>nahi dizkiegu</span>,</i> lemma = <i>nahi_izan</i>,
feats = `Number=Plur|Number[dat]=Plur|Number[erg]=Plur|Person=3|Person[dat]=3|Person[erg]=1`
(we want them to them).

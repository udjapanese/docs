---
layout: relation
title: 'flat'
shortdef: 'flat multiword expression'
udver: '2'
---

`flat`は，UDにおいて複合表現 (multiword expressions; MWEs) の3つの関係のうちの1つを表す関係である．(他の2つは [fixed]() と [compound]()). 関係`flat`は名称 (_Hillary Rodham Clinton_) や日付 (_24 December_) といった，外心的 (exocentric; 主辞を欠く) な準固定的MWE (semi-fixed MWEs) に用いられる．これは，完全に固定的な (機能語のような) MWE (_in spite of_) や内心的 (endocentric; 主辞を持つ) なMWE (_apple pie_のような) [複合語 (compound)]() と対比される．

平板型MWW (flat MWEs) は平板構造としてタグ付けされ，後続する語は全て先頭の語に`flat`ラベルを用いて付加させる．これは，平板構造を持つ表現は内部の統語構造を持たず，構造のタグ付けが恣意的になってしまうという想定にもとづく．どのような言語であっても平板型MWEには一貫したタグ付けを与えることが非常に望ましい．

以下，言語間で共通する[平板型 (flat)]() の最も一般な用法をみることにする．意味的には等しい表現であっても言語によっては標準的な統語構造が異なる場合もある (また，同じ言語内であっても) ため，異なる分析を要することもある．

## 名称 (Names) 

多くの言語では複合表現から成る固有名のうち，内部構造が不明瞭でどれが主辞なのかがはっきりしないものが存在する．このような名称に対しては関係`flat`を用いてタグ付けする (サブタイプ`flat:name`は任意である).

~~~ sdparse
Hilary Rodham Clinton
flat(Hilary, Rodham)
flat(Hilary, Clinton)
~~~

~~~ sdparse
Carl XVI Gustaf
flat(Carl-1, Gustaf-3)
flat(Carl-1, XVI-2)
~~~

~~~ sdparse
New York
flat(New, York)
~~~

肩書き/敬称も関係`flat`から分析される．ただし，肩書きによっては固有の内部構造をもつものもあるので，そのような構造は`flat`に埋め込んだ形で表示する:

~~~ sdparse
Mr. Smith
flat(Mr., Smith)
~~~

~~~ sdparse
President Obama
flat(President, Obama)
~~~

~~~ sdparse
French actor Gaspard Ulliel
amod(actor-2, French-1)
flat(actor-2, Gaspard-3)
flat(actor-2, Ulliel-4)
~~~

~~~ sdparse
Milliardär Ross Perot \n billionaire Ross Perot
flat(Milliardär-1, Ross-2)
flat(Milliardär-1, Perot-3)
~~~

しかし，肩書きや名称が2つの分離した名詞句から成るように思われる場合，`flat`による分析は適切でなく，[u-dep/appos]()による分析のほうがふさわしい．このような事例には，カンマといった記号から名詞句が区切られる場合もあれば，インフォーマルなテキストでカンマが生起しない場合もある．このとき，2要素が逆転可能かどうかを尋ねるテストを行うと良い; 逆転可能なら，`appos`で分析した方がよいだろう; 以下がその例である．

上記のものとは対照的に，名称には_The Lord of the Rings_や_Captured By
Aliens_のように通常の統語関係によってタグ付けすべき事例もある．

~~~ sdparse
The Lord of the Rings
det(Lord, The)
nmod(Lord, Rings)
case(Rings, of)
det(Rings, the)
~~~

~~~ sdparse
The king of Sweden
det(king-2, The-1)
nmod(king-2, Sweden-4)
case(Sweden-4, of-3)
~~~

修飾構造が明瞭である組織名については，次の例のように依存関係が標準の統語関係から修飾構造を示せると良い:

~~~ sdparse
Natural Resources Conservation Service
amod(Resources-2, Natural-1)
compound(Conservation-3, Resources-2)
compound(Service-4, Conservation-3)
~~~

<!--加えて，標準的な統語関係は次のようにも用いられる: (i) 修飾する限定詞やその他の機能語に対して (ii) 埋め込み構造を形成する前置詞句や文が名称に関与し，各要素が結合される場合. (i) は，そのような関係が確認された言語に対して適用される (i.e. (i) の分析はフランス語・ドイツ語・スペイン語には適用されるが，英語には適用されない)．そして，(ii) は
In addition, regular syntactic relations are used: (i) for a modifying determiner or similar function word and (ii) to connect 
together the words of a description or name which involve embedded prepositional phrases, sentences, etc.,
when these relations are (i) recognized in the language being annotated (i.e., the analyses below are for
French, German, and Spanish, not English) and (ii) deemed not to be grammaticalized to the extent that the original role
of the function words has been lost.-->

~~~ sdparse
Le Japon
det(Japon-2, Le-1)
~~~

~~~ sdparse
Ludwig van Beethoven
case(Beethoven, van)
nmod(Ludwig, Beethoven)
~~~

~~~ sdparse
Miguel de Cervantes y Saavedra
conj(Cervantes, Saavedra)
cc(Saavedra, y)
case(Cervantes, de)
nmod(Miguel, Cervantes)
~~~

~~~ sdparse
Río de la Plata
case(Plata-4, de-2)
det(Plata-4, la-3)
nmod(Río-1, Plata-4)
~~~

上記の_Ludwig van Beethoven_ と _Miguel de Cervantes y Saavedra_では，_van_や_de_が前置詞だと仮定した上で分析を行なっている．この分析は名称元の言語内では正しいだろうが，外国のテキストで用いられた場合や文法化が十分に進んだとみなされる場合には異なる分析を受けるだろう．例えば，上のような名称を英語でタグ付けするならば`flat`として分析するほうが適切である:

~~~ sdparse
Ludwig van Beethoven was a famous German composer .
flat(Ludwig, van)
flat(Ludwig, Beethoven)
det(composer, a)
amod(composer, famous)
amod(composer, German)
cop(composer, was)
nsubj(composer, Ludwig)
punct(composer, .)
~~~

~~~ sdparse
Río de la Plata
flat(Río-1, de-2)
flat(Río-1, la-3)
flat(Río-1, Plata-4)
~~~

~~~ sdparse
Al Arabiya is a Saudi-owned news organization
flat(Al-1, Arabiya-2)
nsubj(organization-7, Al-1)
~~~

現代ドイツ語もしくはフランス語において，これらの前置詞は姓 (familiy name) の一部として定着しており，名 (given name) を伴わずに生起することがよくある．この場合でも，`flat`による分析は正しいと考えられる:

~~~ sdparse
Von Hohenlohe gewann das Rennen . \n Von Hohenlohe won the race .
flat(Von-1, Hohenlohe-2)
nsubj(gewann-3, Von-1)
~~~

_Leland Stanford Jr. University_といった人名にちなんだ存在物の固有名では，関係`flat`は人名の内部のみに適用される．そして，残りの部分は通常の統語関係を用いて構成的に分析される:

~~~ sdparse
Leland Stanford Jr. University
compound(Leland-1, University-4)
flat(Leland-1, Stanford-2)
flat(Leland-1, Jr.-3)
~~~

### 名称の関係に対する覚書

_このパラグラフでは，名称構造の関係について過去に展開されてきた議論を簡潔にまとめる．その問題とは歴史的に様々な議論が展開されてきたもので，現在でもそれらのいくつかは議論が続いている．_
_French actor Gaspard Ulliell_のような例: いくつかのツリーバンクでは_Mr._や_French actor_のような肩書きや敬称には`nmod`を用いるが，多くの人はこれを不適切だと考えている．なぜなら，`nmod`の依存部は完全な句であって，格言語 (cased language) においては句の格として修飾語の格をとるべきだからである．<!--Most people think this is inappropriate, since an `nmod` dependent should be a full phrase, which will typically take its own case as a modifier in a cased language. -->対照的に，肩書きはそれに後続する名称と同じ句に属するように思われる; 格言語では一致 (agreement concord) をみせる．
文法的な慣習 (ラテン語に由来) では，上のような_French actor_は"固定化した側置詞 (fixed apposition)" と呼ばれ，名称 (Gaspard Ulliell) を主辞にとる．
UDは関係`appos`を次の"appositives" (ラテン語の"緩い (広い) 同格"に対応する) に限定している．関係`appos`は，2つの完全な名詞句が緩やかに結合し，かつカンマといった記号によって分離された場合のみに用いられる．よって，上記の例に`appos`を用いるのは正しくない．また，関係`compound`が使われることもあったが，これも正しくないように思われる．
It implies headedness, and titles do not usually behave like compounds: in German, they are not joined to the following words, as compounds are normally joined in German, and they appear at the beginning of names in both German and Hebrew, even though German compounds are head last and Hebrew compounds are head first. So `compound` does not seem appropriate either. 
これは主辞性 (headedness) を思わせる．そして，肩書きのふるまいは複合とは通常異なる:ドイツ語では前者は後続する語と結合し
UDv1ツリーバンクのいくつかでは`flat`を_Mr._のような敬称に用いたが，これは奇妙に感じられるので，`flat`を複合表現から成る固有名の結合にのみ用いるべきだと考える人もいる．
UDv2では`flat`は削除され，主辞を取らない要素のチャンクという広い概念を許容する`flat`を取り入れた．<!--どっちも`flat`なの？-->UDv2のガイドラインでは肩書きと敬称のどちらの事例であっても`flat`によって名称と結合するように定めている．


## 日付と複雑な数値

日付は言語によって様々な表現がある．_the 4th of July_のように明瞭な統語構造をみせ，通常の依存関係からタグ付けされる言語もあれば，_1 December 2016_のように平板構造をとり，関係`flat`で分析すべき言語もある.

~~~ sdparse
the 4th of July
det(4th, the)
nmod(4th, July)
case(July, of)
~~~

~~~ sdparse
1 December 2016
flat(1, December)
flat(1, 2016)
~~~

関係`flat`は句構造を欠く他の数値や数表現にも用いられる．

~~~ sdparse
four thousand
flat(four, thousand)
~~~

## 外国語のフレーズ

関係`flat` (サブタイプの`flat:foreign`は任意) は，構成的な分析を受けない外国語のフレーズに対しても適用される．
この事例において．かつてv1で用いられた関係`foreign`は`flat`に置き換えられる．

~~~ sdparse
And then she went : gjiko frac zen .
parataxis(went, gjiko)
flat(gjiko, frac)
flat(gjiko, zen)
~~~

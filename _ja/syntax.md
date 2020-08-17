---
layout: base
title:  'Syntax'
udver: '2'
---

# Syntax

Syntactic dependency labels in Japanese are defined in conformity with
the principles of Universal Dependencies as far as possible.  However,
the definition of Japanese syntax under Universal Dependencies
involves several issues to be discussed.  For example, the definition
of "clause" is not clear, while dependency labels rely on the
definition of "clause", such as the distinction between "nsubj" and
"csubj".  These issues are detailed in the section
[Specific Constructions](http://universaldependencies.org/ja/overview/specific-syntax.html),
while we still have unclear cases.

In the following, we give a rough sketch of dependency labels with a
couple of examples.  See the section [Japanese dependency relations](http://universaldependencies.org/ja/dep/index.html)
for the definition of each label.

## Core arguments
| label | description | examples |
|-------|-------------|----------|
| `nsubj`  | Nominal subjects (typically a postpositional phrase with a case marker が / <i>ga</i> or sometimes with は / <i>wa</i>)</td> | 太郎 が / <i>Taro ga</i> "Taro-NOM" &lt;-`nsubj`- 走る / <i>hashiru</i> "run" |
| `obj` | Direct object (typically a postpositional phrase with a case marker を / <i>o</i>) | ご飯 を / <i>gohan o</i> "rice-ACC" &lt;-`obj`- 食べる / <i>taberu</i> "eat" |
| `iobj` | Indirect object (typicall a postpositional phrase with a case marker に / <i>ni</i>) | 花子 に / <i>Hanako ni</i> "Hanako-ACC" &lt;-`iobj`- あげる / <i>ageru</i> "give" |
| `csubj` | Clausal subjects introduced by a nominal marker の / <i>no</i> | 太郎 が 怒ら れる の は / Taro ga okora reru no ha "that-TOPIC Taro is punished" &lt;-`csubj`- いやだ / iyada "dislike" |
| `ccomp` | Complement clause (typically a clause introduced by と / <i>to</i>) | きれい だ と / <i>kirei da to</i> "that (something) is beautiful" &lt;-`ccomp`- 思う / <i>omou</i> "think" |
| `xcomp` | Not used in Japanese | |

## Non-core dependents
| label | description | examples |
|-------|-------------|----------|
| `obl`| ||
| `vocative`| ||
| `expl`| ||
| `dislocated` | a topic phrase (typically a prepositionalphrase with topic marker は / <i>ha</i>) | 象 は / <i>zo wa</i> "elephant-TOPIC" &lt;-`dislocated`- 鼻 が 長い / <i>hana ga nagai</i> "nose is long" |
| `advcl` | Subordinate clause | 食べ た なら / <i>tabe ta nara</i> "if (someone) ate &lt;-`advcl`- 行く / <i>iku</i> "go" |
| `advmod` | Adverbial modifiers | ゆっくり / <i>yukkuri</i> "slowly" &lt;-`advmod`- 走る <i>hashiru</i> "run" |
| `discourse` | discourse elements like interjection and emoticons | あー / <i>a</i> "ah" &lt;-`discourse`- つかれ た <i>tsukare ta</i> "tired" |
| `aux` | auxiliary verbs and particles that attach to verbs | 食べ <i>tabe</i> "eat" -`aux`-&gt; た / <i>ta</i> "PAST", 行き / <i>iki</i> "go" -`aux`-&gt; ます / <i>masu</i> "POLITE" -`aux`-&gt; か / <i>ka</i> "QUESTION" |
| `cop` | copular auxiliary だ / <i>da</i> | 太郎 は / <i>Taro wa</i> "Taro-TOPIC" &lt;-`nsubj`- 学生 / <i>gakusei</i> "student" -`cop`-&gt; だ / <i>da</i> "COPULA" |
| `mark` | subordinating conjunction, conjunctive particle, complementizer (と / <i>to</i>, か / <i>ka</i>) | 東京 へ 行く / <i>Tokyo e iku</i> "go to Tokyo" -`mark`-&gt; と / <i>to</i> "that" 言っ た / <i>it ta</i> "said" |

## Noun dependents
| label | description | examples |
|-------|-------------|----------|
| `nmod` | Prepositional phrases modifying another phrase | リンゴ の / <i>ringo no</i> "of apple" &lt;-`nmod`- ジュース <i>jusu</i> "juice" |
| `appos` | Appositive relations | 形態素 解析 器 / <i>keitaiso kaiseki ki</i> "morphological analyzer" &lt;-`appos`- Mecab / <i>mekabu</i> "mecab" |
| `nummod` | Numeral classifier phrases | 3 冊 の / <i>san satsu no</i> "three books of" &lt;-`nummod`- 本 / <i>hon</i> "books" |
| `acl` | Relative clause, clausal complement of nouns | 太郎 が 食べ た / <i>Taro ga tabe ta "Taro ate" &lt;-`acl`- リンゴ / <i>ringo</i> "apple" <br/> ほめ られた / <i>home rareta</i> "praise-PASSIVE" &lt;-`acl`- こと / <i>koto</i> "fact" |
| `amod` | Adjectival modifiers; adjectives with arguments are tagged as "acl" | きれいな / <i>kireina</i> "beautiful" &lt;-`amod`- リンゴ / <i>ringo</i> "apple" |
| `det` | この / <i>kono</i> "this", こんな / <i>konna</i> "this", あの / <i>ano</i> "that", あんな  / <i>anna</i> "that", その / <i>sono</i> "that", そんな / <i>sonna</i> "that", どの / <i>dono</i> "which", どんな / <i>donna</i> "which" modifying a noun | この / <i>kono</i> "this" &lt;-`det`- 本 / <i>hon</i> "book" |
| `clf`  |           |   |
| `case` | Postpositions and particles attach to a noun phrase | 太郎 / <i>Taro</i> "Taro" -`case`-&gt; が / <i>ga</i> "NOM", 太郎 / <i>Taro</i> "Taro" -`case`-&gt; の / <i>no</i> "of", 東京 / <i>Tokyo</i> "Tokyo" -`case`-&gt; へ / <i>e</i> "to" |
  
## Coordination
| label | description | examples |
|-------|-------------|----------|
| `conj` | coordination | (太郎 / <i>Taro</i> "Taro" -`cc`-&gt; と / <i>to</i> "and") -`conj`-&gt; 次郎 / <i>Jiro</i> "Jiro" |
| `cc` | conjunction, coordinating conjunctive particle (e.g. と / <i>to</i>, や / <i>ya</i>) | See the example above |

## MWE
| label | description | examples |
|-------|-------------|----------|
| `fixed` | Multi-word functional expressions | に / <i>ni</i> -`fixed`-&gt; よって / <i>yotte</i> "by", かも / <i>kamo</i> -`fixed`-&gt; しれ / <i>shire</i> -`fixed`-&gt; ない / <i>nai</i> (maybe) |
| `flat` | Proper noun compounds | 山田 / <i>Yamada</i> "Yamada" -`flat`-&gt; 太郎 / <i>Taro</i> "Taro" |
| `compound` | Noun compounds, verb compounds | 構文 / <i>kobun</i> "syntax" &lt;-`compound`- 解析 / <i>kaiseki</i> "analysis", 泳ぎ / <i>oyogi</i> "swim" &lt;-`compound`- 着く / <i>tsuku</i> "reach" |

## Loose 

| label | description | examples |
|-------|-------------|----------|
| `list` | Listing | 1. 東京 / <i>Tokyo</i> "Tokyo" &lt;-`list`- 2. 大阪 / <i>Osaka</i> "Osaka"</td></tr>
| `parataxis` | Listing of sentences | 「 太郎 は 花子 が 好き 。 / <i>Taro wa Hanako ga suki .</i> "Taro loves Hanako." &lt;-`parataxis`- 次郎 は 梅子 が 好き 。 / <i>Jiro wa Umeko ga suki .</i> "Jiro loves Umeko" 」 と 三郎 が 言っ た / <i>to Saburo ga it ta</i> "Saburo said" |

## Special
| label | description | examples |
|-------|-------------|----------|
| `orphan` | used to annotate head-less coordination (see the definition in Universal Dependencies for details) | |
| `goeswith` | used when a word is somehow split into tokens | |
| `reparandum` | speech repair |  |

## Other
| label | description | examples |
|-------|-------------|----------|
| `root` | head of a sentence | |
| `dep` | undefined | |
| `punct` | punctuations | (太郎 / <i>Taro</i> "Taro" -`punct`-&gt; 、) -`conj`-&gt; 次郎 / <i>Jiro</i> "Jiro" |


---
layout: base
title:  'Universal Dependency Relations'
generated: 'true'
permalink: u/dep/index.html
udver: '2'
---

# Universal Dependency Relations

以下の表は，UD v2. で用いられる37つの普遍的な構文関係 (universal syntactic relations) をリスト化したものであり，これは  [*Universal Stanford Dependencies: A cross-linguistic typology*](http://nlp.stanford.edu/pubs/USD_LREC14_paper_camera_ready.pdf) (de Marneffe *et al.* 2014) の改変版である.

表の上部はUDの分類法における主な構成原則に従うものであり，_rows_ は主辞 (head; core arguments of clausal predicates, non-core dependents of clausal predicates, and dependents of nominals) に対する機能カテゴリ (functional categories) と対応し，_columns_ は依存部 (dependent; nominals, clauses, modifier words, function words) の構造的カテゴリに対応する．表の下部は狭義の依存関係 (dependency relations) にない関係をリスト化したものである． 

<!-- 
* Relations used to analyze coordination
* Relations used to analyze multiword expressions (MWE)
* Loose joining relations
* Special relations for ellipsis, disfluencies, and orthographic errors
* Special relations for clausal heads, punctuation and other relations
-->

{% include u-dep-table.html %}

\* The `advmod` relation is used for modifiers not only of predicates but also of other modifier words.

----------

Alphabetical listing

{% assign sorted = site.u-dep | sort: 'title' %}{% for p in sorted %}
* [{{ p.title }}](): {{ p.shortdef }}{% endfor %}

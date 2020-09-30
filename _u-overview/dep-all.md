---
layout: base
title:  'Universal Dependencies'
generated: 'true'
permalink: u/dep/all.html
udver: '2'
---

# Universal Dependencies

以下の表は，UD v2. で用いられる37つの普遍的な構文関係 (universal syntactic relations) をリスト化したものであり，これは  [*Universal Stanford Dependencies: A cross-linguistic typology*](http://nlp.stanford.edu/pubs/USD_LREC14_paper_camera_ready.pdf) (de Marneffe *et al.* 2014) の改変版である.

表の上部はUDの分類法における主な構成原則に従う:

* 各列は主辞 (head) に対する機能カテゴリ (functional categories) と対応する:
    * 節の述語 (clausal predicates) における必須項 (core argument)
    * 節の述語における依存部 (non-core dependents)
    * 名詞の依存部 (dependents of nominals)
* 各行は依存部の構造的カテゴリ (structural) に対応する:
    * 名詞 (Nominals)
    * 節 (Clauses)
    * 修飾語 (Modifier words)
    * 機能語 (Function words)

表の下部は狭義の依存関係 (dependency relations) にない関係をリスト化したものである:

* 等位関係 (coordination) の分析に用いられる関係
* 複合表現 (multiword expressions; MWE) の分析に用いられる関係
* 緩い結合関係 (Loose joining relations)
* 省略 (ellipsis)，言い淀み (disfluencies)，つづりの間違い (orthographic erros) を表す特別な関係
* 節の主辞，句読点などを表す特別な関係

{% include u-dep-table.html %}

----------

{% assign sorted = site.u-dep | sort: 'title' %}{% for p in sorted %}
<a id="al-u-dep/{{ p.title }}" class="al-dest"/>
<h2><code>{{ p.title }}</code>: {{ p.shortdef }}</h2>
{% if p.content contains "<!--details-->" %}    
{{ p.content | split:"<!--details-->" | first }}
<a href="{{ p.title }}" class="al-doc">See details</a>
{% else %}
{{ p.content }}
{% endif %}
<a href="{{ site.git_edit }}/{% if p.collection %}{{ p.relative_path }}{% else %}{{ p.path }}{% endif %}" target="#">edit {{ p.title }}</a>
{% endfor %}

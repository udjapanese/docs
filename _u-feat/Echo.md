---
layout: feature
title: 'Echo'
shortdef: 'is this an echo word or a reduplicative?'
---

この素性はブール型であり，重複語 (reduplicative word) もしくはエコー (echo word) かどうかを判別するのに用いられる．これらの語はヒンディー語およびインドの他言語に存在する．Hyderabad Dependency Treebankでは固有の品詞タグとしてRDPとECHを備える．しかし，その語がRDPかECH (エコーする語と同一の語) であるかどうかとは独立してPOSタグを付与できるので，UDではこれらを別個の品詞としては扱わない．そして，おそらくこの素性と"hyphは"compound"と呼ぶようなものへ統合されるだろう．

### Rdp: 重複 (reduplicative)

重複語は先行する語のコピーである．ヒンディー語では，重複によって分散 ("one rupee each")，分離 ("sit separately")，多様さ，もしくは単に強調の意味を加えることがある．

例: [hi] "कभी - कभी" = "kabhī - kabhī" = "sometimes", "कभी" =
"kabhī" = "sometimes"; "एक एक" = "eka eka" = "one each", "एक" = "eka"
= "one"

### Ech: エコー (echo)

エコーは先行する語の韻を踏むが，その語とは同一の形式をとらず，エコー自体は意味を成さない．ヒンディー語では，エコーは先行語の意味を一般化し，"or something", "etc." といった意味としても用いられる.

例: [hi] "चाय वाय" = "čāya vāya" = "tea or something" (as in "Have some tea or something.")

さらなる詳細については Rupert Snell and Simon Weightman: Teach Yourself Hindi, Section 16.4 and 16.5, pages 210 – 211. を参照されたい.

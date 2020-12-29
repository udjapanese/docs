---
layout: feature
title: 'NounType'
shortdef: 'noun type'
---

POSタグのレベルで普通名詞 (common noun) と固有名詞 (proper noun) を区別してきたが，他の区別を標示するためのタグセットも存在する．

### Class: 類別詞 (classifier)

中国語の類別詞は基数 (cardinal number) と名詞に区別される．ただし，この区別は`NounType`の値のみに関係する．Intersetでは“com”と“prop”という値をもつが，Universal Treebanksにおいては，これらはすでにPOSタグから区別されたものとして考える．
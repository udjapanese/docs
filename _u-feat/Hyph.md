---
layout: feature
title: 'Hyph'
shortdef: 'hyphenated compound or part of it'
---

この素性はブール型であり，当該表現がハイフン付きの複合語 (hyphenated compound) かどうかを判別する．トークン化 (tokenization) のあり方によって，当該の複合語が単一のトークンである場合と複数のトークンに分離される場合がある; よって，そのようなトークンを識別するタグが必要になる．

### Yes: ハイフン付き複合語の部分である

例: "anglo-" in "anglo-saxon"; [cs] "česko-slovenský"
(Czecho-Slovak; 2番目の要素は通常の形容詞なので形容詞のパラダイムに含まれるが，1番目の要素は特殊である．)
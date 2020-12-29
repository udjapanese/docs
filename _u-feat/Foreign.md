---
layout: feature
title: 'Foreign'
shortdef: 'is this a foreign word?'
udver: '2'
---

<table class="typeindex" border="1">
<tr>
  <td style="background-color:cornflowerblue;color:white"><strong>Values:</strong> </td>
  <td><a href="#Yes">Yes</a></td>
</tr>
</table>

この素性はブール型 (i.e. 2値) であり，当該表現が外国語であるかどうかを判別する．借用語 (loan word) や外国語の名称ではなく，本当の外国語が直接話法 (direct speech) の内部や書籍のタイトルなど，母国語のテキストに現れることがある．この素性は (分析不可能なトークンにおいて) [u-pos/X]()の品詞タグに適用される．もしくは，そのトークンの品詞が判明していて，かつ元々の言語における品詞としてタグ付けしたい場合にも適用される．

注意: この素性はUD v2で新たに設定されたものである．元々は言語固有の素性としていくつかのツリーバンクで用いられていたが，ブール型ではなく3値をとるものも確認された．しかし，他の値が用いられることがめったにないため，UD v2ではこのような定義を採用しない．

### <a name="Yes">`Yes`</a>: it is foreign

Example: [en] _He said I could "<b>dra åt helvete!</b>"_
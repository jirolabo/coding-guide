html5
=

- [タグ](#tag)
* [属性値](#attribute)
* [空要素](#empty)
* [スタイル](#style)

<a id="tag">タグ</a>
---

### タグ名

タグ名は小文字を利用する

OK

     <span></span>

NG

     <SPAN></SPAN>




<a id="attribute">属性値</a>
-----

属性値はダブルクォーテーションで囲む

    <span class="hoge"></span>

属性値の数が多い場合は属性値ごとに改行を入れてもよい

### 属性値の順序
属性値はclass、id、data-*、そのほかの属性の順序で記述する

### Boolean属性は常に省略する
一貫して値を省略することでBoolean属性であることが明確になり、可読性が向上する。



<a id="empty">空要素</a>
---
### 空要素にスラッシュは書かない
HTML5では不要（書いてもＯＫ）、HTML4.01では書いたらエラー。

※[w3c Markup Validation Service](http://validator.w3.org/check)参照


<a id="attribute">属性値</a>
-----

できるだけstyle=''の記述は使わない

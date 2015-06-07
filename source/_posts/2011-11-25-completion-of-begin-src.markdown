---
layout: post
title: "BEGIN\_SRCの補完"
date: 2011-11-25 14:47
comments: true
categories: Emacs Org-mode
---

<div id="outline-container-1" class="outline-2">
<h2 id="sec-1">BEGIN_SRCの補完</h2>
<div class="outline-text-2" id="text-1">

<p>org-modeで文章を書いていて、ソースコードなどを埋め込む場合、#+で始まるブロックで
囲む必要がある。
</p>


<pre class="src src-org"><span style="color: #708183; font-style: italic;">#+BEGIN_HTML</span>
<span style="color: #bd3612;">bra, bra, bra...</span>
<span style="color: #708183; font-style: italic;">#+END_HTML</span>
</pre>


<p>
これをいちいち打つのは面倒なので、何か方法があるはずだと、org-ja<sup><a class="footref" name="fnr.1" href="#fn.1">1</a></sup> を見てみたら、やっぱりあった。
</p>
<p>
15.2章の 'Easy Templates'より。"&lt;"の後にセレクタを入力し、&lt;TAB&gt;で展開できる。
</p><blockquote>

<table border="2" cellspacing="0" cellpadding="6" rules="groups" frame="hsides">
<caption></caption>
<colgroup><col class="left" /><col class="left" /><col class="left" /><col class="left" />
</colgroup>
<tbody>
<tr><td class="left">`s'</td><td class="left">`#+begin_src</td><td class="left">&hellip;</td><td class="left">#+end_src'</td></tr>
<tr><td class="left">`e'</td><td class="left">`#+begin_example</td><td class="left">&hellip;</td><td class="left">#+end_example'</td></tr>
<tr><td class="left">`q'</td><td class="left">`#+begin_quote</td><td class="left">&hellip;</td><td class="left">#+end_quote'</td></tr>
<tr><td class="left">`v'</td><td class="left">`#+begin_verse</td><td class="left">&hellip;</td><td class="left">#+end_verse'</td></tr>
<tr><td class="left">`c'</td><td class="left">`#+begin_center</td><td class="left">&hellip;</td><td class="left">#+end_center'</td></tr>
<tr><td class="left">`l'</td><td class="left">`#+begin_latex</td><td class="left">&hellip;</td><td class="left">#+end_latex'</td></tr>
<tr><td class="left">`L'</td><td class="left">`#+latex:'</td><td class="left"></td><td class="left"></td></tr>
<tr><td class="left">`h'</td><td class="left">`#+begin_html</td><td class="left">&hellip;</td><td class="left">#+end_html'</td></tr>
<tr><td class="left">`H'</td><td class="left">`#+html:'</td><td class="left"></td><td class="left"></td></tr>
<tr><td class="left">`a'</td><td class="left">`#+begin_ascii</td><td class="left">&hellip;</td><td class="left">#+end_ascii'</td></tr>
<tr><td class="left">`A'</td><td class="left">`#+ascii:'</td><td class="left"></td><td class="left"></td></tr>
<tr><td class="left">`i'</td><td class="left">`#+include:'</td><td class="left">line</td><td class="left"></td></tr>
</tbody>
</table>


</blockquote>




<div id="footnotes">
<h2 class="footnotes">Footnotes: </h2>
<div id="text-footnotes">
<p class="footnote"><sup><a class="footnum" name="fn.1" href="#fnr.1">1</a></sup> <a href="https://github.com/org-mode-doc-ja/org-ja">org-mode-doc-ja/org-ja</a>
</p></div>
</div>

</div>
</div>

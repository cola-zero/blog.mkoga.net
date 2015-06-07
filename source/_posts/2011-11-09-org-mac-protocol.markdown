---
layout: post
title: "org-mac-protocol"
date: 2011-11-09 00:28
comments: true
categories: Emacs
---

<div id="outline-container-1" class="outline-2">
<h2 id="sec-1">org-mac-protocolの設定</h2>
<div class="outline-text-2" id="text-1">

<p>org-modeをemacsclientを使って外部の情報を取り込める仕組み。
</p>
<p>
今回は、Webブラウザ(Safari, Chrome)からorg-modeへリンクを取り込めるようにする。
</p>
<p>
これを使うと、blogを書くときに、urlとタイトルを別々にコピーする必要がなくなった。
</p>
</div>

<div id="outline-container-1-1" class="outline-3">
<h3 id="sec-1-1">設定</h3>
<div class="outline-text-3" id="text-1-1">


</div>

<div id="outline-container-1-1-1" class="outline-4">
<h4 id="sec-1-1-1">org-protocol</h4>
<div class="outline-text-4" id="text-1-1-1">

<p>まずはorg-protocol<sup><a class="footref" name="fnr.1" href="#fn.1">1</a></sup>を有効にする。org-protocolはcontribなので、load-pathに
contribのディレクトリを追加する必要がある。
{% codeblock setting-for-org-protocol.el lang:cl %}
(add-to-list 'load-path "/path/to/org-mode/contrib/lisp")
(require 'org-protocol)
{% endcodeblock %}

</p></div>

</div>

<div id="outline-container-1-1-2" class="outline-4">
<h4 id="sec-1-1-2">org-mac-protocol</h4>
<div class="outline-text-4" id="text-1-1-2">

<p>org-mac-protocol<sup><a class="footref" name="fnr.2" href="#fn.2">2</a></sup>は、org-protocolをMacOSX上で使えるようにしたもの。
まずはgit cloneし、必要なファイルを必要な場所へ。
```
$ git clone https://github.com/claviclaws/org-mac-protocol.git
$ cp -r org-mac-protocol/*.scpt org-mac-protocol/orgQSLib ~/Library/Scripts
```
~/Library/Scriptsがない場合は先に作る必要があります。
</p>
<p>
そして以下の設定
{% codeblock setting-for-org-mac-protocol.el lang:cl %}
(add-to-list 'load-path "/path/to/org-mac-protocol")
(require 'org-mac-protocol)
{% endcodeblock %}
</p></div>

</div>

<div id="outline-container-1-1-3" class="outline-4">
<h4 id="sec-1-1-3">QuickSilver</h4>
<div class="outline-text-4" id="text-1-1-3">

<p>環境設定-&gt; Catalog -&gt; Scripts -&gt; Scripts(User)にチェックを入れる。
</p>
</div>
</div>

</div>

<div id="outline-container-1-2" class="outline-3">
<h3 id="sec-1-2">使用方法</h3>
<div class="outline-text-3" id="text-1-2">

<p>Chromeでコピーしたいページを開き、QuickSilverでorg-link.scptを選択。
</p>
<p>
Emacsで
```
M-x org-insert-link
```
したあと、ミニバッファに貼り付け(C-y)すると、リンクとその説明が正しく
貼り付けれれた。
</p>
</div>
</div>

</div>

<div id="outline-container-2" class="outline-2">
<h2 id="sec-2">まとめ</h2>
<div class="outline-text-2" id="text-2">

<p>AppleScriptの魔法を使い、Emacsとほかのアプリケーションの連携がうまく
できるようになった。
</p>

<div id="footnotes">
<h2 class="footnotes">Footnotes: </h2>
<div id="text-footnotes">
<p class="footnote"><sup><a class="footnum" name="fn.1" href="#fnr.1">1</a></sup> <a href="http://orgmode.org/worg/org-contrib/org-protocol.html">org-protocol.el – Intercept calls from emacsclient to trigger custom actions:Google Chrome</a>
</p>


<p class="footnote"><sup><a class="footnum" name="fn.2" href="#fnr.2">2</a></sup> <a href="https://github.com/claviclaws/org-mac-protocol">claviclaws/org-mac-protocol - GitHub:Google Chrome</a>
<a href="#iTunes-8F41FA7653E36F99">Song 6:iTunes</a>
</p></div>
</div>

</div>
</div>

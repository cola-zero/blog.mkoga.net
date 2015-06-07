---
layout: post
title: "Octopressでorg-modeを使う方法"
date: 2011-10-20 14:00
comments: true
categories: octopress
---

<div id="outline-container-1" class="outline-2">
<h2 id="sec-1"></h2>
<div class="outline-text-2" id="text-1">

<p><a href="http://blog.mkoga.net.dev/blog/2011/10/18/new-post/">前回のエントリー</a>
の続き。
{% img right /images/org2octopress.png org2octopress %}

</p>
</div>

<div id="outline-container-1-1" class="outline-3">
<h3 id="sec-1-1">結果</h3>
<div class="outline-text-3" id="text-1-1">

<p>   前回は、org-modeからhtmlを生成するために、<a href="https://github.com/bdewey/org-ruby">org-ruby</a> を使おうとしてたが、
   少しググったところ、OctoressがラップしているJekyllとOrg-modeを組み合わせて使っている人がいた<sup><a class="footref" name="fnr.1" href="#fn.1">1</a></sup>。
   すでにEmacs上にはOrg-modeからhtmlへの変換が実現しているため、こちらを使う方が確実。
   結局Org-modeからhtmlを吐き出し、それをOctopressに食わせるようにした。asdf
</p>
</div>

</div>

<div id="outline-container-1-2" class="outline-3">
<h3 id="sec-1-2">変更点</h3>
<div class="outline-text-3" id="text-1-2">

<p>Org-mode のファイルは、新たにorg/_postsディレクトリを作成し、そこに生成する。
</p>
<p>
この動作を実現するため、Rakefileの一部を以下のように変更した。
{% gist 1300490 %}
先頭のチャンクは、rake new_postで生成するファイルの場所と拡張子を変更している<sup><a class="footref" name="fnr.2" href="#fn.2">2</a></sup>。
後半の２つのチャンクは、new_postとnew_pageで生成するファイルのヘッダをorg-modeにあわせて変更している。
</p>
<p>
さらに、<sup><a class="footref" name="fnr.1.2" href="#fn.1">1</a></sup>よりorg-jekyllをインストールし、以下の設定を自分の.emacsに追加した。
{% gist 1300497 %}

</p></div>

</div>

<div id="outline-container-1-3" class="outline-3">
<h3 id="sec-1-3">投稿手順</h3>
<div class="outline-text-3" id="text-1-3">

<p>あとは、rakeコマンドで生成されたファイルを編集し、
{% codeblock %}
M-x org-publish
{% endcodeblock %}
を実行するとsource/_posts ディレクトリにhtmlが生成される。その後、ターミナル上で
{% codeblock %}
$ rake generate
{% endcodeblock %}
を実行すると、各ポストが生成される。
</p>
</div>

</div>

<div id="outline-container-1-4" class="outline-3">
<h3 id="sec-1-4">まとめ</h3>
<div class="outline-text-3" id="text-1-4">

<p>一応org-modeを使うことができるようになった。。
</p>

<div id="footnotes">
<h2 class="footnotes">Footnotes: </h2>
<div id="text-footnotes">
<p class="footnote"><sup><a class="footnum" name="fn.1" href="#fnr.1">1</a></sup> <a href="http://juanreyero.com/open/org-jekyll/">http://juanreyero.com/open/org-jekyll/</a>
</p>


<p class="footnote"><sup><a class="footnum" name="fn.2" href="#fnr.2">2</a></sup> この変更はstylesheetに関するRakeの動作にも影響があるため、source/stylesheetsからorg/stylesheetsにリンクを作成した。
</p></div>
</div>
</div>

</div>
</div>

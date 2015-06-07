---
layout: post
title: "VMware Fusion 4でGuest OSをguiなしで起動する方法"
date: 2012-02-15 01:39
comments: true
categories:
---

<div id="outline-container-1" class="outline-2">
<h2 id="sec-1"></h2>
<div class="outline-text-2" id="text-1">

<p>ずっと方法がわからなかったが、ついに実現したので、メモ。
</p>
<p>
以下のディレクトリにあるvmrunコマンドを使う。
</p><blockquote>

<p>/Applications/VMware Fusion.app/Contents/Library
</p>
</blockquote>


<p>
マニュアルは<sup><a class="footref" name="fnr.1" href="#fn.1">1</a></sup>にある。
</p>
<p>
上記ディレクトリをPATHに追加したら、以下のコマンドで起動する。
</p><blockquote>

<p>$ vmrun ~/Documents/Virtual\ Machines.localized/VM-Name.vmwarevm/VM-Name.vmx nogui
</p>
</blockquote>


<p>
以上。
</p>

<div id="footnotes">
<h2 class="footnotes">Footnotes: </h2>
<div id="text-footnotes">
<p class="footnote"><sup><a class="footnum" name="fn.1" href="#fnr.1">1</a></sup> <a href="http://www.vmware.com/support/developer/vix-api/vix111_vmrun_command.pdf">http://www.vmware.com/support/developer/vix-api/vix111_vmrun_command.pdf</a>
</p></div>
</div>

</div>
</div>

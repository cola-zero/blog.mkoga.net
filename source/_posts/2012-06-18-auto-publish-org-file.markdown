---
layout: post
title: "Org-modeで保存後自動でpublishする"
date: 2012-06-18 16:07
comments: true
categories:
---
<p>
Emacsのsave-after-hookを変更して、orgファイルを保存したあとに自動でorg-publishを
行うようにした。
</p>


{% codeblock lang:scm %}
(defun auto-export-my-blog ()
  (let* ((project-plist (cdr (assoc "blog" org-publish-project-alist)))
         (project-dir (expand-file-name
                       (plist-get project-plist :base-directory))))
    (save-excursion
      (if (string= project-dir (file-name-directory buffer-file-name))
          (org-publish-current-file)))))

(add-hook 'after-save-hook
          'auto-export-my-blog)
{% endcodeblock %}

<p>
上記の例の場合、`org-publish-project-alis`に"blog"のエントリーがあること。
</p>
<p>
自分の現在の設定は以下の通り。
</p>


{% codeblock lang:scm %}
(setq org-publish-project-alist
   '(("blog" .  (:base-directory "~/work/blog.mkoga.net/source/_org_posts/"
                 :base-extension "org"
                 :publishing-directory "~/work/blog.mkoga.net/source/_posts/"
                 :sub-superscript ""
                 :recursive t
                 :publishing-function org-publish-org-to-html
                 :headline-levels 4
                 :html-extension "markdown"
                 :body-only t))))
{% endcodeblock %}

<p>
この設定にすると、~/work/blog.mkoga.net/source/_org_posts/以下にあるorgファイルを保存した時、
自動的にpublishされる。
</p>
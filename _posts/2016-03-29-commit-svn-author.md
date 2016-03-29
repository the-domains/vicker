---
inFeed: true
hasPage: true
inNav: false
inLanguage: null
starred: false
keywords: []
description: ''
datePublished: '2016-03-29T04:22:58.458Z'
dateModified: '2016-03-29T04:22:57.905Z'
title: 修改已經 commit 的 SVN author
authors: []
publisher:
  name: null
  domain: null
  url: null
  favicon: null
author: []
sourcePath: _posts/2016-03-29-commit-svn-author.md
published: true
url: commit-svn-author/index.html
_type: Article

---
# 修改已經 commit 的 SVN author

近日遇到一個問題就係 JIRA username 同 SVN username 唔同. 結果唔識得自動做 user mapping. 解決方法好明顯就係要改 username. JIRA 要改 username 極煩... Atlassian support 曾經講過因為 username 會 hardcode o係好多個地方... 所以正常黎講無可能改得到. 咁唯有改 SVN 啦. 之前曾經試過要做類似既事... 要將整個 repository dump 出黎, 改完之後再 import 返入去. 呢個方法唔單止慢, 仲好 risky...

Google 左一輪發現原來係可以透過 Subclipse 或者 Turtlesvn 改 commit properties (包括 author 同 description). 不過首先就要o係 repository level 加返一個 pre-revprop-change o既 executable hook 先得.

以 Subversion Edge (Windows) 為例. 其實睇返隻 repository 就會見到 hook 個 folder. 裡面有一堆 tmpl. 如果係 nix 的話其實只要將 tmpl 轉做 executive 就攪掂. Windows 就要自己寫 bat 喇 =.=
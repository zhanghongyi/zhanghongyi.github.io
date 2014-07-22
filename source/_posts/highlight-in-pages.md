layout: photo
title: 在Pages中高亮代码
date: 2014-07-19 17:32:15
tags: tips
discription: highlight code pages
photos:
- /img/2014-7-19.png
---

在用Pages写报告的时候，常常为如何高亮代码而苦恼。我原来的做法是建立一个1×1的表格，再将代码copy进去，但是这样又增加了排版的复杂度，并不够方便。直到我遇见了[Highlight](http://www.andre-simon.de/doku/highlight/en/highlight.php)。

使用Highlight只要两步就可以轻松地将代码copy到剪切板，然后再Ctrl+v到文档中，就搞定了。
<!--more-->

首先，安装Highlight。如果Mac上有安装[Homebrew](http://brew.sh/)，`brew install highlight` 即可。如果没有Homebrew, 嗯...我觉得还是装一个先好了。Homebrew是Mac上一个很好用的包管理工具。

最后，没错就是最后了，使用Highlight来高亮代码。在terminal中执行 `highlight filename -O rtf | pbcopy`，高亮好的代码就已经在你的剪切板里啦。你可以粘贴到你想要的文档里去，包括但不限于Pages，Keynote。

#### Tips:

1. 如何指定高亮的语言？

	Highlight几乎支持你能想到的所有语言，完整地list可以查看[官方说明](http://www.andre-simon.de/doku/highlight/en/langs.php)，使用 ` — syntax python` 或者 `—syntax py`，可以指定语言为python，其他同理。

2. Highlight甚至提供了不同的主题供选择

	`highlight -w` 可以查询所有的主题，使用`—style themename`可以指定想要的主题。

3. `-O rtf` 是什么意思？

	使用`-O`可以指定输出的格式，rtf只是其中的一种，还可以输出为html, latex, SVG.

4. 生成文件

	使用小写的`-o`可以指定输出为文件，例如`highlight -o hello.html hello.py` 就可以生成一个坐拥高亮代码的html啦。

5. 显示行号
	
	`—line-number`

6.  使用echo

	如果只有一小行代码的话，不妨使用echo吧。`echo “print(‘Hello, World.’)” | highlight -O rtf —syntax py | pbcopy`

7. 更多

	我用到的就是这么多啦，如果有更多的需求，可以`highlight -h` 或者到官方wiki了解更多惊喜。

以上。

	
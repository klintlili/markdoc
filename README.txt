一个在线 Markdown 编辑器 - Markdoc

这个markdown工具本身就是一个github仓库地址https://github.com/weareoutman/markdoc

它里面还依赖另外一个子github仓库地址（.gitmodules文件只有设置） https://github.com/marijnh/CodeMirror.git

这个CodeMirror项目现在更新了很多，但是Markdoc工具却只是使用CodeMirror项目的版本是f4ae5b42c929edc78c2df0888ae1b0179098652a，对应这个地址https://github.com/marijnh/CodeMirror/tree/f4ae5b42c929edc78c2df0888ae1b0179098652a

这个就行，我之前下载了最新的版本，我就发现以前使用CodeMirror，要引入CodeMirror目录lib下codemirror.js

新版本CodeMirror已经在lib文件夹下没有了codemirror.js这个文件，新版本是在src目录下但是codemirror.js的内容变小了

我们最后还是使用老版本的CodeMirror吧，使用的是4.3.1版本，这个版本至少CodeMirror项目文件夹下lib下有codemirror.js文件

我们使用Markdoc项目就不会报错在不到这个codemirror.js文件了

额外提一下：
我们下载下来或者clone Markdoc项目之后，里面的CodeMirror文件夹下的内容是空的，也就说Markdoc项目依赖的CodeMirror项目就存放在CodeMirror文件夹下，现在我们下载下来
CodeMirror就存在在CodeMirror文件夹下即可。
我们更新子git窗口内容是可以使用命令
第一次拉取：
git submodule sync --recursive
git submodule update --init --recursive
更新：
git pull --recurse-submodules

Git 同步
将本项目代码同步到目标项目。
git submodule update --init --recursive --remote


但是我发现下载CodeMirror项目太慢了，并且不知道下载好了之后会不会是下载了CodeMirror的最新版本
最后我们下载了指定版本的zip包，没有使用git来clone


还有额外小知识就是
$(function() {……});这行写js代码，是function()匿名函数页面加载后里面执行的意思。

Markdoc项目会记住上一次用户写在页面上markdown内容，我们下次进来或者刷新页面还是在的，那是因为使用了js浏览器的本地缓存功能
https://www.runoob.com/jsref/prop-win-localstorage.html
在Markdoc项目js文件夹下的editor.js文件中有使用 localStorage.getItem(storageKey) 和 localStorage.setItem(storageKey, value);

最后说说codemirror的作用是什么
在线代码编辑器 CodeMirror
https://www.oschina.net/p/codemirror?hmsr=aladdin1e1
CodeMirror是一款"Online Source Editor"，基于Javascript，短小精悍，实时在线代码高亮显示，他不是某个富文本编辑器的附属产品，他是许多大名鼎鼎的在线代码编辑器的基础库。
oschina站的在线LESS编译器和Markdown编辑器就是采用这个组件开发。
比如这个 https://tool.oschina.net/less   https://tool.oschina.net/markdown
可以用来编辑html，js，php，css，markdown等等语言
具体可以看看我的文章"codemirror在线代码编辑器"。
。
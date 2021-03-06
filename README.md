支持将 markdown 格式一键复制到微信公众号文章编辑中，保留 markdown 排版样式，并对 markdown 默认样式进行了美化。在线地址：
[http://zhouzhili.github.io/wechatformat/index.html](http://zhouzhili.github.io/wechatformat/index.html#/)

### 特性

- [x]  样式自定义

- [x]  代码高亮

- [x] 文章链接转为文末引用

- [x] 一键复制文章

- [x] 模拟手机预览

### 处理过程

- 解析 markdown，我使用[marked](https://github.com/markedjs/marked)进行解析，marked 会将 markdown 解析为 HTML 元素，并且在期 render 中可以对各个元素进行处理，比如应用自己设定的样式之类，十分方便。

- 代码高亮，作为程序员，代码高亮是必不可少的。我使用[highlight.js](https://highlightjs.org/)处理 marked 解析之后的 code 标签进行代码高亮，highlight 有上百种代码样式，但是并不是所有的都很美观，因此我删除了其中的一些样式。在切换高亮风格的时候只需要切换 css 文件即可。我们只需要在初始化的时候创建一个 link 标签，在切换样式的时候动态修改 link 标签的 href 属性就可以了。

- 样式自定义。自定义样式只需要在默认的样式文件上修改保存即可。本来自定义样式以 css 文件方式存储最为简单，但是在修改 css 的时候获取此刻编辑的标签十分困难，不够直观。因此，我选择以 JSON 存储样式，使用[jsoneditor](https://github.com/josdejong/jsoneditor)作为样式编辑器，我们就可以在编辑某个样式的时候高亮当前编辑的元素，使得编辑更加直观。

### 参考

1. Lyric 的[wechat-format](https://labs.lyric.im/wxformat/)
2. 胡子哥的[WxMarkdown](http://md.barretlee.com/)

### 不足

由于没有后台支撑，自定义样式目前只支持创建一个(太懒，不想写了),而且保存在浏览器的 localStorage,因此在您清除浏览器缓存之后可能会消失，建议先保存到本地以防不测。

这是一款浏览器插件  
目的是为了让浏览器的翻译内容更加美观

一开始想直接让翻译内容下方出现下划线  
后面一直没能实现，就改成简单效果，将内容颜色改为红色
一通乱搞，阴差阳错之下，在豆包浏览器成功了，但在谷歌浏览器失败了  
这也让我思考重要的一点，我应该先去搞懂，浏览器是如何翻译内容的，搞懂内在逻辑  
豆包浏览器的翻译逻辑好像比较统一，都是会在这个节点：
  document.querySelectorAll('[data-doubao-translate-traverse-mark]  

## CSS Questions
**Describe what a "reset" CSS file does and how it's useful**  
Reset CSS的目标是通过修正浏览器的某些__默认样式__，让你的代码在不同浏览器上的表现更加一致。比如在一个浏览器下的默认段落行高（`line-height`）和另外一个浏览器的默认段落行高会有不一致，而通过Reset CSS可以将他们归为一致。又比如，有些浏览器里面用`left-margin`来设置`ol`元素的默认的左边距（这里就是左外边距），有些浏览器却是用`left-padding`来设置的（这里就是左内边距），Reset CSS同样可以让他们更一致，比如让它们统一使用左外边距。你可以在[这篇文章](http://meyerweb.com/eric/thoughts/2007/04/18/reset-reasoning/)里面了解更多。

## JS Questions
**Explain event delegation**  
事件委托是一种页面js程序的设计方法，用于将子节点事件委托予父节点处理。假设有一个父节点`ul`，它拥有多个子节点`li`。假设我们的需求是在`li`元素被点击的时候做出一些处理程序，那么就需要往每个`li`节点添加eventListener。麻烦的事情是，如果这些li节点被频繁插入、删除并且数量很大时，页面的整体性能会被严重降低。事件委托设计方法通过在父节点`ul`上监听一个类型相同的事件`e`，这个事件对象在DOM树上会有propagate以及bubbling两个阶段，我们可以在这两个阶段中拦截这个事件，并通过`e.target`获取真正需要处理的DOM节点对象，并进行相应处理。更多介绍可以查看[这篇文章](http://davidwalsh.name/event-delegate)。  
**Explain how `this` works in JavaScript**
`this`即当前运行代码的上下文对象。简单地说，谁调用的函数，`this`就是谁。但是这个调用方并不总是你能直接看到的，比如调用`Object.prototype.bind`的时候，调用方就由虚拟机在内部制定。具体地说，可以查看[这篇文章](http://howtonode.org/what-is-this)。  
**AMD vs. CommonJS?**  
CommonJS是模块化JS的规范，AMD是其拓展。  
**What's a hashtable?**  
即Key-Value对，一个Key对应一个Value。JS中一般将对象当做hashtable使用，因为他们同样是KV结构。但是JS中的对象只支持字符串和数字为Key。  
**What's the difference between a variable that is: `null`, `undefined` or `undeclared`?**
`undeclared`是未声明（这东西不常用），`undefined`是未赋值的，`null`是已经赋值的空对象。  
**Difference between document load event and document ready event**  
document.ready是在所有html和DOM加载完毕的时候触发的，不包括图像等外部资源的加载。而window.onload则是在所有外部资源也加载完毕的时候出发的。所以顺序是`document.ready -> window.onload`。

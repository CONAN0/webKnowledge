### 背景图片引入路径在html中的书写注意事项
* 1、backgroundImage后面的URL括号里面有 **“”** 引号
	> 错误  `.png(:style='{"backgroundImage":"url("+ defaultAvatar +")"}')`
	> 正确  `.png(:style='{"backgroundImage": \`url("${defaultAvatar}")\` }')`（es6转义失败）
	
* 2、webpack 打包html中引入的图片路径（本地路径，远程路径不受影响），在开发中的坑是在dev环境下打包正常，在build环境下就不正常了，因为html中的css被提取到vender.css之后相对路径被改变了
	> 解决方法 `import defaultAvatar from './assets/avatar.png';`,在html里面引入变量（vue框架）

* 3、一个元素定位为fixed，用backgroundImage引入图片，浮在页面上，如果该元素下层有可点击的元素（比如：radio），会发生点击穿透bug，此元素不触发事件（即使已经绑定点击事件），此元素下面的radio元素会触发radio绑定的事件，
	> 解决方法 backgroundImage引入图片方式改成img:src的方式引入即可，不会发生点击穿透事件
* 4、fixed元素（主要是蒙层），在移动端上下滑动时会发生穿透，导致蒙层下面的页面也会跟着滑动

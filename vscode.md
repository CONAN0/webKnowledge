### 当vscode打开一个文件，覆盖另外一个文件的时候。分两点考虑：
* 把tab浏览模式打开
	> workbench.editor.showTabs 设为true，
* 把预览模式关闭
	> workbench.editor.enablePreview 设为false，

---------
#####具体步骤
* mac中shift+command+p --> 输入settings --> 找到settings.json文件 --> 修改对应代码
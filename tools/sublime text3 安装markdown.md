### sublime text3 安装markdown
#### 安装package control
参考[安装Package Control](https://blog.csdn.net/zknxx/article/details/52685094)

主要是如果安装完成后报```There are no packages available for installation```的错误，需要在```Preference->Package Setting->Package Control->Settings User```中写如下内容：
```
"channels":
	[
		"C:\\sublime\\channel_v3.json" // 本地路径
	]
```
channel_v3.json从官网上下载的文件，见[channel_v3.json](Blogs/attachments/files/sublime/channel_v3.json)

#### 安装插件
1. 使用```Ctrl + Shift + p```调出命令模式，输入```Package Control: install ```，回车进入后，依次安装：```MarkdownEditing```，```MarkdownPreview```, ```LiveReload```。

2. 安装完成后，配置```MarkdownPreview```（该插件用于在浏览器中打开markdown的实时效果）的快捷键(打开快捷键设置的方法：先调出命令模式，输入```key binding```即可)，如下：
```
{ "keys": ["alt+m"], "command": "markdown_preview", "args": {"target": "browser", "parser":"markdown"}  }
```
其中```parser```可以为```github```，那将调用github的api解析markdown文件

3. 打开```Preferences -> Package Settings -> Markdown Preview -> Settings User``` 配置如下：
```
{
    "enable_autoreload": true
}
```

4. 调出命令模式，输入```LiveReload: Enable/disable plug-ins```， 回车后选择```Simple Reload with delay (400ms)```或者```Simple Reload```，表示是否延时加载。

5. 重启sublime后，新建markdown文件，保存，按上述设置的快捷键调出浏览器即可查看markdown的显示效果了（每次需保存才会触发刷新）。

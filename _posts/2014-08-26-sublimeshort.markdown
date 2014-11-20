---
layout: post
title:  "sublime txt 快捷键&简单教程 "
date:   2014-08-26 09:28:51
categories: wiki 
---
## 快捷键
1. Ctrl+D 选词 （反复按快捷键，即可继续向下同时选中下一个相同的文本进行同时编辑）
1. Ctrl+G 跳转到相应的行
1. Ctrl+J 合并行（已选择需要合并的多行时）
1. Ctrl+L 选择整行（按住-继续选择下行）
1. Ctrl+M 光标移动至括号内开始或结束的位置
1. Ctrl+T 词互换
1. Ctrl+U 软撤销
1. Ctrl+P 查找当前项目中的文件和快速搜索；输入 @ 查找文件主标题/函数；或者输入 : 跳转到文件某行；
1. Ctrl+R 快速列出/跳转到某个函数
1. Ctrl+K Backspace 从光标处删除至行首
1. Ctrl+KB 开启/关闭侧边栏
1. Ctrl+KK 从光标处删除至行尾
1. Ctrl+KT 折叠属性
1. Ctrl+KU 改为大写
1. Ctrl+KL 改为小写
1. Ctrl+K0 展开所有
1. Ctrl+Enter 插入行后（快速换行）
1. Ctrl+Tab 当前窗口中的标签页切换
1. Ctrl+Shift+A 选择光标位置父标签对儿
1. Ctrl+Shift+D 复制光标所在整行，插入在该行之前
1. ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找
1. Ctrl+Shift+K 删除整行
1. Ctrl+Shift+L 鼠标选中多行（按下快捷键），即可同时编辑这些行
1. Ctrl+Shift+M 选择括号内的内容（按住-继续选择父括号）
1. Ctrl+Shift+P 打开命令面板
1. Ctrl+Shift+/ 注释已选择内容
1. Ctrl+Shift+↑可以移动此行代码，与上行互换
1. Ctrl+Shift+↓可以移动此行代码，与下行互换
1. Ctrl+Shift+[ 折叠代码
1. Ctrl+Shift+] 展开代码
1. Ctrl+Shift+Enter 光标前插入行
1. Ctrl+PageDown 、Ctrl+PageUp 文件按开启的前后顺序切换
1. Ctrl+Z 撤销
1. Ctrl+Y 恢复撤销
1. Ctrl+F2 设置书签
1. Ctrl+/ 注释整行（如已选择内容，同“Ctrl+Shift+/”效果）
1. Ctrl+鼠标左键 可以同时选择要编辑的多处文本
1. Shift+鼠标右键（或使用鼠标中键）可以用鼠标进行竖向多行选择
1. Shift+F2 上一个书签
1. Shift+Tab 去除缩进
1. Alt+Shift+1~9（非小键盘）屏幕显示相等数字的小窗口
1. Alt+. 闭合当前标签
1. Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑
1. Tab 缩进 自动完成
1. F2 下一个书签
1. F6 检测语法错误
1. F9 行排序(按a-z)
1. F11 全屏模式

## 安装包控制（Package Control）
- 打开Sublime Text 2，按快捷键 ctrl+` 或者点击 Tools → Command Palette 调出控制台Console；
- 将以下代码复制粘贴进命令行后回车：
{% highlight ruby %}

import urllib2,os;pf='Package Control.sublime-package';
ipp=sublime.installed_packages_path();
os.makedirs(ipp) if not os.path.exists(ipp)elseNone;open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read())

{% endhighlight %}
- 重新启动Sublime Text 2，如果在Preferences → Package Settings 中看到 Package Control 这一项，就说明安装成功了。

## 安装Alignment插件
* 对于喜欢整齐的玛民来说，这不失为一个省事的插件。该插件可以通过上面安装好的 Package Control 来安装：
* 按ctrl + shift + P调出命令面板；
* 输入 install 调出 Package Control：Install Package 选项，并回车；
* 输入Alignment，选中并按回车安装；
* 重启Sublime Text 2，选中文本并按ctrl + alt + a 就可以进行对齐操作了。

## 安装 Soda 主题
* 这里的主题不同于针对代码的 color scheme，而是针对Sublime Text 2该软件本身的主题，该主题也可以通过万能的 Package Control 来安装。
* 按ctrl + shift + P调出命令面板；
* 输入 install 调出 Package Control：Install Package 选项，并回车；
* 输入 theme soda 选中后回车即可安装；
* 安装完之后要激活主题，打开 Preferences → Global Settings – User，加上以下代码保存即可生效：
"theme": "Soda Light.sublime-theme" 或者 "theme" : "Soda Dark.sublime-theme"

## 安装cTags插件
* 首先，从Ctags官网下载压缩包下来，解压到电脑的某个地方，比如“C:\Program Files\ctags”，然后把cTags添加到系统变量里去：
* 在“我的电脑”右键属性 → 高级 → 环境变量 → 在“系统变量”里找到“Path”，点击“编辑” → 把“;C:\Program Files\ctags”（不包括双引号）复制到最后 → 最后一路“确定”保存。
* 然后通过 Package Control 来安装 cTags 插件：
按ctrl + shift + P调出命令面板；
* 输入 install 调出 Package Control：Install Package 选项，并回车；
* 输入 ctags 选中后回车即可安装。
* 安装完之后，在项目的当前目录下按ctrl + t, ctrl + r，会生成.tags的文件。当光标停留在某个函数上时，按快捷键 ctrl+t, ctrl+t就可以打开函数所在的文件，并跳转到相应的位置了。
* PS： 安装这个插件折腾了我蛮久，主要是不知道还要从ctags官网下载压缩包，以及修改系统的变量，后来还是一博友给我发的国外的参考资料才知道要这样配置 的。刚开始知道这软件之所以没用是因为没有像eclipse可以追踪函数的功能，后来才知道可以通过安装cTags插件来实现。装上此功能后，就更喜欢用 Sublime Text 2了。

## jsFormat插件
* 格式化js：选中一段文本，control+alt+f。

## DocBlockr
* 在JS函数上方输入/**，然后回车，doc就生成好了非常好用。

## sublime-jslint
* 打 开一个js文件，control+j，即可输出jsLint检查的结果。
* 打开Packages目录，找到插件目录sublime-jslint，打开 sublime-jslint.sublime-settings文件，可以修改jsLint配置，还可以配置文件保存时自动检查等
* 如：
`{ // Path to the jslint jar. // Leave blank to use bundled jar. "jslint_jar": "",   // Options pass to jslint. // Jerry Qu注：全部可用配置参考这里，https://github.com/fbzhong/sublime-jslint/wiki/Available-jslint4java-options "jslint_options": "--encoding utf-8 --bitwise --browser --cap --css --devel --debug --evil --forin --fragment --on --sub --white --windows --sloppy",   // Ignore errors, regex. "ignore_errors": [ // "Expected an identifier and instead saw 'undefined' \(a reserved word\)" ],   // run jslint on save. "run_on_save": false,   // debug flag. "debug":false }`

## SideBarEnhancements
* 推荐通过 Package Control 安装 SideBarEnhancements 这个插件，可以大大加强在侧栏目录树中右键的选项

## Zen Coding

## jQuery Package for sublime Text

## Clipboard History

## Bracket Highlighter

## GBK to UTF8

## Git


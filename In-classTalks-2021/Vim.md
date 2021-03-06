# Vim入门小教程：

## vim概述：

* Vim的来源：Vi Imitation -> Vi Improved
* 终端文本编辑器：不必打开新窗口，直接在终端操作。远程连接……
* 不用鼠标：追求极致的速度&代价是需要熟记命令
* 功能齐全：代码补全&外观配色&资源管理……
* **四种模式**：
  * 命令模式（Command mode）
  * 底线命令模式（Last line mode）
  * 输入模式（Insert mode）
  * 可视模式（Visual mode）

#### 安装和基本使用：

只需要执行下面的语句即可安装：

```
sudo apt install vim
```

**打开文件**：`vim a.cpp`

## 命令模式：

一开始进入的界面就是命令模式：在这个模式下，你输入的字符不是对文本的修改，而是针对vim编辑器的一个命令

**基础命令**：

`h`：向左移动
`j`： 向下移动
`k`：向上移动
`l`： 向右移动
`^`：移动到行首
`$`：移动到行尾
`gg`：移动到文件开头
`G`： 移动到文件末尾
`nG`：移动到第几行，其中n是一个数字
`H`：将光标移动到屏幕顶行
`L`： 将光标移动到屏幕底行
`z`： 将当前行置为屏幕顶端/中间/底端
	`z.`：中间
	`z+`：顶端
	`z-`：底端

**撤销**：`u`
**重做**：`<C-r>`
**删除**：Vim的删除都会将其放入剪切板中
	`x`：删除选中内容或当前字符（不要使用Backspace/Delete，只在插入模式中有用）
	`d`：更复杂的删除命令，一般只需要用dd删除整行

**复制黏贴**：
`p`：在光标后黏贴
`P`：在光标前黏贴
`y`：复制选中内容

**缩进**：
`>>`：表示将当前行（或选中内容）缩进
`<<`：表示将当前行（或选中内容）反向缩进

## 底线命令模式：
**如何进入**：

1. `:`    输入指令
2. `:!`    输入命令行命令
3. `:!!`    执行上一条命令
4. `/`    进行查找

**基本操作**：
   `:w`写入，加文件名表示另存为
   `:q`退出
   `:e`重新载入
   `:o`打开文件
   `:q!`强制退出，加上!表示强制（在文件未保存时编辑器会发出警告）类似的有`:e!`, `:o!`
   `:wq`保存并退出。

**查找和替换**：
	`/string`：表示查找string。按下n会移动到下一个，按下N移动到上一个。
	`:%s/aaa/bbb/gc`：表示将aaa替换为bbb。后面gc意思是替换并确认。
	**注意**：上述aaa和bbb默认使用正则表达式！这样替换非常方便

**命令行相关**：
	`:!`后加命令，直接执行
	`:sh`启动一个子shell

**分屏**：
	`:vs`打开新文件并放在当前窗口左边
	`:sv`打开新文件并放在当前窗口上面

## 插入模式：

**如何进入插入模式：**
   `a`：在当前光标的右边添加文本
   `i`： 在当前光标的左边添加文本
   `A`：在当前行的末尾添加文本
   `I`： 在当前行的开始添加文本
   `o`：在当前行的下方新创建一行，添加文本
   `O`：在当前行的上方新创建一行，添加文本

## 可视模式：

这是一种文本选择模式（当然也可以用鼠标选择，这里提供的是快捷键进行选择的方法）

**按下`v`进入**：此时光标的位置就是你选择的一个端点，然后通过其他快捷键移动光标到另一个端点，期间文字都被选择。

## 配置文件：
**示范配置文件位置**：`/usr/share/vim/vim80/vimrc_example.vim`
将将这个文件复制到用户目录下，重命名为`.vimrc`，之后编辑`.vimrc`即可：

```
mv /usr/share/vim/vim80/vimrc_example.vim ~/.vimrc
```


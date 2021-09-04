
# PanGu.vim

修改版盘古插件用于自动格式化中文文章排版, 更符合自己的习惯.

## 功能

* 去除句末多余空格
* 给非符号句末添加句号
* 替换多个重复句号或逗号为省略号
* 替换句号、逗号、冒号、分号、感叹号、问号、小括号、单引号、双引号为半角
* 引号间加空格
* 支持删除/添加句首缩进
* 中英文字符间增加一个半角空白
* 全角英文、数字转成半角字符
* 感叹号、问号最多允许连续重复 3 次
* 其他标点符号不允许重复出现

## 支持的文件格式

推荐在以下文件格式中使用:

* Markdown (*.md, *.markdown)
* Text (*.text, *.txt)
* Wiki (*.wiki)
* Vim 中文文档 (*.cnx)

如果想在其他格式的文件中使用这个功能, 可以执行 `:Pangu` 命令.

同时可以在 vimrc 中开启自动规范化功能. 开启方式:

```viml
autocmd BufWritePre *.markdown,*.md,*.text,*.txt,*.wiki,*.cnx call PanGuSpacing()
```

> **注意: 目前只对纯文本格式的文件支持较好, 其他如 html 等, 请谨慎开启. **
>
> 如果有合适的文件格式推荐, 请提交 [Issue](https://github.com/hotoo/pangu.vim/issues)

## 安装

via vim-plug:

```
Plug 'asiocity/pangu.vim'
```

## 用法

### `:Pangu` 命令

手动执行该命令, 将当前文件进行规范化.

### `:PanguAddSpaceAtStart` 命令

手动执行该命令, 对当前文件所有行首进行缩进处理.

### `:PanguDelSpaceAtStart` 命令

手动执行该命令, 删除当前文件所有行首进行缩进.

### `:PanguB2G` 命令

手动执行该命令, 对当前文件进行繁简转换.

### `:PanguG2B` 命令

手动执行该命令, 对当前文件进行简繁转换.

## 技巧

批量规范化多个文档.

```
$ vim a.md b.md c.md

:argdo Pangu | update
:wq
```

### 持久化禁用

在编辑的文档中任何位置注明 `PANGU_DISABLE`, 则整个文档不自动规范化.

## 参考

* [中文文案排版指北](https://github.com/sparanoid/chinese-copywriting-guidelines)


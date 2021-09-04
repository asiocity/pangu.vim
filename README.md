
# PanGu.vim

修改版盘古插件用于自动格式化、标准化中文排版.

它会可以进行自动格式化、标准化, 更符合自己的习惯.

## 功能

* 替换逗号句号为半角
* 替换多个重复句号和逗号为三个句号做省略号
* 去除句末多余空格
* 支持给句末自动添加句号

## 原功能

* 中英文字符间增加一个半角空白
* 中文前后的半角标点转成全角标点
* 全角英文、数字转成半角字符
* 连续的句号自动转省略号
* 感叹号、问号最多允许连续重复 3 次
* 其他中文标点符号不允许重复出现

## 支持的文件格式

推荐在以下文件格式中使用：

* Markdown (*.md, *.markdown)
* Text (*.text, *.txt)
* Wiki (*.wiki)
* Vim 中文文档 (*.cnx)

如果想在其他格式的文件中使用这个功能，可以执行 `:Pangu` 命令。

同时可以在 vimrc 中开启自动规范化功能。开启方式：

```viml
autocmd BufWritePre *.markdown,*.md,*.text,*.txt,*.wiki,*.cnx call PanGuSpacing()
```

> **注意：目前只对纯文本格式的文件支持较好，其他如 html 等，请谨慎开启。**
>
> 如果有合适的文件格式推荐，请提交 [Issue](https://github.com/hotoo/pangu.vim/issues)

## 安装

via vim-plug:

```
Plug 'asocity/pangu.vim'
```

## 用法

### `:Pangu` 命令

手动执行该命令，将当前文件进行规范化。

### `:PanguDisable` 命令

禁止自动规范化。

### `:PanguEnable` 命令

启用自动规范化。

## 技巧

批量规范化多个文档。

```
$ vim a.md b.md c.md

:argdo Pangu | update
:wq
```

### 持久化禁用

在编辑的文档中任何位置注明 `PANGU_DISABLE`，则整个文档不自动规范化。

## 参考

* [中文文案排版指北](https://github.com/sparanoid/chinese-copywriting-guidelines)


# markdown语法介绍和typora编辑器的安装使用

[TOC]

## typora

实时预览：一般 Markdown 编辑器界面都是两个窗口，左边是 Markdown 源码，右边是效果预览。有时一边写源码，一边看效果，确实有点不便。但是使用 Typora 可以实时的看到渲染效果，而且是在同一个界面，所见即所得；

扩展语法：Typora 使用的是 GitHub 风格的 Markdown 语法，扩展了任务列表、表格、表情符号、数学公式、代码高亮等常用功能；

快捷操作：Typora 对几乎所有 Markdown 语法都提供了快捷操作，通过菜单栏的 段落  和 格式 中的功能可以快速设置标记语法，一些常用的操作都有快捷键，用起来非常高效；

简单漂亮：Typora 不光界面简单，操作也不复杂，上手非常容易。默认支持 6 种主题，可随意切换，好看而且好用；

跨平台：Typora 支持 macOS、Windows 和linux系统；

免费：目前的版本是 Version 0.9.9.9.9.2，还处于 beta 阶段，依然免费；

### ubuntu（16.04）安装typora

- `sudo apt-key adv --keyserver keyserver.ubuntu.com --recv-keys BA300B7755AFCFAE`这是一个可选的操作，但是建议还是添加上这一步。
- `sudo add-apt-repository 'deb http://typora.io linux/'`添加`typora`的远程仓库
- 如果提示`sudo: add-apt-repository: command not found` 那`sudo apt-get install python-software-properties`和`sudo apt-get install software-properties-common`
- `sudo apt-get update`更新
- `sudo apt-get install typora` 安装
- 如果出现`typora`无法打开的情况，执行 `sudo apt install gconf2`

## Typora For Markdown语法

### 标题

使用#表示一级标题，##表示二级标题，以此类推，有6个标题。 

### 列表

输入+, -, *,创建无序的列表，使用任意数字开头，创建有序列表

### 块引用

使用>来插入块引用。例如：

```
>这是一个块引用！
```

将产生：

> 这是一个块引用！
>
> > 这是一个二级引用

### 代码

- 使用`包裹的内容将会以代码样式显示，例如

```
使用`printf()`
```

则会产生`printf()`样式。

- 输入```然后回车，可以输入代码块，并且可以选择代码的语言。例如：

  将会产生

  ```java
  public Class HelloWorld{
    System.out.println("Hello World!");
  }
  ```

### 强调

使用两个*号或者两个_包裹的内容将会被强调。例如

```
**使用两个*号强调内容**
__使用两个下划线强调内容__
```

将会输出

**使用两个\*号强调内容** **使用两个下划线强调内容** Typroa 推荐使用两个*号。

### 斜体

在标准的Markdown语法中，*和_包裹的内容会是斜体显示，但是GFM下划线一般用来分隔人名和代码变量名，因此我们推荐是用星号来包裹斜体内容。如果要显示星号，则使用转义：

```
\*
```

### 下划线

用HTML的语法`<u>Underline</u>`将产生下划线<u>Underline</u>.

<u>dhidhisdhod</u>

### 删除线

GFM添加了删除文本的语法，这是标准的Markdown语法木有的。使用`~~`包裹的文本将会具有删除的样式，例如`~~删除文本~~`将产生删除文本的样式。

~~删除文本~~

### 高亮

`使用==文本==来高亮需要显示的文本`

==高亮文本==

`使用 $文本 $来高亮显示`

$高亮文本​$

### 插入图片

利用https://sm.ms/ 工具生成一个可以在任何位置访问的图片的地址,将地址粘贴到这就好了。

![597b013ed5469.jpg](https://i.loli.net/2018/07/15/5b4a21a8cbb9b.jpg)

### 插入URL连接

使用尖括号包裹的url将产生一个连接，例如：`<www.baidu.com>`将产生连接:<www.baidu.com>.

如果是标准的url，则会自动产生连接，例如:www.google.com

### 目录列表

输入[toc]然后回车，将会产生一个目录，这个目录抽取了文章的所有标题，自动更新内容。

### 水平分割线

使用`***`或者`---`，然后回车，来产生水平分割线。

------

### 表格

```
|姓名|性别|毕业学校|工资|
|:---|:---:|:---:|---:|
|杨洋|男|重庆交通大学|3200|
|峰哥|男|贵州大学|5000|
|坑货|女|北京大学|2000|
```

将产生:

| 姓名 | 性别 | 毕业学校     | 工资 |
| ---- | ---- | ------------ | ---- |
| 杨洋 | 男   | 重庆交通大学 | 3200 |
| 峰哥 | 男   | 贵州大学     | 5000 |
| 坑货 | 女   | 北京大学     | 2000 |

其中代码的第二行指定对齐的方式，第一个是左对齐，第二个和第三个是居中，最后一个是右对齐。

但是表格我建议还是用typora的快捷方式吧。在**菜单栏**里**段落**中插入**表格** 更快。

### 任务列表

还没怎么用过，我建议这种不怎么能用的上的，不要记，等到用的时候还是直接用typora中的快捷键吧，在菜单栏的段落里面。语法是`- [ ] 完成`，记得要三个部分要有空格。

- [x] 完成
- [ ] 没完成

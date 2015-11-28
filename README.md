# Vno, just another ghost theme

(中文在后)

## Overview

`Vno` is a ghost theme derivated from [Dale Anthony's Uno](https://github.com/daleanthony/uno). The theme features a minimal, responsive design with a cover page, disqus comment integration, font icons and various color options.

I fixed some unexpected behaviors and changed some style and detail, making it more suitable for Chinese (or Japanese and Korea) language content. Please find a live demo of the theme running as my personal blog, [OneV's Den](http://onevcat.com).

## Features

### Cover page

There is a beautiful full screen landing page for you to display a cover image with blur effect. I suppied several color for you to choose for the cover, while of course you can add your own. You can also place your avatar, blog title, your bio and some social button here.

### Responsive and Animation

Vno is following the responsive design and works well in mobile devices. You may find some events is driven by great animation, thanks to the [Animate.css](http://daneden.github.io/animate.css/), which makes all these possible.

### Disqus comments and Font Awesome

Integrate comment system with a simple user name input with [Disqus](https://disqus.com). Use [Font Awesome](http://fontawesome.io) icon to express yourself better. They are perfect for a personal site (such as blog), as well as some commercial CMS.

### SASS and No-JS fallback

Vno is built on SASS, but it is not a must flow. If you know HTML and CSS, making modifications to the theme should be super simple.

While JS is widely used, there are always strange systems and browsers not supporting JS. Don't worry, there is fallback if there is no JS. So you can just see a proper layout even if the JS does not work.

### Code highlight

[highlight.js](http://highlightjs.org) is used as the code highlight engine of this theme. You can get a clean and good-look code block in your tech blog.

## Usage

### Install

You should already set up a [ghost blog](https://ghost.org). If you are not prepared yet, please refer to the official [installation page](http://docs.ghost.org/installation/).

When you get ready, just clone the repo to a folder under your blog's theme folder: `content/themes/`. Restart ghost and you can find the `Vno` in the blog setting panle.

### Cover

#### Image and Color

Place your cover image under `assets/images/` folder and replace the default image file `background-cover.jpg`(You can also change it in your blog setting). You can change the cover overlap color as well. Change the `cover-orange` in the line of `<div class="panel-cover--overlay cover-blue"></div>` in `partials/side-panel.hbs` to the color you like. There are 7 options by default: 

* `cover-blue` - #2568A3
* `cover-green` - #156F78
* `cover-purple` - #493252
* `cover-red` - #E25440
* `cover-orange` - #FB9C50
* `cover-slate` - #3D4260
* `cover-disabled` - Transparent

#### Avatar and Bio

The avatar will be the logo of your blog. Change it in your blog setting.

You can write a short bio on the landing page. See `partials/side-panel.hbs` file and you will find how to deal with that. :)

#### Navigation Buttons

Also in the `partials/side-panel.hbs` file. Don't forget to change it to your own links. You may not change the `/#blog` link, which will trigger an animation to your blog main page.

#### Social Buttons

You should update the links and icons in `partials/social.hbs`. The icons comes from Font Awesome, see [here](http://fontawesome.io/icons/) for all icons you can use.

### Disqus

You need to know your `short name` of Disqus. Add it to `disqus_shortname` in `comments.hbs` and then replace the `{{!-- {{> comments}} --}}` with `{{> comments}}` in `post.hbs` to enable Disqus for your blog.

### Code highlight theme

Vno is using the classic [tomorrow](http://jmblog.github.io/color-themes-for-highlightjs/tomorrow/) theme as a default. You can select your favourite color scheme and put it under `assets/css` folder directly. Then change the `css/tomorrow.css` in `default.hbs` to make it live. For more color schemes, see [this site](http://jmblog.github.com/color-themes-for-highlightjs/).

## Development

In order to develop or make changes to the theme you will need to have the sass compiler and bourbon both installed.  If you are running a Ghost environment locally then you should already have these installed as those are required to run Ghost.

To check installation run the following commands from a terminal and you should see the `> cli output` but your version numbers may vary.

### SASS

```bash
sass -v
> Sass 3.3.6 (Maptastic Maple)
```

If for some reason SASS isn't installed follow the instructions from the [Sass install page](http://sass-lang.com/install)

### Bourbon
```bash
bourbon version
> Bourbon 4.0.1
```

If Bourbon isn't installed follow the installation instructions on the [Bourbon website](http://bourbon.io)

### Go go dev

Once installation is verified we will need to go mount the bourbon mixins into the `scss` folder.

From the project root run `bourbon install` with the correct path

```bash
bourbon install --path assets/scss
> bourbon files installed to assets/scss/bourbon/
//Or "Bourbon files already installed, doing nothing." if you already installed it.
```

Now that we have the bourbon mixins inside of the `scss` src folder. We can now use the sass cli command to watch the scss files for changes and recompile them.

```bash
pwd
> In the vno theme root folder: {blog_path}/content/themes/vno
sass --watch assets/scss/vno.scss:assets/css/vno.css
>>>> Sass is watching for changes. Press Ctrl-C to stop.
```

Now, you can change the scss files and all change will be complied to the final `/css/vno.css` automatically.

### OSX Maverick

Some people may receive this error when trying to run the `sass --watch` command

```bash
> LoadError: cannot load such file -- rb-fsevent
  Use --trace for backtrace.
```

This is a known issue with the [Sass on OSX Maverick](http://stackoverflow.com/questions/22413834/getting-error-when-using-command-line-for-sass-to-watch-files) as indicated install the `rb-fsevent` gem.

```bash
gem install rb-fsevent
```

### Good luck

Enjoy it and give me feedback. If you find any bugs (in fact I am new to web dev), do not hesitate to point them out, and a pull request would be appreciated!

## Licence

Great thanks to [Dale Anthony](https://github.com/daleanthony) and his [Uno](https://github.com/daleanthony/uno). Vno is based on Uno, and contains a lot of modification on page layout, animation, font and some more things I can not remember.

Vno is followed with Uno and be licensed as [Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/). See the link for more information.

---

## 总览

`Vno` 是一个从 [Dale Anthony 的 Uno](https://github.com/daleanthony/uno) 派生出的 Ghost 主题。它遵从简洁和响应式的设计风格，拥有一个独立的封面，易于集成的 Disqus 评论系统，字体图标以及多种颜色。

我在原来的基础上对一些预料外的行为进行了修正，并且改变了一些样式和细节，这样主题在中文 (以及日文和韩文) 上表现得更好。我的个人博客 [OneV's Den](http://onevcat.com) 正在使用这个主题，您可以看看实际的效果。

## 特性

### 封面

主题有一个全屏的带有模糊（和半透明）效果的封面页，您可以选择喜欢的颜色，当然也可以添加您自己喜欢的颜色。您可以在封面页上放置头像，博客名字，简介以及社交网络导航等等。

### 响应式设计和动画

Vno 遵循响应式设计，所以应该能在各种设备上都表现良好。很多事件是由动画驱动的，这要感谢 [Animate.css](http://daneden.github.io/animate.css/) 的帮助。

### Disqus 评论系统和 Font Awesome 字体

如果您打算使用 [Disqus](https://disqus.com) 的话，集成评论系统就只是填一个用户名那么简单。您也可以使用 [Font Awesome](http://fontawesome.io) 的图标字体来获得更好的表现。这些不仅对于个人站点 (比如博客) 来说是很好的选择，对于一些商用的 CMS (内容管理系统) 来说也是不错的解决方案。

### SASS 和 No-JS 回滚

Vno 是基于 SASS 创建的，但是如果您不再希望继续维护可扩展性，您也可以忽略这个再开发的流程。不过如果您懂一些 HTML 和 CSS 的话，对现有主题做出修改是轻而易举的。

虽然 JS 已经被广泛使用了，但是还是总会有一些奇怪的系统或是浏览器不支持 JS。得益于 Vno 对于没有 JS 时进行了回滚处理，所以您也不必担心。

### 代码高亮

使用了 [highlight.js](http://highlightjs.org) 作为主题的代码高亮引擎。您可以在您的技术博客上以简洁优美的形式呈现您的代码。

## 使用

### 安装

您应该已经建立了一个可用的 [ghost 博客](https://ghost.org)。如果您还没有准备好，请参考[官方的安装页面](http://docs.ghost.org/installation/)来配置一个属于您自己的 ghost 博客。

一旦您准备就绪，只需要将这个 repo clone 到您博客的主题文件夹下：`content/themes/`，然后重启 ghost，您应该就能在博客的设定面板中看到 `Vno` 了。

### 封面

#### 图片和颜色

将您的封面图片放到主题的 `assets/images/` 下，替换掉原来的 `background-cover.jpg` 文件即可（您也可以在博客的设定页面中进行更改）。您也可以改变封面的颜色。找到 `partials/side-panel.hbs` 文件，将 `<div class="panel-cover--overlay cover-blue"></div>` 中的 `cover-orange` 替换成您需要的颜色即可。默认为您提供了七种选择：

* `cover-blue` - #2568A3
* `cover-green` - #156F78
* `cover-purple` - #493252
* `cover-red` - #E25440
* `cover-orange` - #FB9C50
* `cover-slate` - #3D4260
* `cover-disabled` - 透明

#### 头像和简介

头像直接使用了您的博客的 logo。在博客的设定页面中可以进行更改。

您还可以在封面页上写一个简短的介绍。只要您瞄一眼 `partials/side-panel.hbs` 应该就知道怎么做了 :)

#### 导航按钮

也在 `partials/side-panel.hbs` 文件中定义。不要忘了把它们换成您自己的链接。您不应该更改或者至少保留 `/#blog` 链接，因为这个链接将触发一个转场到您的博客主页面的动画。

#### 社交按钮

可以在 `partials/social.hbs` 中按照例子将社交网络的按钮替换成您需要的链接和图标。图标都来自 Font Awesome，您可以访问它们的[网站](http://fontawesome.io/icons/)来查看您能使用的所有图标。

### Disqus

为了使用 Disqus 的评论系统，您需要从 Disqus 获取您自己的 `short name`。将其添加到 `comments.hbs` 的 `disqus_shortname` 中就可以了。然后您还需要将 `post.hbs` 中的 `{{!-- {{> comments}} --}}` 替换为 `{{> comments}}` 来使 Disqus 生效。


### 代码高亮主题

Vno 使用经典的 [tomorrow](http://jmblog.github.io/color-themes-for-highlightjs/tomorrow/) 主题作为默认的代码高亮配色。您也可以选择和使用您最喜欢的配色，将配色文件直接放到 `assets/css` 文件夹下， 然后将 `default.hbs` 中的 `css/tomorrow.css` 改为您的文件来使配置生效。想要更多的配色方案的话，可以看看这个[站点](http://jmblog.github.com/color-themes-for-highlightjs/)。

## 开发

为了简单地对主题进行修改和开发，您需要安装 sass 编译器以及 bourbon。如果您在本地有 ghost 环境的话，这些应该已经安装好了，因为 ghost 运行是需要这些部件的。

您可以在终端中进行一些检查，来看看是否已经安装完成。如果没有问题的话，您应该可以在命令行后看到对应的工具的版本号。

### SASS

```bash
sass -v
> Sass 3.3.6 (Maptastic Maple)
```

如果 SASS 没有能正确安装的话，请参见 [Sass 安装页面](http://sass-lang.com/install)进行安装。

### Bourbon

```bash
bourbon version
> Bourbon 4.0.1
```

如果 Bourbon 没有能正确安装的话，请参见 [Bourbon 的网站](http://bourbon.io)进行安装。

### 开始开发

验证安装后就可以开始开发了。首先我们要将 bourbon 加载到 `scss` 文件夹里。

在主题文件夹下执行 `bourbon install` 来加载 bourbon：

```bash
bourbon install --path assets/scss
> bourbon files installed to assets/scss/bourbon/
//Or "Bourbon files already installed, doing nothing." if you already installed it.
```

然后就可以使用 sass 的命令行工具来监视文件夹中的 scss 文件的改动，并自动重新编译了。

```bash
pwd
> In the vno theme root folder: {blog_path}/content/themes/vno

sass --watch assets/scss/vno.scss:assets/css/vno.css
>>>> Sass is watching for changes. Press Ctrl-C to stop.
```

现在，任何对于 scss 文件的改动都将自动反映到最终的 `/css/vno.css` 文件中了。

### OSX Maverick

有些人在运行 `sass --watch` 时可能会遇到如下错误：

```bash
> LoadError: cannot load such file -- rb-fsevent
  Use --trace for backtrace.
```

这是一个 Sass 在 OSX Maverick 下的[已知问题](http://stackoverflow.com/questions/22413834/getting-error-when-using-command-line-for-sass-to-watch-files)，新版本中应该已经修复。请尝试将 Sass 升级到最新版本，或者安装 `rb-fsevent` 这个gem：

```bash
gem install rb-fsevent
```

### 祝你好运

玩得开心，也请记得给我反馈。如果您发现了什么 bug (我刚入门 web 开发，这简直是必然的)，请直接指出，如果还能附带一个 pull request 修正的话，那真的感激万分！

如果您觉得这个主题还不错的话，欢迎加颗星星或者 follow 我一下以示支持，这将对我和我的项目的发展提供不可估量的帮助。再次感谢。

## 许可

非常感谢 [Dale Anthony](https://github.com/daleanthony) 和他的 [Uno](https://github.com/daleanthony/uno)。Vno 是一个基于 Uno 大量工作的主题，我在页面布局，动画，字体以及其他一些我也不记得了的地方做出了不少改动。

Vno 遵循 Uno 的要求按照 [Creative Commons Attribution 4.0 International](http://creativecommons.org/licenses/by/4.0/) 进行授权。点击上面的链接可以了解到更多信息。

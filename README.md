# React 中文文档翻译计划

我们使用 [Jekyll](http://jekyllrb.com/) 静态站点生成器，使用 ([mostly](http://zpao.com/posts/adding-line-highlights-to-markdown-code-fences/)) 处理 Markdown, 文档部署在 [GitHub Pages](http://pages.github.com/).

## 团队协作

### 工具

* [Github](https://github.com)
* [Trello](https://trello.com)
* [Gitlo](http://gitlo.co)

### 加入翻译组

我们使用 Github issue 管理项目进度。翻译组成员无需直接提出issue，注册完成github和trello之后，可以使用第三方工具gitlo进行协作。

点击[邀请链接](http://gitlo.co/invite/github/discountry/discountry/react)加入翻译组，根据提示连接你的github及trello账号。

### 认领翻译

![trello-tasks.png](https://ooo.0o0.ooo/2017/05/10/5911faefad615.png)

新建一个与你github名称同名的列表，并将待翻译列表中的待翻译文档拖拽至你的列表中，视为认领翻译（切勿随意编辑他人创建的列表）。

## 安装

如果你想要参与文档的翻译，首先需要在本地部署文档的jkeyll站点。

### 依赖

在使用jkeyll之前，我们需要先安装好ruby

 - [Ruby](http://www.ruby-lang.org/) (version >= 1.8.7)
 - [RubyGems](http://rubygems.org/) (version >= 1.3.7)
 - [Bundler](http://gembundler.com/) (使用 `gem install bundler`)


```sh
$ cd react/docs
$ bundle install # Might need sudo.
$ npm install
```

如果你收到国内糟糕的网络环境影响，请将ruby源切换至国内镜像[ruby-china](http://gems.ruby-china.org/).

### 构建文档

首先克隆本仓库到你的电脑本地：

```sh
$ git clone https://github.com/discountry/react.git
$ cd react/
```

先跑一下 `grunt` 确保项目依被构建。

使用 Jekyll 在本地运行站点 (默认端口路由为： `http://localhost:4000`):

```sh
$ cd docs/
$ bundle exec rake
$ bundle exec jekyll serve -w
$ open http://localhost:4000/react/index.html
```

### 生成文档

通过如下命令，我们可以和react存放的统一路径下名为 `react-gh-pages` 文件夹中的文档。

```sh
$ bundle exec rake release
```

### 发布文档

切换至本项目的 `gh-pages` 分支下，复制 `react-gh-pages` 文件夹中的所有内容，提交并同步至项目中。

```sh
# 如果是初次在本地创建 gh-pages 分支
$ git checkout --orphan gh-pages
$ git rm --cached -r .
# 复制粘贴 `react-gh-pages` 文件夹中的所有内容
# 切换至文档部署分支
$ git checkout gh-pages
# 复制粘贴 `react-gh-pages` 文件夹中的所有内容
$ git add .
$ git commit -m 'update docs'
$ git push origin gh-pages
```

### 申请合并

完成你所选部分的翻译之后，可以在 [Pull requests](https://github.com/discountry/react/pulls) 页面发起新的 Pull requests 请求合并你的翻译至本仓库中。
# 1 博客迁移
## 1.1 环境配置
- node.js 下载
- git 安装以及 github 密钥配置
## 1.2 新博客搭建
1. 复制原电脑博客的以下目录到新电脑的博客目录下
```
_config.yml
themes
source
scaffolds
package.json
.gitignore
```
2. `npm install -g hexo@4.3.1` 全局安装 hexo 脚手架
3. `npm install` 安装必要模块
4. ``npm install hexo-deployer-git --save`` 安装自动提交的插件

## 1.3 启动博客
- `hexo g` 生成博客
- `hexo d` 提交应用博客

# 2 遇到问题
## 2.1 跳过文件生成
为了达到在 Github 部署页面有一个说明文件的效果，需要在 public 增加一个 README.md 文件，而在使用`hexo -g`生成静态网页时会把该文件删掉，所以要在`source`文件夹下新建文件，并设置根目录下`_config.yml`文件的`skip_render: README.md`参数为需要跳过渲染的文件，否则会将该 README 文件渲染。
## 2.2 正确渲染 latex 公式
原生的 markdown 生成器`hexo-renderer-marked`并不好用。根据[官网介绍](https://theme-next.js.org/docs/third-party-services/math-equations)，将其替换成`hexo-renderer-pandoc`，并设置`mathjax: enable: true`，会出现一些标题无法正确渲染。<br>
正确做法应该时将 markdown 生成器换成`hexo-renderer-markdown-it-plus`，并设置`mathjax: enable: false`和`katex: enable: true`，这时两个 dollar 符的公式仍然无法正确渲染，在文章头部加上`mathjax: true`，完美解决。
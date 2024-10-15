# 博客迁移
## 环境配置
- node.js 下载
- git 安装以及 github 密钥配置
## 新博客搭建
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

## 启动博客
- `hexo g` 生成博客
- `hexo d` 提交应用博客

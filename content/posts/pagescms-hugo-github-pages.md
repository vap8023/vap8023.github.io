---
title: "PagesCMS + Hugo + GitHub Pages：免费可视化后台的博客方案"
date: 2026-09-27
draft: false
description: "用 PagesCMS + Hugo + GitHub Pages 替代 WordPress，零成本搭建带可视化后台的个人博客"
tags: ["Hugo", "PagesCMS", "GitHub Pages", "博客搭建"]
categories: ["建站"]
---

## 背景：为什么不用 WordPress

如何替换 WordPress 这样的动态 CMS 网站？前文提到的 VS Code + Front Matter CMS + Hugo + GitHub 是一个免费方案，但对普通用户来说，使用 VS Code 仍有一定难度，无法像 WordPress 那样全部在网站上操作。

因此，这里介绍一个更简单的方案：**PagesCMS + Hugo + GitHub Pages**。它拥有和 WordPress 一样的可视化后台，可以完美替代传统 WordPress 系统，具备三大特点：

- **高速访问**：静态网站，天然快速
- **全自动部署**：保存即发布，无需手动操作
- **可视化后台发文**：浏览器内完成，不碰命令行

整套方案没有任何费用，个人用户可以长期零成本使用，个人博客、技术随笔、笔记站点完全够用。

## 一、架构原理

这套方案使用免费服务 [PagesCMS](https://pagescms.org)：

1. 技术人员搭建好 Hugo 站点，完成初期配置
2. 之后，**没有任何技术基础的用户**使用 GitHub 账号登录 PagesCMS，通过 CMS 界面发布和管理文章
3. 保存提交后，Markdown 文件自动写入 GitHub 仓库，GitHub Actions 自动编译部署
4. 网站自动更新，全程无需人工干预

## 二、搭建流程

### 1. 创建 GitHub 专属网站仓库

登录 GitHub，新建仓库：

- 仓库名：`你的用户名.github.io`
- 选择 **Public** 公开仓库
- 初始化为空白仓库

### 2. 创建 Hugo 网站

本地克隆仓库，新建并初始化一个 Hugo 站点，同步到该仓库。

### 3. 配置 GitHub Actions

在 GitHub 仓库中：

1. 进入 **Settings → Pages → Deployment source**
2. 选择 **GitHub Actions**
3. 点击"浏览工作流模板"，选用 **Hugo** 模板
4. 点击 Configure，保存文件

工作流配置写入仓库后，自动部署正式生效。

### 4. 配置 PagesCMS 后台

使用 GitHub 登录 PagesCMS 网站，选定目标仓库，新建并修改配置文件。该文件保存在仓库根目录的 `.pages.config.yml`，适配 Hugo 的配置内容如下：

```yaml
media:
  input: "assets/images"
  output: "/images"

content:
  - name: "posts"
    label: "博客文章"
    type: "collection"
    path: "content/posts"
    create: true
    delete: true
    fields:
      - name: title
        label: 文章标题
        type: string
      - name: date
        label: 发布日期
        type: date
      - name: draft
        label: 草稿状态
        type: boolean
      - name: description
        label: 文章摘要
        type: string
      - name: tags
        label: 标签
        type: list
      - name: categories
        label: 分类
        type: list
      - name: body
        label: 正文内容
        type: markdown
```

保存后，所有前期配置就完成了。

## 三、PagesCMS 后台日常发文

### 1. 登录后台

前期配置完成后，后续操作全部在浏览器上进行。打开 PagesCMS 官网：<https://app.pagescms.org>，使用 GitHub 账号授权登录，即可进入后台管理。

### 2. 新建 / 编辑文章

登录后选择对应仓库，进入管理面板，即可管理文章和媒体：

- 点击 **Add an entry** 发布新文章
- 旧文章点击 **Edit** 编辑
- 正文需要自己写 Markdown 语法（非所见即所得），建议先在记事本写好内容，转为 Markdown 后粘贴进去
- 图片直接拖拽上传，自动存入指定目录

### 3. 自动发布更新

点击保存后，PagesCMS 自动提交 Markdown 文件到仓库，触发 GitHub Actions 自动编译部署。等待 1-2 分钟，网站更新完成。

## 结语

PagesCMS + Hugo + GitHub Pages 方案，是目前个人免费博客的最优解之一：

- 解决了传统静态博客"**无后台、难维护**"的痛点
- 规避了 WordPress"**付费、卡顿、不安全**"的缺陷

实现了免费、好看、高速、易用、免维护的博客体验。

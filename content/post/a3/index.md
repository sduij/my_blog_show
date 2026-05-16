---
date : '2026-05-15T10:55:22+08:00'
draft : false
title : 'deekwiki番外--Zread'
categories:
  - 工具
tags:
  - deepwiki
img: ''
---

> 开源项目用网页版https://zread.ai/即可

## 为什么用ZreadCLI

* 要分析的是本地私有项目
* 中文支持好
* 安装很快，无复杂配置

## ZreadCLI是什么

Zread CLI 面向本地代码库场景，帮助开发者在本地目录中直接生成项目文档。

它适合这些需求：

* 快速理解代码结构
* 为项目沉淀基础文档
* 为团队 onboarding 提供阅读入口
* 为 AI 编程工具提供更清晰的上下文

## ZreadCLI怎么用

### 安装

参考官方文档https://zread.ai/cli安装即可

### 配置及使用

进入项目目录，安装完首次输入命令zread会进行配置的引导；
1. 选择中文

2. 选服务商时 虽然自定义，coding plan，智谱登录都行，
    但我推荐选自定义服务，用deepseek（便宜），模型选deepseek-v4-flash就行，智谱太贵了

  ![文档生成](https://raw.githubusercontent.com/sduij/my_blog_img/refs/heads/main/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202026-05-15%20102716.png)

![GLM5.1花费](https://raw.githubusercontent.com/sduij/my_blog_img/refs/heads/main/%E5%B1%8F%E5%B9%95%E6%88%AA%E5%9B%BE%202026-05-15%20102908.png)

光生成项目概述就花了我将近3块

> Tips:  有的中转站虽然比deepseek还便宜，但是可能会遇到{"message":"No tool call found for function cal"}的报错，
> 这是因为zread 在生成 Wiki 时，需要调用大模型的“函数调用（Tool Call/Function Calling）”能力，而中转站可能
> 不支持 zread 所需要的这种复杂函数调用格式，或者它中转的模型（比如旧版本 GPT-3.5）本身就不支持函数调用，导
> 致返回的数据格式不对，zread 解析失败，于是报 400 Bad Request。

3. 配好后即可生成文档，生成完成后，文档会保存在项目目录下的 .zread/ 中：
4. 然后可以用zread browse在浏览器中查看


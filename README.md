codeSnifferGitHooks
===================

目的
---
规范代码格式，提高代码质量

说明 
---
* php 编码规范采用类pear风格，有适度修改。
* js 编码规范采用google风格。
* git 钩子将自动对待commit文件进行校验，校验内容包括：
** php语法错误
** php编码规范
** js编码规范
* 校验不通过将不允许提交代码，不通过时，命令行将会报告本次校验结果，具体到代码行。
* gjslint提供基本的格式修复工具fixjsstyle，使用方法

$ fixjsstyle path/file.js

修复时建议从后往前修复，这样行号不会发生变动，避免找不到错误行。
* php 代码规范示例：[http://redmine.huoyunren.com/documents/54]
* js 代码规范：[http://chajn.org/jsguide/javascriptguide.html]

依赖
---
使用本钩子需要安装 php codeSniffer, gjslint, easy_install开源工具\<br>
*PHP_CodeSniffer
** 在线文档: [http://pear.php.net/package/PHP_CodeSniffer/]
** 安装：使用pear安装，不会的请求助搜索工具
* easy_install
** 安装：[http://peak.telecommunity.com/DevCenter/EasyInstall#installing-easy-install]
* gjslint
** 在线文档: [https://developers.google.com/closure/utilities/docs/linter_howto?hl=zh-CN]
** 安装：需要先安装python，使用easy_install安装

配置
---
Git库检出 CatGitHook 项目。
将Cat 目录复制到：pear/codesniffer目录下，如：
// 请注意大小写
$ cp /projects/CatGitHook/Cat /usr/local/Cellar/php55/5.5.5/lib/php/PHP/CodeSniffer/Standards/Cat
将Hook/pre-commit 和 Hook/config.ini复制到项目.git/hooks/目录下：
$ cp /projects/CatGitHook/Hook/pre-commit /projects/cat/app/cat_ucenter/.git/hooks/
$ cp /projects/CatGitHook/Hook/config.ini /projects/cat/app/cat_ucenter/.git/hooks/
配置config.ini
[global]
; 需要排除的文件, 使用正则
exclude[] = 
; Example :
; exclude[] = /.*?tests\/.*?/
; exclude[] = /.*?xx.php/

[php]
; php 执行文件位置
path = php

[phplint]
; 是否开启php语法校验
enable = 1

[phpcs]
; 是否开启 phpcs 校验
enable = 1
; php codesniffer 执行文件所在路径
path = phpcs
; phpcs 代码规范
standard = Cat

[gjslint]
; 是否开启 gjslint
enable = 1
; gjslint 执行文件所在路径
path = gjslint

---
layout:     post
title:      "How to IDEA"
subtitle:   " \"Intellij IDEA Ultimate使用笔记\""
date:       2019-11-04 12:00:00
author:     "Zhul"
header-img: "img/post-bg-2015.jpg"
tags:
    - IDEA
---


# Intellij IDEA Ultimate使用笔记
## 1. 快捷键设置
* File -> Settings -> Keymap，然后在右侧选择切换为Eclipse的快捷键。
* Editor -> Live Templates  下拉选Enter,可以设置一些关于回车键按照模板自动补全代码的设置。


## 2. 字体设置
* File -> Settings -> Editor -> Font，可以设置字体大小。
* 推荐字体：DejaVu Sans Momo    字号：6    行间距：1.0


## 3. 用户个人配置
* 一般来说,Windows下类似 C:\Users\Administrator\.IntelliJIdea2018.2 这种目录，Linux下类似/home/root/.IntelliJIdea2019.2这种目录，在该目录下右config文件夹，该文件夹下存放用户的配置信息。
* 假如其他电脑安装idea，启动的时候可以选择导入你的这个config
这样省得再重复配置了；
* system目录是一些系统缓存文件，日志文件，临时文件，索引文件，包括本地历史文件等等，假如idea遇到运行奇葩问题，请把system文件删除，大多数情况能解决问题；


## 4. IDEA优化配置
### 4.1 优化启动速度
* Linux环境下修改~/.IntelliJIdea2019.2/config/idea64.vmoptions
* 关键的三个参数,
    * 第一个 -Xms 是最小启动内存参数,
    * 第二个 -Xmx 是最大运行内存参数,
    * 第三个-XX:ReservedCodeCacheSize  保留代码占用的内存容量参数
    * 个人设置：1000M，2000M，500M

### 4.2 优化设置
#### 4.2.1 主题设置
* Appearance&Behavior -> Appearance 
#### 4.2.2 设置鼠标悬浮提示
* 再Eclipse里，我们鼠标移动到一个类上，会提示这个类的文档解释信息；IDEA里默认不会这样，我们需要设置下；
* Editor->General
* other标签:勾选Show quick documentation on mouse move，同时设置延迟时间，半秒即可。
#### 4.2.3 显示方法分隔符
* Editor->General ->Appearance
* 勾选Show method separators
#### 4.2.4 忽略大小写提示
* DEA默认提示是区分大小写的，比如输入string，不会提示String类；
* Editor->General ->Code Completion 
* 取消勾选match case(匹配大小写)
#### 4.2.5 自动导包
* Editor->general->Auto Import
* Java标签，下拉选All 然后下面两个勾选下即可；
* 不仅能自动导包，自己试下会知道，还能自动去包；
#### 4.2.6 设置Tabs单行或多行显示
* Editor->General ->Editor Tabs
* 根据是否勾选show tabs in one row来设置单行或多行显示
#### 4.2.7 配置类文档注释信息模版
* Editor --> File and Code Templates --> Includes --> File Header
```
/**
@author lcode
@create  ${YEAR}-${MONTH}-${DAY} ${TIME}
/
```
#### 4.2.8 设置文件编码
* Editor -> File Encodings
* Global Encoding   __UTF-8__
* Project Encoding  __UTF-8__
#### 4.2.9 设置自动编译
* 在Eclipse里，项目都是自动编译的，IDEA里默认不是；
* Build,Execution,Deployment -> Compiler
* 勾选Build project automatically和Compile independent modules in parallel；
* 设置项目自动编译，包括平行结构的多个模块也自动编译；
#### 4.2.10 水平或者垂直显示代码
* 有时候为了比对或者参数代码，需要让代码水平或者垂直显示，Eclipse里，我们直接拖拽即可；
* IDEA里，我们右键文件Tab，显示如下：
* Split Vertically，Split Horizontally
* 分别是水平分隔，和垂直分隔，等同于Eclipse中的分隔。


## 5. IDEA(eclipse设置)常用快捷键
* ```Alt+Shift+S``` ```Alt+Inster``` 实现自动生成get/set方法以及构造方法
* ```Ctrl+D``` 删除当前行或者选中所有行
* ```Ctrl+Shift+O``` 导入包
* ```Ctrl+Shift+F``` 代码格式化
* ```Ctrl+Shift+Y``` 转换大小写
* ```Ctrl+F```  查找（当前文件）
* ```Ctrl+h``` 全局查找
* ```双击Shift``` 查找文件
* ```tab/shift+tab``` 整体代码**向后/向前**移动
* ```alt+/``` 提示操作
* ```Alt+Shift+R``` 重命名参数和方法
* ```Ctrl+Alt+↓``` 向下复制一行  
* ```Ctrl+/``` 单行注释
* ```Ctrl+Shift+/``` 多行注释
* ```Shift+Enter```  光标定位到新开的下一行行头
* ```Alt+↑``` ```Alt+↓```  选中单行或者多行 向上或者向下移动
* ```Ctrl+T``` ```Ctrl+点击```  点击进入对应方法
* ```Ctrl+Shift+R``` 打开资源（当前工作区中打开的文件，不包括导入的包和类中的文件）
* ```Ctrl+Shift+T``` 打开类型（包括导入的包和类中的文件）
* ```Alt+Enter```  生成返回值/纠错  eclipse是Ctrl+1
* ```Alt+←``` ```Alt+→``` 跳转上一个/下一个编辑页面
* ```Ctrl+-``` ```ctrl+=``` 收缩或者展开单个方法
* ```Ctrl+Shift+-``` ```Ctrl+shift+=``` 收缩全部或者展开全部方法  自定义配置
* ```Ctrl+Shift+H``` 查看方法重写结构
* ```Ctrl+Alt+H``` 查看方法调用者
* ```F4选中类``` 查看类继承关系
* ```Ctrl+O``` 查看类结构
* ```Ctrl+Alt+Shift+U``` 查看类结构关系图
* ```todo```  插入TODO标签，下面TODO页可以查询相关的TODO备注


## 6. IDEA Proect/Module
| Eclipse | IDEA |
| :---: | :---: |
| Workspace | Project |
| Project | Module |
| Project-specific JRE | Module JDK|
| User library | Global library |
| Classpath variable | Path variable |
| Project dependency | Module dependency |
| Library | Module library |

* Intellij系中的 Project  相当于Eclipse系中的 Workspace ；
* Intellij系中的 Module  相当于Eclipse系中的 Project ；
* Intellij中一个 Project  可以包括多个 Module ；
* Eclipse中一个 Workspace  可以包括多个 Project；


## 7. IDEA DEBUG
常用操作:
  * F5 进入方法
  * F6 单步执行
  * F8 执行到下一个断点，没有下一个断点则执行结束
  * Shift+F8 调出方法，跳到调用方发处
  * Ctrl+U 表达式计算


## 8. IDEA Maven
* Build,Execution,Deployment -> Maven   设置maven仓库
* Build,Execution,Deployment -> Maven -> Importing  
    * Import maven projects automatically   自动导入maven项目
    * Automatically download:Sources Documentation  自动下载源码和文档
* File -> Other Settings -> Settings for New Projects...    修改maven全局配置


## 9. IDEA Jrebel
Lisence Server:（2019.11.02可用）<br>
https://jrebel.hexianwei.com/d6b6698a-a2e6-11e9-a2a3-2a2ae2dbcce4
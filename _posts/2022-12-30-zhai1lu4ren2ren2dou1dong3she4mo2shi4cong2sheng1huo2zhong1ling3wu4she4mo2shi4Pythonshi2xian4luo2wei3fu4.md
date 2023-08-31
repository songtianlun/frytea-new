---
title: "[摘录]《人人都懂设模式：从生活中领悟设模式（Python实现） 》 - 罗伟富"
categories: [ "阅读", "阅读摘录 "]
tags: [  ]
draft: false
slug: "700"
date: "2022-12-30 19:56:59"
---

人人都懂设模式：从生活中领悟设模式（Python实现）
罗伟富
64个笔记


◆ 基础篇

>> 类图用于表示不同的实体（人、事物和数据），以及它们彼此之间的关系。该图描述了系统中对象的类型以及它们之间存在的各种静态关系，是一切面向对象方法的核心建模工具。

>> UML 类图中最常见的几种关系有：泛化（Generalization）、实现（Realization）、组合（Composition）、聚合（Aggregation）、关联（Association）和依赖（Dependency）。这些关系的强弱顺序为：泛化=实现 > 组合 > 聚合 > 关联 > 依赖

>> 泛化（Generalization）是一种继承关系，表示一般与特殊的关系，它指定了子类如何特化父类的所有特征和行为

>> 实现（Realization）是一种类与接口的关系，表示类是接口所有特征和行为的实现。

>> 组合（Composition）也表示整体与部分的关系，但部分离开整体后无法单独存在。因此，组合与聚合相比是一种更强的关系。

>> 聚合（Aggregation）是整体与部分的关系，部分可以离开整体而单独存在。

>> 关联（Association）是一种拥有关系，它使一个类知道另一个类的属性和方法。关联可以是双向的，也可以是单向的。

>> 依赖（Dependency）是一种使用的关系，即一个类的实现需要另一个类的协助，所以尽量不要使用双向的互相依赖。

>> 在对象间定义一种一对多的依赖关系，当这个对象状态发生改变时，所有依赖它的对象都会被通知并自动更新。

>> 监听模式又名观察者模式，顾名思义就是观察与被观察的关系

>> 监听模式的核心思想就是在被观察者与观察者之间建立一种自动触发的关系。

>> 监听模式根据其侧重的功能还可以分为推模型和拉模型

>> 推模型：被观察者对象向观察者推送主题的详细信息，不管观察者是否需要，推送的信息通常是主题对象的全部或部分数据。

>> 拉模型：被观察者在通知观察者的时候，只传递少量信息。

>> SolidState、LiquidState、GaseousState这三个单词中我们会发现都有一个State后缀，于是我们会想它们之间是否有一些共性，能否提取出一个更抽象的类，这个类就是状态类（State）

>> 用一个中介对象来封装一系列的对象交互，中介者使各对象不需要显式地相互引用，从而使其耦合松散，而且可以独立地改变它们之间的交互。

>> 很多系统中，多个类很容易相互耦合，形成网状结构。中介模式的作用就是将这种网状结构（如图3-3所示）分离成星型结构（如图3-4所示）。这样调整之后，使得对象间的结构更加简洁，交互更加顺畅。

>> 工厂模式关注的是整个产品（整体对象）的生成，即成品的生成；而构建模式关注的是产品的创建过程和细节，一步一步地由各个子部件构建为一个成品。

>> 区别：组合模式关注的是对象内部的组成结构，强调的是部分与整体的关系。构建模式关注的是对象的创建过程，即由一个一个的子部件构建一个成品的过程。

>> 适配模式中主要有三个角色，在设适配模式时要找到并区分这些角色。
（1）目标（Target）：即你期望的目标接口，要转换成的接口。
（2）源对象（Adaptee）：即要被转换的角色，要把谁转换成目标角色。
（3）适配器（Adapter）：适配模式的核心角色，负责把源对象转换和包装成目标对象。

>> 策略模式的核心思想是：对法、规则进行封装，使得替换法和新增法更加灵活。

>> 工厂模式三姐妹：简单工厂模式（小妹妹）、工厂方法模式（妹妹）、抽象工厂模式（姐姐）。

>> 这是最简单的一个版本，只有一个工厂类 SimpleFactory，类中有一个静态的创建方法createProduct，该方法根据参数传递过来的类型值（type）或名称（name）来创建具体的产品（子类）对象

>> 不符合“开放封闭”原则，如果要增加或删除一个产品类型，就要修改switch...case...（或if...else...）的判断代码。

>> 定义一个创建对象（实例化对象）的接口，让子类来决定创建哪个类的实例。工厂方法使一个类的实例化延迟到其子类。

>> 盒马鲜生之所以这么火爆，一方面是因为中国从来就不缺像David这样的吃货，另一方面是因为里面的生鲜很新鲜，而且可以自己挑选。

>> 将一个请求封装成一个对象，从而让你使用不同的请求把客户端参数化，对请求排队或者记录请求日志，可以提供命令的撤销和恢复功能。

>> 命令模式是一种高内聚的模式，之所以说是高内聚是因为它把命令封装成对象，并与接收者关联在一起，从而使（命令的）请求者（Invoker）和接收者（Receiver）分离。

>> （1）你希望系统发送一个命令（或信号），任务就能得到处理时。如 GUI 中的各种按钮的点击命令，再如自定义一套消息的响应制。
（2）需要将请求调用者和请求接收者解耦，使得调用者和接收者不直接交互时。
（3）需要将一系列的命令组合成一组操作时，可以使用宏命令的方式。

>> 在不破坏内部结构的前提下捕获一个对象的内部状态，这样便可在以后将该对象恢复到原先保存的状态。

>> 备忘模式的最大功能就是备份，可以保存对象的一个状态作为备份，这样便可让对象在将来的某一时刻恢复到之前保存的状态。

>> 人生没有彩排，但程序却可以让你无数次回放！这便是备忘模式的设思想。

>> 运用共享有效地支持大量细粒度对象的复用。

>> 在故事剧情中，我们通过限定颜料的数量并采用共享的方式来达到节约资源、节约成本的目的，在程序的世界中这种方式叫享元模式（Flyweight Pattern）。

>> 封装一些作用于某种数据结构中各元素的操作，它可以在不改变数据结构的前提下定义作用于这些元素的新的操作。

>> 设模式的开山鼻祖 GoF 的《设模式：可复用面向对象软件的基础》一书中提到了23种设模式，也称为经典设模式。


◆ 进阶篇

>> 过滤器模式就是根据某种规则，从一组对象中，过滤掉一些不符合要求的对象的过程。

>> MVC 将程序的各个模块进行分层，M（Model）负责数据的存储，V（View）负责数据的显示，C（Controller）负责与用户的交互逻辑，也就是业务逻辑。

>> 模型负责数据的持久化（也就是存储）；视图负责数据的输入和显示，直接和用户交互的一层，如大家看到的网站的页面内容、在表单上输入的数据；控制器负责具体的业务逻辑，根据用户的请求内容操作相应的模型和视图。

>> MVP是MVC的一个变种，很多框架都自称遵循MVC模式，但是实际上它们却实现的是MVP模式；在MVP中使用Presenter对视图和模型进行解耦，视图和模型独立发展，互不干扰，沟通都通过Presenter进行。

>> 前端应用MVC模式（前端的Model并不持久化数据，只是缓存数据或临时数据），后端也用 MVC 模式。

>> 整个网站也是一种 MVC 模式，前端相当于View，而后端同时负责Controller和Mode（l 服务器代码相当于Controller，数据库相当于Model）；用户直接与前端进行交互，根本不知道有后端的存在


◆ 经验篇

>> S—单一职责原则，O—开放封闭原则，L—里氏替换原则，I—接口隔离原则，D—依赖倒置原则

>> 开放封闭原则，即Open Close Principle，简称OCP。

>> 接口尽量小，但是要有限度。当发现一个接口过于臃肿时，就要对这个接口进行适当的拆分。但是如果接口过小，则会造成接口数量过多，使设复杂化。所以接口大小一定要适度。

>> 软件的设是一个循序渐进、逐步优化的过程。经过一次次的逻辑分析，一层层的结构调整和优化，最终才能得出一个较为合理的设图

>> 单一职责原则告诉我们实现类要职责单一

>> 里氏替换原则告诉我们不要破坏继承体系

>> 依赖倒置原则告诉我们要面向接口编程

>> 接口隔离原则告诉我们在设接口的时候要精简单一。

>> 开放封闭原则告诉我们要对扩展开放，对修改封闭。开放封闭原则可以说是整个设的最终目标和原则！开放封闭原则是总纲，其他四个原则是对这个原则的具体解释。

>> 在实际的项目开发中，必须要按时按量地完成任务。项目的进度受时间成本、测试资源的影响，而且程序也一定要保证稳定可靠。

>> 面对需求的变更，我们有三种解决方法。方法一，直接改原有的函数（方法），这种方式最快速，但后期维护最困难，而且不便拓展，是一定要杜绝的

>> 方法二，增加一个新方法，不修改原有的方法，这在方法级别上是符合单一职责原则的，但会给上层的调用增加不少麻烦

>> 方法三，增加一个新的类来负责新的职责，两个职责分离，这是符合单一职责原则的

>> 每一个逻辑单元应该对其他逻辑单元有最少的了解：也就是说只亲近当前的对象。只和直接（亲近）的朋友说话，不和陌生人说话。

>> Keep It Simple and Stupid
保持简单和愚蠢。

>> “简单”就是要让你的程序能简单、快速地被实现；“愚蠢”是说你的设要简单到傻瓜都能理解，即简单就是美！

>> Don＇t repeat yourself.
不要重复自己

>> 不要重复你的代码，即多次遇到同样的问题，应该抽象出一个共同的解决方法，不要重复开发同样的功能。也就是要尽可能地提高代码的复用率

>> （1）函数级别的封装：把一些经常使用的、重复出现的功能封装成一个通用的函数。
（2）类级别的抽象：把具有相似功能或行为的类进行抽象，抽象出一个基类，并把这几个类都有的方法提到基类去实现。
（3）泛型设

>> 你没必要那么着急，不要给你的类实现过多的功能，直到你需要它的时候再去实现。

>> Rule of three 称为“三次法则”，指的是当某个功能第三次出现时，再进行抽象化，即事不过三，三则重构。

>> 查询（Query）：当一个方法返回一个值来回应一个问题的时候，它就具有查询的性质；
命令（Command）：当一个方法要改变对象的状态的时候，它就具有命令的性质。

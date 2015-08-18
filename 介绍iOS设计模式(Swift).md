**Update 04/22/2015:** Updated for Xcode 6.3 and Swift 1.2.

**2015/04/22更新：** 最新更新到Xcode6.3和Swfit 1.2。


**Update note:** This tutorial was updated for iOS 8 and Swift by Vincent Ngo. Original post by Tutorial team member Eli Ganem.

**更新日志：** 这个教程由Vicent Ngo最新更新到iOS 8和Swift。原教程由教程组组员Eli Ganem发表。


**iOS Design Patterns** – you’ve probably heard the term, but do you know what it means? While most developers probably agree that design patterns are very important, there aren’t many articles on the subject and we developers sometimes don’t pay too much attention to design patterns while writing code.

**iOS设计模式** － 你很可能听说过这个词，但是你真的知道它什么意思么？虽然大多数开发者都同意设计模式非常重要，但于此同时，并没有很多文章写这个内容，而且我们作为开发者在写代码时也有时不在意设计模式。

Design patterns are reusable solutions to common problems in software design. They’re templates designed to help you write code that’s easy to understand and reuse. They also help you create loosely coupled code so that you can change or replace components in your code without too much of a hassle.

设计模式是在软件设计中常见问题的重复使用的解决方法。它们是可以让你的代码清晰易懂可重复使用度高的模版。它们也可以帮你完成一些松散的代码，你不用很麻烦就可以更改代码或者替换里面的


If you’re new to design patterns, then I have good news for you! First, you’re already using tons of iOS design patterns thanks to the way Cocoa is built and the best practices you’re encouraged to use. Second, this tutorial will bring you up to speed on all the major (and not so major) iOS design patterns that are commonly used in Cocoa.

如果你并不熟悉设计模式，那我有一个好消息给你！首先， 由于Cocoa的建立方式，你现在就可以使用很多iOS的设计模式了！其次，这个教程会让你快速学所有的主流（以及不那么主流）的被广泛应用在Cocoa里的iOS设计模式。

In this two-part tutorial, you will create a Music Library app that will display your albums and their relevant information.

教程分为两部分，你将会做一个音乐库的app，它可以显示你的专辑以及它们相关的信息。

In the process of developing this app, you’ll become acquainted with the most common Cocoa design patterns:

在开发这个app的过程中，你将会了解大部分常见的Cocoa设计模式：

* Creational: Singleton.
* 创建型：单例模式（Singleton）
* Structural: MVC, Decorator, Adapter, Facade.
* 结构型：MVC，修饰模式（Decorator），适配器模式（Adapter），外观模式（Facade）
* Behavioral: Observer, and, Memento
* 行为型：观察者模式（Observer），备忘录模式（Memento）

Don’t be misled into thinking that this is an article about theory; you’ll get to use most of these design patterns in your music app. Your app will look like this by the end of the tutorial:

别以为这篇文章是关于理论的；你将会在你的音乐app中知道怎么运用大多数这些设计模式。在本教程最后你的app最终会是这样：

![swiftDesignPattern1](http://cdn2.raywenderlich.com/wp-content/uploads/2014/11/swiftDesignPattern1-179x320.png)

![swift设计模式1](http://cdn2.raywenderlich.com/wp-content/uploads/2014/11/swiftDesignPattern1-179x320.png)

Let’s get started!

让我们开始吧！

## Getting Started

Download the [starter project](http://cdn1.raywenderlich.com/wp-content/uploads/2014/11/BlueLibrarySwift-Starter.zip), extract the contents of the ZIP file, and open `BlueLibrarySwift.xcodeproj` in Xcode.

There are three things to note in the project:

1. The `ViewController` has two `IBOutlet` connecting the table view and toolbar in storyboard.

2. The storyboard has 3 components which are setup with constraints for your convenience. The top component is where the album covers will be displayed. Below the album covers will be a table view which list information related to an album cover. Lastly the tool bar has two buttons, one to undo an action and another to delete an album that you select. The storyboard is shown below: 
![swiftDesignPatternStoryboard](http://cdn5.raywenderlich.com/wp-content/uploads/2014/11/Screen-Shot-2014-11-11-at-12.20.32-AM-480x228.png)
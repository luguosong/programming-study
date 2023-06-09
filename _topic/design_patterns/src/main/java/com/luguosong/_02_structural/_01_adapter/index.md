---
layout: note
title: 适配器（Adapter）
nav_order: 10
parent: 结构型模式
grand_parent: 设计模式
create_time: 2023/6/6
---

# 意图

使接口不兼容的对象能够相互合作。

将一个类的接口转换成客户希望的另外一个接口。适配器模式使得原本由于接口不兼容而不能一起工作的那些类可以一起工作。

# 结构

![](https://cdn.jsdelivr.net/gh/luguosong/images@master/blog-img/20230606111514.png)

1. `客户端（Client）`是包含当前程序业务逻辑的类。
2. `客户端接口（Client Interface）`描述了其他类与客户端代码合作时必须遵循的协议。
3. `服务（Service）`中有一些功能类（通常来自第三方或遗留系统）。客户端与其接口不兼容，因此无法直接调用其功能。
4. `适配器（Adapter）`是一个可以同时与客户端和服务交互的类：它在实现客户端接口的同时封装了服务对象。适配器接受客户端通过适配器接口发起的调用，并将其转换为适用于被封装服务对象的调用。
5. `客户端`代码只需通过接口与适配器交互即可，无需与具体的适配器类耦合。因此，你可以向程序中添加新类型的适配器而无需修改已有代码。这在服务类的接口被更改或替换时很有用：你无需修改客户端代码就可以创建新的适配器类。

# 示例

{% highlight java %}
{% include_relative AdapterExample.java %}
{% endhighlight %}

# 类适配器

{% highlight java %}
{% include_relative AdapterByClassExample.java %}
{% endhighlight %}

# 使用场景

## sun.nio.cs.StreamDecoder

![](https://cdn.jsdelivr.net/gh/luguosong/images@master/blog-img/20230607102901.png)

---
layout: note
title: 解释器（Interpreter）
nav_order: 30
parent: 行为型模式
grand_parent: 设计模式
create_time: 2023/6/21
---

# 意图

将待解决问题，提取出规则，抽象为一种语言

# 结构

![](https://cdn.jsdelivr.net/gh/luguosong/images@master/blog-img/202306211007197-%E8%A7%A3%E9%87%8A%E5%99%A8%E7%BB%93%E6%9E%84.png)

1. `AbstractExpression（抽象表达式）`：在抽象表达式中声明了抽象的解释操作，它是所有终结符表达式和非终结符表达式的公共父类。
2. `TerminalExpression（终结符表达式）`：是抽象表达式的子类，它实现了与文法中的终结符相关联的解释操作，在句子中的每一个终结符都是该类的一个实例。通常，在一个解释器模式中只有少数几个终结符表达式类，它们的实例可以通过非终结符表达式组成较为复杂的句子。
3. `NonterminalExpression（非终结符表达式）`：也是抽象表达式的子类，它实现了文法中非终结符的解释操作。由于在非终结符表达式中可以包含终结符表达式，也可以继续包含非终结符表达式，因此其解释操作一般通过递归的方式来完成。
4. `Context（环境类）`：环境类又称为上下文类，它用于存储解释器之外的一些全局信息，通常它临时存储了需要解释的语句。


# 外观模式(Facade Pattern)

外观模式(Facade Pattern)为子系统中的一组接口提供一个一致的界面， Facade模式定义了一个高层接口，这个接口使得这一子系统更加容易使用。

外观模式(Facade Pattern)属于结构型模式。结构型模式涉及到如何组合类和对象以获得更大的结构；结构型类模式采用继承机制来组合接口或实现。结构型模式主要包括：Adapter模式、Bridge模式、Composite模式、Decorator模式、Facade模式、Flyweight模式和Proxy模式。结构型类模式在某种程度上具有相关性。

## 模式简介

GOF的《设计模式》指出Facade模式的意图是：  
为子系统中的一组接口提供一个一致的界面， Facade模式定义了一个高层接口，这个接口使得这一子系统更加容易使用。

将一个系统划分成为若干个子系统有利于降低系统的复杂性，设计目标是使子系统间的通信和相互依赖关系达到最小。达到该目标的途径之一是就是引入一个外观(Fecade)对象，它能为子系统提供简单的缺省视图。

Facade模式适用于以下场景：

- 当你要为一个复杂子系统提供一个简单接口时。子系统往往因为不断演化而变得越来越复杂。大多数模式使用时都会产生更多更小的类。这使得子系统更具可重用性，也更容易对子系统进行定制，但这也给那些不需要定制子系统的用户带来一些使用上的困难。
- 客户程序与抽象类的实现部分之间存在着很大的依赖性。引入Fecade将这个子系统与客户以及其他的子系统分离，可以提高子系统的独立性和可移植性。
- 当你需要构建一个层次结构的子系统时，使用Facade模式定义子系统中每层的入口点。如果子系统之间是相互依赖的，你可以让它们仅通过Fecade进行通讯，从而简化了它们之间的依赖关系。

## 模式图解

Facade模式的UML示例如下：

![Facade模式示例](../images/structural_fecade.jpg)

Facade模式的工作过程如下：

- Facade类知道哪些子系统类负责处理请求，将客户的请求代理给适当的子系统对象。
- Subsystem包内的类实现子系统的功能，并负责处理由Facade对象指派的任务，禁止访问Facade类。
- Client通过发送请求给Facade的方式与子系统通讯，Facade将这些消息转发给适当的子系统对象。
- 使用Facade的客户程序不需要直接访问子系统对象。

Facade模式的有益效果如下：

- 它对客户屏蔽子系统组件，因而减少了客户处理的对象的数目并使得子系统使用起来更加方便。
- 它实现了子系统与客户之间的松耦合关系，而子系统内部的功能组件往往是紧耦合的。
- Facade模式有助于建立层次结构系统和建立对象间的分层依赖关系，并消除循环依赖关系。
- 如果应用需要，它并不限制它们使用子系统类，可以在系统易用性和通用性之间灵活选择。

Abstract Factory模式可以与Facade模式一起使用以提供一个接口，这一接口可用来以一种子系统独立的方式创建子系统对象。 Abstract Factory也可以代替Facade模式隐藏那些与平台相关的类。Mediator模式和Facade模式均抽象了一些已有的类的功能。但是Mediator的目的协调若干个同事对象之间的通信，充当中介者和仲裁者的角色。Facade模式仅对子系统对象的接口进行抽象，简化原始子系统的接口的使用，原始子系统是外部系统或难于维护的子系统，不允许对原始子系统做任何修改。

## 模式实例

Android框架中大量使用了Facade模式，诸如：

- ${android_sdk_root/frameworks/opt/net/wifi/service/java/com/android/server/wifi/FrameworkFacade.java

## 系列文章

- [CSDN专栏: 设计模式(UML/23种模式)](https://blog.csdn.net/column/details/27399.html)
- [Github专栏: 设计模式(UML/23种模式)](https://github.com/media-tm/MTDesignPattern)

## 参考文献

- [GOF的设计模式：可复用面向对象软件的基础](http://item.jd.com/10057319.html)
- [设计模式之禅](http://item.jd.com/11414555.html)
- [图说设计模式](https://github.com/me115/design_patterns)
# 单例模式(Singleton Pattern)

> 一起创作,Come on!! [设计模式-Github-Ebook](https://github.com/media-tm/MTDesignPattern)

单例模式(Singleton Pattern)保证一个类仅有一个实例，并提供一个访问它的全局访问点。Singleton模式属于创建型模式，创建型模式包括FactoryMethod模式，AbstractFactory模式，Singleton模式，ProtoType模式和Builder模式。

## 模式简介

单例模式(Singleton Pattern)是最简单的设计模式。Singleton模式的核心结构中只包含一个单例的特殊类。通过单例模式可以保证系统中有仅仅有唯一的示例。

GOF的《设计模式》指出单例模式的意图是：  
保证一个类仅有一个实例，并提供一个访问它的全局访问点。

Singleton模式适用于以下场景：

- 当类只能有一个实例而且客户可以从一个众所周知的访问点访问它时。
- 当这个唯一实例应该是通过子类化可扩展的，并且客户应该无需更改代码就能使用一个扩展的实例时。

## 模式图解

单例模式保证一个类仅有一个实例，并提供一个访问它的全局访问点，是最简单的设计模式。单例模式的UML示例如下：

![单例模式示例](../images/creational_singleton.jpg)

单例模式的工作过程如下：

- Singleton类中定义Instance操作，Instance操作允许客户访问它的唯一实例；
- Instance操作第一次被调用时，创建它自己的唯一实例；
- 客户只能通过Instance操作访问Singleton实例；

单例模式的有益效果如下：

- 对唯一实例的受控访问 因为Singletion类封装它的唯一实例，Singleton限制了类的访问；
- Singletion模式是对全局变量的一种改进；
- 扩展Singletion类的子类相对容易。
- 允许可变数目的实例，实例数量可以控制

## 模式实例

Android的系统服务大量使用了单例模式

``` javascript
libmedia/AudioSystem.cpp:33:// client singleton for AudioFlinger binder interface
libmedia/AudioSystem.cpp:683:// client singleton for AudioPolicyService binder interface
libmedia/IMediaDeathNotifier.cpp:27:// client singleton for binder interface to services
libmedia/mediametadataretriever.cpp:33:// client singleton for binder interface to service
```

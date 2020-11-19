# Design Pattern - Based on the book 《设计模式之禅》

相关课程参考 bilibili [课程网址](https://www.bilibili.com/video/BV1bJ411v7zC?p=6)

## 六大设计原则 (Six major degin principles)


### 1 单一职责原则 (Single Responsibility Principle)

就一个类而言，应该只有一个引起它变化的原因。A class or module should only take one ***responsibility***. There should never be more than one reason for a class to change.

典型违背单一职责原则的场景：在一个方法中写分支判断，分别执行各自的逻辑。
解决方法：使用父类对方法进行抽象
实际经验：如果类型简单，方法少，可以违背单一职责原则；若果类型复杂，方法多，建议遵循单一职责原则。

### 2 里氏替换原则 (Liskov Substitution Principle)

    a. 子类可以实现父类的抽象方法，但不能覆盖父类的非抽象方法，父类有的方法子类必须有！
    b. 子类中可以增加自己特有的方法
    c. 当子类的方法重载父类的方法时，方法的前置条件（即方法的输入参数）要比父类的方法更宽松
    d. 当子类的方法实现父类的方法时（重写/重载或实现抽象方法），方法的后置条件（即方法的的输出/返回值）要比父类的方法更严格或相等

    *第3,4条也可以理解为，父类可以的，子类一定也可以*

### 3 依赖倒置原则（Dependence Inversion Principle) ###

依赖倒置原则的原始定义为：高层模块不应该依赖低层模块，两者都应该依赖其抽象；抽象不应该依赖细节，细节应该依赖抽象（High level modules shouldnot depend upon low level modules.Both should depend upon abstractions.Abstractions should not depend upon details. Details should depend upon abstractions）。其核心思想是：***要面向接口编程，不要面向实现编程。*** 面向抽象的缺点是不能使用子类的个性化行为。

    a. 每个类尽量提供接口或抽象类，或者两者都具备。
    b. 变量的声明类型尽量是接口或者是抽象类。
    c. 任何类都不应该从具体类派生。
    d. 使用继承时尽量遵循里氏替换原则。

***任何父类出现的地方都可以通过子类代替***

### 4 迪米特法则（Law of Demeter) ###

一个对象对其他对象保持最少的依赖，只和最直接的朋友通信。

    a. 从依赖者的角度来说，只依赖应该依赖的对象。
    b. 从被依赖者的角度说，只暴露应该暴露的方法。

### 5. 接口隔离原则（Interface Segregation Principle) ###

客户端***不应该依赖其不需要的接口***，一个类对另一个类的依赖应建立在最小的接口上。

接口隔离原则和单一职责都是为了提高类的内聚性、降低它们之间的耦合性，体现了封装的思想，但两者是不同的：
    a. 单一职责原则注重的是职责，而接口隔离原则注重的是对接口依赖的隔离。
    b. 单一职责原则主要是约束类，它针对的是程序中的实现和细节；接口隔离原则主要约束接口，主要针对抽象和程序整体框架的构建。

### 6. 开闭原则（Open Closed Principle) ###

***对扩展开放***，对修改关闭。开闭原则的含义是：当应用的需求改变时，在不修改软件实体的源代码或者二进制代码的前提下，可以扩展模块的功能，使其满足新的需求。






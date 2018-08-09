# JVM内部核心组件
## 几个概念
   JVM内部组件、 JVM内存模型
   JVM内存分配、JVM内存管理模型
   Java内存模型
## JVM主要分为三部分：堆、栈、非堆内存（方法区，驻留字符串） 
### 1、堆上面存储的是应用数据类型的实例；
### 2、栈当中存储的是变量的引用，
### 3、方法区主要存储的是运行时常量池Constant pool，以及类、方法相关的数据

![image](https://qph.ec.quoracdn.net/main-qimg-6a756e9e071fd02fd5cdc409bd40cd02.webp)

各组件内部使用见说明： 
https://www.quora.com/What-is-the-architecture-of-JVM-and-responsibility-of-each-component-in-JVM-Java-virtual-machine


# JVM内存管理模型

![image](https://ss0.baidu.com/6ONWsjip0QIZ8tyhnq/it/u=4044078498,420259557&fm=173&app=25&f=JPEG?w=640&h=172&s=E0D3CF32C57340281E4B68520300E0FA)

https://baijiahao.baidu.com/s?id=1606480770208000096&wfr=spider&for=pc

Jdk1.6及之前：常量池分配在永久代 。

Jdk1.7：有，但已经逐步“去永久代” 。

Jdk1.8及之后：无(java.lang.OutOfMemoryError: PermGen space,这种错误将不会出现在JDK1.8中)。

  ## -Xms（堆内存最小值） -Xmx （堆内存最大值）
  
  经过多次Minor GC之后到年老代
  
  年轻代分为3部分： Enden区和两个Survior区
 ###  年轻带空间的要点：
- [x]  大多数信件的对象都位于Eden区
- [x]  当Eden区被对象填满时，就会执行Minor GC。并把所有存活下来的对象转移到其中的一个survior区。
- [x]  Minor GC同样会检查活下来的对象，并把他们转移到另一个Survior区。 这样在一段时间内，总会有一个空的Suvior区。
- [x] 经过多次GC周期后，仍然存活下来的对象会被转移到年老代内存空间。通常这是在年轻带有资格提升到年老代前通过设定年龄阀值来完成的。

  
  
  ![image](https://www.java-mindmap.com/store/thumbs/2018/0401/012101101fpm.png)
  
 
 
  

    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
    
   
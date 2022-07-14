# 初识面向对象



![20220513131216](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220513131216.png)





![20220513131415](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220513131415.png)











# 方法回顾和加深



![20220513131645](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220513131645.png)











# 对象的创建分析

1. 类的创建：` public class Student()` 

   1. 包括 public（权限控制关键字）+class（类关键字）+Student（类名）
   2. 类里面包括 类的属性和方法

2. **类的实例化 也就是具体的一个对象**

   1. 比如学生类的**实例化**就是一个具体的学生
   2. 如何实例化 `Student student=new Student()`
      1. 类名+具体实例的名字=（赋值号）+new（关键字）+类名（）（类名+括号）

3. 类的一些方法

   1. 构造函数

      1. 无参构造函数

      2. 带参构造函数 

      3. ` public+类名（）{}`

         构造器：

         1. 和类名相同
         2. 没有返回值

         作用：

         		1. new 本质在调用构造方法
           		2. 初始化对象的值

         注意：

         ​	1. 定义带参构造之后，如果想使用无参构造，显示的定义一个无参的构造（就是得写出构造函数）

           		1. alt+insert（快速生成构造函数）



![20220521133613](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521133613.png)



# 面向对象的三大特性

1. **封装（数据隐藏）**
   1. 属性私有 get set
   2. 只通过方法进行 设置或者得到对应属性的值
      1. 属性私有
      2. get 
      3. set
   3. 优点：
      1. 提高了程序的可维护性
      2. 统一了接口
      3. 减少了属性的暴露，比较安全
2. **继承（extends）**
   1. ![20220521134517](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521134517.png)



2. ​			![	](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521135440.png)

   通过super可以在子类中比较容易的调用父类的构造方法等

   1. 方法的重写
   2. ![20220521140716](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521140716.png)

   3. 子类重写了父类方法之后，父类再调用的此方法就是子类重写之后的方法

   4. 父类可以引用子类` A a=new B()`B->A
     4

​		

3. **多态**
   1. 父类的引用可以指向子类
   2. 强制转换 高转低
   3.  在java中，多态是**同一个行为具有多个不同表现形式或形态的能力**；多态就是同一个接口，使用不同的实例而执行不同操作。 多态的优点：1、消除类型之间的耦合关系；2、可替换性；3、可扩充性；4、接口性；5、灵活性；6、简化性。 （就是通过重写方法实现多态）
   4. 同一个接口不同的表现形式

   ![20220521141900](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521141900.png)

   ![20220521142237](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521142237.png)

   5. instanceof
      1.  作用是测试它左边的对象是否是它右边的类的实例 
      2. A instanceof B 判断A是否是B的实例![20220521144055](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521144055.png)

# 抽 象类和接口

1. 抽象类

   1. 相当于c++的虚基类
   2. 其子类必须可以覆盖抽象类的方法
   3. 不能new 只能靠子类继承去实现它里面的一些方法 
   4.  抽象类不能实例化对象，所以抽象类必须被继承 
   5. 把一些要实现的方法进行抽象 子类直接去实现就行
   6.   在Java中抽象类表示的是一种继承关系，**一个类只能继承一个抽象类，而一个类却可以实现多个接口**。 
   7.  抽象类**必须有子类**，使用extends继承，一个子类只能继承一个抽象类；
      （4）子类（如果不是抽象类）则**必须覆写抽象类之中的全部抽象方法**（如果子类没有实现父类的抽象方法，则必须将子类也定义为为[abstract](https://so.csdn.net/so/search?q=abstract&spm=1001.2101.3001.7020)类。）； 

   ![20220521145106](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521145106.png)

2. 接口

   1. ![20220521145202](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521145202.png)

   2. 提供了一组约束规则（方法的抽象）然后通过类去具体实现接口的约束规则

![20220521145947](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521145947.png)

# 内部类以及oop实战



![20220521150007](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220521150007.png)








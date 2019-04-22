# **四、java**

# **测试一下**
## **基础**

### **1.Java 语言的优点**

面向对象,平台无关,内存管理,安全性,多线程,Java 是解释型的

### **2.Java 和 C++的区别**

**1.** **多重继承**(java接口多重,类不支持,C++支持)

**2.** **自动内存管理**

**3.** **预处理功能**

**4.** **goto语句**(java不支持)

**5.** **引用与指针**。在Java中不可能直接操作对象本身，所有的对象都由一个引用指向，必须通过这个引用才能访问对象本身，包括获取成员变量的值，改变对象的成员变量，调用对象的方法等。而在C++中存在引用，对象和指针三个东西，这三个东西都可以访问对象。其实，Java中的引用和C++中的指针在概念上是相似的，他们都是存放的对象在内存中的地址值，只是在Java中，引用丧失了部分灵活性，比如Java中的引用不能像C++中的指针那样进行**加减运算**。

### **3.值传递和引用传递**

变量被值传递，意味着传递了**变量的一个副本**。因此，就算是改变了变量副本，也不会影响源对象的值。

对象被引用传递，意味着传递的并不是实际的对象，而是**对象的引用**。因此，外部对引用对象所做的改变会反映到所有的对象上。 java本质上还是值传递，如方法调用的时候传入一个对象引用进去，在方法栈中会构建一个副本和该引用变量值相同指向同一个地址。如果改变引用的值不会对改变传入的引用的值。

### **4.静态变量和实例变量的区别**

**在语法定义上的区别**：静态变量前要加 static 关键字，而实例变量前则不加。

**在程序运行时的区别**：实例变量属于某个对象的属性，必须创建了实例对象，其中的实例变量才会被分配空间，才能使用这个实例变量。静态变量不属于某个实例对象，而是属于类，所以也称为类变量，只要程序加载了类的字节码，不用创建任何实例对象，静态变量就会被分配空间，静态变量就可以被使用了。总之，实例变量必须创建对象后才可以通过这个对象来使用，静态变量则可以直接使用类名来引用。

### **5.JDK 包.**

JDK 常用的 package:

**·** **java.lang**：这个是系统的基础类，比如 String 等都是这里面的，这个 package 是唯一一个可以不用 import 就可以使用的 Package

**·** **java.io**: 这里面是所有输入输出有关的类，比如文件操作等

**·** **java.net**: 这里面是与网络有关的类，比如 URL,URLConnection 等。

**·** **java.util**: 这个是系统辅助类，特别是集合类 Collection,List,Map 等。

**·** **java.sql**: 这个是数据库操作的类，Connection, Statememt，ResultSet 等

### **6.JDK, JRE 和 JVM 的区别**

JDK,JRE和JVM 是 Java 编程语言的核心概念。尽管它们看起来差不多，作为程序员我们也不怎么关心这些概念，但是它们是不同的针对特定目的的产品。这是一道常见的 Java 面试题，而本文则会一一解释这些概念并给出它们之间的区别。

**1）Java 开发工具包 (JDK)**

Java 开发工具包是 Java 环境的**核心组件，并提供编译、调试和运行一个 Java 程序所需的所有工具，可执行文件和二进制文件**。包括java基础jar包、虚拟机、javac等可执行文件等。JDK 是一个平台特定的软件，有针对 Windows，Mac 和 Unix 系统的不同的安装包。可以说 JDK 是 JRE 的超集，它包含了 JRE 的 Java 编译器，调试器和核心类。

**2）Java 虚拟机(JVM)**

JVM 是 Java 编程语言的核心。当我们运行一个程序时，JVM 负责将字节码转换为特定机器代码。JVM 也是平台特定的，并提供核心的 Java 方法，例如内存管理、垃圾回收和安全机制等。JVM 是可定制化的，我们可以通过 Java 选项(java options)定制它，比如配置 JVM 内存的上下界。JVM 之所以被称为虚拟的是因为它提供了一个不依赖于底层操作系统和机器硬件的接口。这种独立于硬件和操作系统的特性正是 Java 程序可以一次编写多处执行的原因。

**3）Java 运行时环境(JRE)**

JRE 是 JVM 的实施实现，它提供了运行 Java 程序的平台。**JRE 包含了 JVM、Java 二进制文件和其它成功执行程序的类文件**。JRE 不包含任何像 Java 编译器、调试器之类的开发工具。如果你只是想要执行 Java 程序，你只需安装 JRE 即可，没有安装 JDK 的必要。

**JDK, JRE 和 JVM 的区别**

· JDK 是用于开发的而 JRE 是用于运行 Java 程序的。

· JDK 和 JRE 都包含了 JVM，从而使得我们可以运行 Java 程序。

· JVM 是 Java 编程语言的核心并且具有平台独立性。

**即时编译器(JIT)**

JIT 是 JVM 的一部分，它可以在同一时间编译类似的字节码来优化将字节码转换为机器特定语言的过程相似的字节码，从而将优化字节码转换为机器特定语言的过程，这样减少转换过程所需要花费的时间。

### **7.是否可以在 static 环境中访问非 static 变量**

static 变量在 Java 中是属于类的，它在所有的实例中的值是一样的。当类被Java虚拟机载入的时候，会对 static 变量进行初始化。如果你的代码尝试不用实例来访问非 static 的变量，编译器会报错，因为这些变量还没有被创建出来，还没有跟任何实例关联上。

### **Java 中的 final关键字用法**

· (1)修饰类：表示该类不能被继承；

· (2)修饰方法：表示方法不能被覆盖；

· (3)修饰变量：表示变量只能一次赋值以后值不能被修改（常量）。

### **assert**

assertion(断言)在软件开发中是一种常用的调试方式，很多开发语言中都支持这种机制。一般来说，assertion **用于保证程序最基本、关键的正确性**。assertion 检查通常在开发和测试时开启。为了提高性能，在软件发布后， assertion 检查通常是关闭的。在实现中，断言是一个包含布尔表达式的语句，在执行这个语句时假定该表达式为 true；如果表达式计算为 false，那么系统会报告一个 AssertionError。

断言用于调试目的：

​	assert(a > 0); // throws an AssertionError if a <= 0

断言可以有两种形式：

​	assert Expression1;

​	assert Expression1 : Expression2 ;

Expression1 应该总是产生一个布尔值。 Expression2 可以是得出一个值的任意表达式；这个值用于生成显示更多调试信息的**字符串消息** 断言在默认情况下是禁用的，要在编译时启用断言，需使用 source 1.4 标记：

​	javac -source 1.4 Test.java

要在运行时启用断言，可使用 -enableassertions 或者 -ea 标记。 要在运行时选择禁用断言，可使用 -da 或者 -disableassertions 标记。

### **final, finally, finalize 的区别?**

**final**：修饰符（关键字）有三种用法：如果一个类被声明为final，意味着它不能再派生出新的子类，即不能被继承，因此它和 abstract 是反义词。将变量声明为 final，可以保证它们在使用中不被改变，被声明为 final 的变量必须在声明时给定初值，而在以后的引用中只能读取不可修改。被声明为 final 的方法也同样只能使用，不能在子类中被重写。

**finally**：通常放在 try…catch 的后面构造总是执行代码块，这就意味着程序无论正常执行还是发生异常，这里的代码只要 JVM 不关闭都能执行，可以将释放外部资源的代码写在 finally 块中。

**finalize**：Object 类中定义的方法，Java 中允许使用 finalize() 方法在垃圾收集器将对象从内存中清除出去之前做必要的清理工作。这个方法是由垃圾收集器在销毁对象时调用的，通过重写finalize() 方法可以整理系统资源或者执行其他清理工作。

### **& 和 &&**

& 和 && 都可以用作逻辑与的运算符，表示逻辑与（and），当运算符两边的表达式的结果都为 true 时，整个运算结果才为 true，否则，只要有一方为 false，则结果为 false。

**&& 还具有短路的功能**，即如果第一个表达式为 false，则不再计算第二个表达式.& 还可以用作位运算符，当 & 操作符两边的表达式不是 boolean 类型时，& 表示按位与操作.

### **用最有效率的方法算出 2 乘以 8 等於几**

2 << 3，因为将一个数左移 n 位，就相当于乘以了 2 的 n 次方，那么，一个数乘以 8 只要将其左移 3 位即可，而位运算 cpu 直接支持的，效率最高，所以，2 乘以 8 等於几的最效率的方法是 2 << 3 。

### **char 型变量**

char 类型可以存储一个中文汉字，因为 Java 中使用的编码是** Unicode**（不选择任何特定的编码，直接使用字符在字符集中的编号，这是统一的唯一方法），一个 char 类型占 2 个字节（16bit），所以放一个中文是没问题的。

补充：使用 Unicode 意味着字符在 JVM 内部和外部有不同的表现形式，在 JVM 内部都是 Unicode，当这个字符被从 JVM 内部转移到外部时（例如存入文件系统中），需要进行编码转换。所以 Java 中有字节流和字符流，以及在字符流和字节流之间进行转换的转换流，如 InputStreamReader 和 OutputStreamReader.

### **String 和StringBuilder、StringBuffer 的区别**

答：Java 平台提供了两种类型的字符串：String 和StringBuffer / StringBuilder，它们可以储存和操作字符串。其中 String 是**只读**字符串，也就意味着 String 引用的字符串内容是不能被改变的。

而 StringBuffer 和 StringBuilder 类表示的字符串对象可以直接进行修改。StringBuilder 是 JDK 1.5 中引入的，它和 StringBuffer 的方法完全相同，区别在于它是在单线程环境下使用的，因为它的所有方面都没有被 synchronized 修饰，因此它的效率也比 StringBuffer 略高。

有一个面试题问：有没有哪种情况用 + 做字符串连接比调用 StringBuffer / StringBuilder 对象的 append 方法性能更好？如果连接后得到的字符串在静态存储区中是早已存在的，那么用+做字符串连接是优于 StringBuffer / StringBuilder 的 append 方法的。

### **String不可变性**

至于为什么要把 String 类设计成不可变类，是它的用途决定的。其实不只 String，很多 Java 标准类库中的类都是不可变的。在开发一个系统的时候，我们有时候也需要设计不可变类，来传递一组相关的值，这也是面向对象思想的体现。不可变类有一些优点，比如因为它的对象是只读的，**所以多线程并发访问也不会有任何问题**。当然也有一些缺点，比如每个不同的状态都要一个对象来代表，可能会造成性能上的问题。所以 Java 标准类库还提供了一个可变版本，即 StringBuffer。

Javac 编译可以对字符串常量直接相加的表达式进行优化，不必要等到运行期去进行加法运算处理，而是在**编译时去掉其中的加号**，直接将其编译成一个这些常量相连的结果。所以 String s=“a”+”b”+”c”+”d”;只生成一个对象.

### **不可变对象**

如果一个对象，在它创建完成之后，不能再改变它的状态，那么这个对象就是不可变的。不能改变状态的意思是，不能改变对象内的成员变量，包括基本数据类型的值不能改变，引用类型的变量不能指向其他的对象，引用类型指向的对象的状态也不能改变。 **如何创建不可变类**

\1. 将类声明为final，所以它不能被继承

\2. 将所有的成员声明为私有的，这样就不允许直接访问这些成员

\3. 对变量不要提供setter方法

\4. 将所有可变的成员声明为final，这样只能对它们赋值一次

\5. 通过构造器初始化所有成员，进行深拷贝(deep copy):如果某一个类成员不是原始变量(primitive)或者不可变类，必须通过在成员初始化(in)或者get方法(out)时通过深度clone方法，来确保类的不可变。

\6. 在getter方法中，不要直接返回对象本身，而是克隆对象，并返回对象的拷贝



### **为什么String要设计成不可变的\****

在Java中将String设计成不可变的是综合考虑到各种因素的结果,如内存,同步,数据结构以及安全等方面的考虑.

\1. 

字符串常量池的需要. 字符串池的实现可以在运行时节约很多heap空间，因为不同的字符串变量都指向池中的同一个字符串。但如果字符串是可变的，那么String interning将不能实现(译者注：String interning是指对不同的字符串仅仅只保存一个，即不会保存多个相同的字符串。)，因为这样的话，如果变量改变了它的值，那么其它指向这个值的变量的值也会一起改变。

\2. 

\3. 

线程安全考虑。 同一个字符串实例可以被多个线程共享。这样便不用因为线程安全问题而使用同步。字符串自己便是线程安全的。

\4. 

\5. 

类加载器要用到字符串，不可变性提供了安全性，以便正确的类被加载。譬如你想加载java.sql.Connection类，而这个值被改成了myhacked.Connection，那么会对你的数据库造成不可知的破坏。

\6. 

\7. 

支持hash映射和缓存。 因为字符串是不可变的，所以在它创建的时候hashcode就被缓存了，不需要重新计算。这就使得字符串很适合作为Map中的键，字符串的处理速度要快过其它的键对象。这就是HashMap中的键往往都使用字符串。

\8. 



### **什么是 Java 序列化，如何实现 Java 序列化**

序列化就是一种用来处理对象流的机制，**所谓对象流也就是将对象的内容进行流化**。**可以对流化后的对象进行读写操作，也可将流化后的对象传输于网络之间**。序列化是为了解决在对对象流进行读写操作时所引发的问题。

序列化的实现：将需要被序列化的类实现 Serializable 接口，该接口没有需要实现的方法， implements Serializable 只是为了标注该对象是可被序列化的，然后使用一个输出流(如：FileOutputStream)来构造一个ObjectOutputStream(对象流)对象，接着，使用ObjectOutputStream对象的writeObject(Object obj)方法就可以将参数为obj的对象写出(即保存其状态)，要恢复的话则用输入流。

### **错误和异常的区别(Error vs Exception)**

\1. java.lang.Error: Throwable 的子类，**用于标记严重错误,表示系统级的错误和程序不必处理的异常**。合理的应用程序不应该去 try/catch 这种错误。是恢复不是不可能但很困难的情况下的一种严重问题；**比如内存溢出**，不可能指望程序能处理这样的情况；

java.lang.Exception: Throwable 的子类，**表示需要捕捉或者需要程序进行处理的异常，是一种设计或实现问题**；也就是说，它表示如果程序运行正常，从不会发生的情况。并且鼓励用户程序去 catch 它。

\1. Error 和 RuntimeException 及其子类都是**未检查的异常（unchecked exceptions）**，而所有其他的 Exception 类都是检查了的异常（checked exceptions）

**checked exceptions**: **上下文环境有关，即使程序设计无误，仍然可能因使用的问题而引发．通常是从一个可以恢复的程序中抛出来的，并且最好能够从这种异常中使用程序恢复**。比如 **FileNotFoundException**, ParseException 等。检查了的异常发生在编译阶段，必须要使用 try…catch（或者 throws ）否则编译不通过。

**unchecked exceptions**:通常是如果一切正常的话本不该发生的异常，但是的确发生了。 **发生在运行期，具有不确定性，主要是由于程序的逻辑问题所引起的**。比如 ArrayIndexOutOfBoundException, ClassCastException 等。从语言本身的角度讲，程序不该去 catch 这类异常，虽然能够从诸如 RuntimeException 这样的异常中 catch 并恢复，但是并不鼓励终端程序员这么做，因为完全没要必要。因为这类错误本身就是 bug，应该被修复，出现此类错误时程序就应该立即停止执行。 因此，面对 Errors 和 unchecked exceptions 应该让程序自动终止执行，程序员不该做诸如 try/catch 这样的事情，而是应该查明原因，修改代码逻辑。

RuntimeException：RuntimeException体系包括错误的类型转换、数组越界访问和试图访问空指针等等。处理 RuntimeException 的原则是：如果出现 RuntimeException，那么一定是程序员的错误。例如，可以通过检查数组下标和数组边界来避免数组越界访问异常。其他（IOException等等）checked 异常一般是外部错误，例如试图从文件尾后读取数据等，这并不是程序本身的错误，而是在应用环境中出现的外部错误。

常见 非检查异常：

· NullPointerException

· ArrayIndexOutOfBoundException

· IllegalArgumentException

· OutOfMemoryError

常见的检查异常:

· ClassNotFoundException

· IOException

· FileNotFoundException

### **try{} 里的 return 语句**

Java 允许在 finally 中改变返回值的做法是不好的，因为如果存在 finally 代码块，try 中的 return 语句不会立马返回调用者，而是记录下返回值待 finally 代码块执行完毕之后再向调用者返回其值，然后如果在 finally 中修改了返回值，这会对程序造成很大的困扰

### **运行时异常与受检异常有何异同？**

答：异常表示程序运行过程中可能出现的非正常状态，运行时异常表示虚拟机的通常操作中可能遇到的异常，是一种常见运行错误，只要程序设计得没有问题通常就不会发生。受检异常跟程序运行的**上下文环境有关，即使程序设计无误，仍然可能因使用的问题而引发**。Java编译器要求方法必须声明抛出可能发生的受检异常，但是并不要求必须声明抛出未被捕获的运行时异常。异常和继承一样，是面向对象程序设计中经常被滥用的东西，神作《Effective Java》中对异常的使用给出了以下指导原则：

**·** **不要将异常处理用于正常的控制流（设计良好的API不应该强迫它的调用者为了正常的控制流而使用异常）**

**·** **对可以恢复的情况使用受检异常，对编程错误使用运行时异常**

**·** **避免不必要的使用受检异常（可以通过一些状态检测手段来避免异常的发生）**

**·** **优先使用标准的异常**

**·** **每个方法抛出的异常都要有文档**

**·** **保持异常的原子性**

**·** **不要在 catch 中忽略掉捕获到的异常**

### **throws、throw、try、catch、finally**

一般情况下是用 try 来执行一段程序，如果出现异常，系统会抛出（throw）一个异常，这时候你可以通过它的类型来捕捉（catch）它，或最后（finally）由缺省处理器来处理；try 用来指定一块预防所有“异常”的程序；catch 子句紧跟在 try 块后面，用来指定你想要捕捉的“异常”的类型；throw 语句用来明确地抛出一个“异常”；throws用来标明一个成员函数可能抛出的各种“异常”；finally 为确保一段代码不管发生什么“异常”都被执行一段代码；

### **常见的runtime exception**

1、NullPointerException 空指针引用异常 2、ClassCastException - 类型强制转换异常。 3、IllegalArgumentException - 传递非法参数异常。 4、IndexOutOfBoundsException - 下标越界异常 5、UnsupportedOperationException - 不支持的操作异常 6、ArithmeticException - 算术运算异常 7、ArrayStoreException - 向数组中存放与声明类型不兼容对象异常 8、NegativeArraySizeException - 创建一个大小为负数的数组错误异常 9、NumberFormatException - 数字格式异常 10、SecurityException - 安全异常

### **throw和throws有什么区别**

throw关键字用来在程序中明确的抛出异常，相反，throws语句用来表明方法不能处理的异常。每一个方法都必须要指定哪些异常不能处理，所以方法的调用者才能够确保处理可能发生的异常，多个异常是用逗号分隔的。

### **Switch能否用string做参数？**

Java 1.7之前不可以，java 1.7后String可以作为参数。 整型（byte，short int，int，long int），枚举类型，boolean，字符型(char),字符串都可以，唯独浮点型不可以

### **equals与==的区别**

\1. == 是一个运算符。

\2. Equals则是string对象的方法，可以.（点）出来。 我们比较无非就是这两种 1、基本数据类型比较 2、引用对象比较

1、基本数据类型比较 　==比较两个值是否相等。相等为true 否则为false； equals不能直接用于基本类型的比较。需要将基本类型转换为包装器进行比较。

2、引用对象比较 ==和equals都是比较栈内存中的地址是否相等 。相等为true 否则为false； 　 需注意几点：

1、string是一个特殊的引用类型。对于两个字符串的比较，不管是 == 和 equals 这两者比较的都是字符串是否相同；

2、当你创建两个string对象时，内存中的地址是不相同的，你可以赋相同的值。 　　所以字符串的内容相同。引用地址不一定相同，（相同内容的对象地址不一定相同），但反过来却是肯定的；

3、基本数据类型比较(string 除外) == 和 Equals 两者都是比较值；

### **Object有哪些公用方法**

· protected Object clone()创建并返回此对象的一个副本。

· public boolean equals(Object obj)指示其他某个对象是否与此对象“相等”。

· protected void finalize()当垃圾回收器确定不存在对该对象的更多引用时，由对象的垃圾回收器调用此方法。

· public final native Class< ? > getClass() 返回此 Object 的运行时类。

· public int hashCode()返回该对象的哈希码值。

· public String toString()返回该对象的字符串表示。

· public void notify()唤醒在此对象监视器上等待的单个线程。

· public void notifyAll()唤醒在此对象监视器上等待的所有线程。

· public void wait()在其他线程调用此对象的 notify() 方法或 notifyAll() 方法前，导致当前线程等待。

· public void wait(long timeout)在其他线程调用此对象的 notify() 方法或 notifyAll() 方法，或者超过指定的时间量前，导致当前线程等待。

· public void wait(long timeout, int nanos)在其他线程调用此对象的 notify() 方法或

注意：

\1. 

如果一个类实现了Cloneable,Object的clone方法就返回该对象的逐域拷贝，否则就会抛出CloneNotSupportException异常。java.lang.Cloneable 是一个标示性接口，不包含任何方法（详见《effective java》 p46）。

\2. 

\3. 

覆盖equals（）时总要覆盖hashCode（）（详见《effective java》p39） 在每个覆盖equals方法的类中也必须覆盖hashCode方法，如果不这样做就会导致Object.hashCode的通用约定---**相等的对象必须具有相等的散列码的约定**，从而导致该类无法集合所有基于散列集合一起工作，这样的集合有HashMap,HashSet和HashTable。HashMap等使用Key对象的hashCode()和equals()方法去决定key-value对的索引。如果将equals相等的对象认为是同一个对象的话，那么put方法将对象放在一个散列桶，而get方法可能从另一个散列桶获取该对象，因为这两个方法传入的对象虽然equals相同，但hashCode可能不同，而hashMap根据hashCode去定位散列桶位置导致出现在不同的散列桶中。

\4. 

Hashcode的作用。

\1. hashCode的存在主要是用于查找的快捷性，如Hashtable，HashMap等，hashCode是用来在散列存储结构中确定对象的存储地址的；

\2. 比较对象是否相同。

一下是关于hashCode的约定： 1、如果两个对象相同，就是适用于equals(java.lang.Object) 方法，那么这两个对象的hashCode一定要相同；

2、如果对象的equals方法被重写，那么对象的hashCode也尽量重写，并且产生hashCode使用的对象，一定要和equals方法中使用的一致，否则就会违反上面提到的第2点；

3、两个对象的hashCode相同，并不一定表示两个对象就相同，也就是不一定适用于equals(java.lang.Object) 方法，只能够说明这两个对象在散列存储结构中，如Hashtable，他们“存放在同一个篮子里”。

### **String、StringBuffer与StringBuilder的区别**

\1. String是字符串常量，是不可变类。如果要操作少量的数据用

\2. StringBuffer是字符串变量，是线程安全的。多线程操作字符串缓冲区 下操作大量数据

\3. StringBuilder是字符串变量，非线程安全。单线程操作字符串缓冲区 下操作大量数据

速度：StringBuilder > StringBuffer > String

String 对象的字符串拼接其实是被 JVM 解释成了 StringBuffer 对象的拼接，所以这些时候 String 对象的速度并不会比 StringBuffer 对象慢，而特别是以下的字符串对象生成中， String 效率是远要比 StringBuffer 快的：

String S1 = “This is only a” + “ simple” + “ test”;

StringBuffer Sb = new StringBuilder(“This is only a”).append(“simple”).append(“ test”);



### **try catch finally，try里有return，finally还执行么？**

1)不管有木有出现异常，finally块中代码都会执行

2)当try和catch中有return时，finally仍然会执行

3)finally是在return后面的表达式运算后执行的（此时并没有返回运算后的值，而是先把要返回的值保存起来，**不管finally中的代码怎么样，返回的值都不会改变**，任然是之前保存的值），所以函数返回值是在finally执行前确定的

4)finally中最好不要包含return，否则程序会提前退出，返回值不是try或catch中保存的返回值

### **UnsupportedOperationException是什么**

UnsupportedOperationException是用于表明操作不支持的异常。在JDK类中已被大量运用，在集合框架java.util.Collections.UnmodifiableCollection将会在所有add和remove操作中抛出这个异常。

### **Excption与Error包结构**

### **java值传递问题**

\1. 对象就是传引用

\2. 原始类型就是传值

\3. String，Integer, Double等immutable类型因为没有提供自身修改的函数，每次操作都是新生成一个对象，所以要特殊对待。可以认为是传值。

Integer 和 String 一样。保存value的类变量是Final属性，无法被修改，只能被重新赋值／生成新的对象。 当Integer 做为方法参数传递进方法内时，对其的赋值都会导致 原Integer 的引用被 指向了方法内的栈地址，失去了对原类变量地址的指向。对赋值后的Integer对象做得任何操作，都不会影响原来对象。

### **Integer**



### **修饰符顺序**

public protected private abstract static final transient volatile synchronized native strictfp

 

 

 

## **面向对象**

下面列出了面向对象软件开发的优点：

· (1) 代码开发模块化，更易维护和修改。

· (2) 代码复用。

· (3) 增强代码的可靠性和灵活性。

· (4) 增加代码的可理解性。 面向对象编程有很多重要的特性，比如：封装，继承，多态和抽象

### **Java面向对象的三个特征与含义**

一、**继承**：

\1. 

概念：**继承是从已有的类中派生出新的类，新的类能吸收已有类的数据属性和行为，并能扩展新的能力.**

\2. 

\3. 

好处：提高代码的复用，缩短开发周期。

\4. 

二、**多态**：

\1. 

概念：多态（Polymorphism）按字面的意思就是“**多种状态，即同一个实体同时具有多种形式**"。一般表现形式是程序在运行的过程中，同一种类型在不同的条件下表现不同的结果。多态也称为动态绑定，一般是在运行时刻才能确定方法的具体执行对象，这个过程也称为动态委派。

\2. 

\3. 

好处：

\4. 

· 将接口和实现分开，改善代码的组织结构和可读性，还能创建可拓展的程序。

· 消除类型之间的耦合关系。允许将多个类型视为同一个类型。

· 一个多态方法的调用允许有多种表现形式

三、**封装**：

\1. 

概念：**就是把对象的属性和行为（或服务）结合为一个独立的整体，并尽可能隐藏对象的内部实现细节**。

\2. 

\3. 

好处：

\4. 

· 隐藏信息，实现细节。让客户端程序员无法触及他们不应该触及的部分。

· 允许可设计者可以改变类内部的工作方式而不用担心会影响到客户端程序员。

### **Overload 和 Override**

Overload 是重载的意思，Override 是覆盖的意思，也就是重写。 **重载 Overload** 表示**同一个类**中可以有多个名称相同的方法，但这些方法的参数列表各不相同（即参数个数或类型不同）。

**重写 Override** 表示**子类**中的方法可以与**父类**中的某个**方法的名称和参数完全相同**，通过子类创建的实例对象调用这个方法时，将调用子类中的定义方法，这相当于把父类中定义的那个完全相同的方法给覆盖了，这也是面向对象编程的多态性的一种表现。**子类覆盖父类的方法时，只能比父类抛出更少的异常，或者是抛出父类抛出的异常的子异常**，因为子类可以解决父类的一些问题，不能比父类有更多的问题。**子类方法的访问权限只能比父类的更大，不能更小**。如果**父类的方法是private类型，那么，子类则不存在覆盖的限制**，相当于子类中增加了一个全新的方法。

至于 Overloaded 的方法是否可以改变返回值的类型这个问题，要看你倒底想问什么呢？这个题目很模糊。如果几个 Overloaded 的方法的参数列表不一样，它们的返回者类型当然也可以不一样。但我估计你想问的问题是：如果两个方法的参数列表完全一样，是否可以让它们的返回值不同来实现重载 Overload。这是不行的，我们可以用反证法来说明这个问题，因为我们有时候调用一个方法时也可以不定义返回结果变量，即不要关心其返回结果，例如，我们调用 map.remove(key) 方法时，虽然 remove 方法有返回值，但是我们通常都不会定义接收返回结果的变量，这时候假设该类中有两个名称和参数列表完全相同的方法，仅仅是返回类型不同，Java 就无法确定编程者倒底是想调用哪个方法了，因为它无法通过返回结果类型来判断。

Override 可以翻译为覆盖，从字面就可以知道，它是覆盖了一个方法并且对其重写，以求达到不同的作用。对我们来说最熟悉的覆盖就是对接口方法的实现，在接口中一般只是对方法进行了声明，而我们在实现时，就需要实现接口声明的所有方法。除了这个典型的用法以外，我们在继承中也可能会在子类覆盖父类中的方法。**在覆盖要注意以下的几点**：

**1.** **覆盖的方法的标志必须要和被覆盖的方法的标志完全匹配，才能达到覆盖的效果；**

**2.** **覆盖的方法的返回值必须和被覆盖的方法的返回一致,或者是其子类（协变返回类型)；**

**3.** **覆盖的方法所抛出的异常必须和被覆盖方法的所抛出的异常一致，或者是其子类；**

**4.** **被覆盖的方法不能为 private，否则在其子类中只是新定义了一个方法，并没有对其进行覆盖。**

Overload 对我们来说可能比较熟悉，可以翻译为重载，它是指我们可以定义一些名称相同的方法，通过定义不同的输入参数来区分这些方法，然后再调用时，VM 就会根据不同的参数样式，来选择合适的方法执行。在使用**重载要注意**以下的几点：

\1. **在使用重载时只能通过不同的参数样式。**例如，不同的参数类型，不同的参数个数，不同的参数顺序（当然，同一方法内的几个参数类型必须不一样，例如可以是 fun(int,float)，但是不能 fun(int,int)）；

**2.** **不能通过访问权限、返回类型、抛出的异常进行重载**；

**3.** **方法的异常类型和数目不会对重载造成影响**；

### **接口和抽象类的区别**

Java 提供和支持创建抽象类和接口。它们的实现有共同点，不同点在于：

\1. 接口中所有的**方法**隐含的都是抽象的。而抽象类则可以同时包含抽象和非抽象的方法。

\2. 类可以实现很多个接口，但是只能**继承**一个抽象类

\3. 类如果要**实现**一个接口，它必须要实现接口声明的所有方法。但是，类可以不实现抽象类声明的所有方法，当然，在这种情况下，类也必须得声明成是抽象的。

\4. 抽象类可以在不提供接口方法实现的情况下实现接口。

\5. Java 接口中声明的**变量**默认都是 final 的。抽象类可以包含非 final 的变量。

\6. Java 接口中的**成员函数**默认是 public 的。抽象类的成员函数可以是 private，protected 或者是 public 。

\7. 接口是绝对抽象的，不可以被实例化。抽象类也不可以被实例化，但是，如果它包含 main 方法的话是可以被调用的

### **接口**

接口很重要，为了说明情况，这里稍微啰嗦点：

· (1) 接口用于描述系统对外提供的所有服务,因此接口中的成员常量和方法**都必须是公开(public)类型**的,确保外部使用者能访问它们；

· (2) 接口仅仅描述系统能做什么,但不指明如何去做,所以接口中的方法**都是抽象(abstract)方法**；

· (3) 接口不涉及和任何具体实例相关的细节,因此接口没有构造方法,不能被实例化,没有实例变量，**只有静态（static）变量**；

· (4) 接口的中的变量是所有实现类**共有的**，既然共有，肯定是不变的东西，因为变化的东西也不能够算共有。所以**变量是不可变(final)类型，也就是常量了**。

· (5) 接口中不可以定义变量.如果接口可以定义变量，但是接口中的方法又都是抽象的，在接口中无法通过行为来修改属性。有的人会说了，没有关系，可以通过 实现接口的对象的行为来修改接口中的属性。这当然没有问题，但是考虑这样的情况。如果接口 A 中有一个public 访问权限的静态变量 a。按照 Java 的语义，我们可以不通过实现接口的对象来访问变量 a，通过 A.a = xxx; 就可以改变接口中的变量 a 的值了。正如抽象类中是可以这样做的，**那么实现接口 A 的所有对象也都会自动拥有这一改变后的 a 的值了，也就是说一个地方改变了 a，所有这些对象中 a 的值也都跟着变了**。这和抽象类有什么区别呢，怎么体现接口更高的抽象级别呢，怎么体现接口提供的统一的协议呢，那还要接口这种抽象来做什么呢？所以接口中 不能出现变量，如果有变量，就和接口提供的统一的抽象这种思想是抵触的。所以接口中的属性必然是常量，只能读不能改，这样才能为实现接口的对象提供一个统 一的属性。 通俗的讲，你认为是要变化的东西，就放在你自己的实现中，不能放在接口中去，接口只是对一类事物的属性和行为更高层次的抽象。对修改关闭，对扩展（不同的实现 implements）开放，接口是**对开闭原则**的一种体现。 所以：**接口的方法默认是 public abstract**；

接口中不可以定义变量即只能定义常量(加上final修饰就会变成常量)。**所以接口的属性默认是 public static final 常量，且必须赋初值**。 **注意**：final 和 abstract 不能同时出现。

### **两个对象值相同(x.equals(y) == true)，但却可有不同的 hash code，这句话对不对？**

答：不对，如果两个对象 x 和 y 满足 x.equals(y) == true，它们的哈希码（hash code）应当相同。 Java 对于 eqauls 方法和 hashCode 方法是这样规定的：

**·** **(1)如果两个对象相同（equals 方法返回 true ），那么它们的 hashCode 值一定要相同**；

**·** **(2)如果两个对象的 hashCode 相同，它们并不一定相同**。当然，你未必要按照要求去做，但是如果你违背了上述原则就会发现在使用容器时，相同的对象可以出现在 Set 集合中，同时增加新元素的效率会大大下降（对于使用哈希存储的系统，如果哈希码频繁的冲突将会造成存取性能急剧下降）。

**·** **(3)如果对象的equals方法的比较操作所用到的信息没有被修改,那么对同一个对象调用多次,hashCode方法都必须始终如一地返回同一个整数**.

补充：关于 equals 和 hashCode 方法，很多 Java 程序都知道，但很多人也就是仅仅知道而已，在 Joshua Bloch 的大作《Effective Java》（很多软件公司，《Effective Java》、《Java 编程思想》以及《重构：改善既有代码质量》是 Java 程序员必看书籍，如果你还没看过，那就赶紧去亚马逊买一本吧）中是这样介绍 equals 方法的：首先 equals 方法必须满足**自反性（x.equals(x) 必须返回true）、对称性（x.equals(y) 返回true时，y.equals(x) 也必须返回 true）、传递性（x.equals(y)和y.equals(z)都返回 true 时，x.equals(z)也必须返回true）和一致性**（当x和y引用的对象信息没有被修改时，多次调用x.equals(y)应该得到同样的返回值），而且对于任何非 null 值的引用 x，x.equals(null) 必须返回 false。实现高质量的 equals 方法的**诀窍**包括：

**·** **使用 == 操作符检查“参数是否为这个对象的引用”**；

**·** **使用 instanceof 操作符检查“参数是否为正确的类型”**；

**·** **对于类中的关键属性，检查参数传入对象的属性是否与之相匹配**；

**·** **编写完 equals 方法后，问自己它是否满足对称性、传递性、一致性**；

**·** **重写 equals 时总是要重写 hashCode**；

**·** **不要将 equals 方法参数中的 Object 对象替换为其他的类型，在重写时不要忘掉 @Override 注解**。

### **什么是 AOP 和 OOP，IOC 和 DI**

1）面向对象编程（Object Oriented Programming，OOP，面向对象程序设计）是一种计算机编程架构。AOP 是 OOP 的延续，是 Aspect Oriented Programming 的缩写，意思是面向方面编程。 将通用需求功能从不相关类之中分离出来；同时，能够使得很多类共享一个行为，一旦行为发生变化，不必修改很多类，只要修改这个行为就可以。AOP 就是这种实现分散关注的编程方法，它将“关注”封装在“方面”中

2）控制反转 IOC(Inversion of Control) 控制指的就是程序相关类之间的依赖关系.传统观念设计中, 通常由调用者来创建被调用者的实例, **在 Spring 里,创建被调用者的工作不再由调用者来完成,而是由 Spring 容器完成，依赖关系被反转了，称为控制反转，目的是为了获得更好的扩展性和良好的可维护性**。依赖注入(Dependency injection)创建被调用者的工作由 Spring 容器完成，然后注入调用者，因此也称依赖注入。控制反转和依赖注入是**同一个概念**。



## **集合框架**

![img](file:///C:\Users\NIGHT_~1\AppData\Local\Temp\ksohtml7664\wps1.png) 

Collection：List列表，Set集 
Map：Hashtable，HashMap，TreeMap 

Collection: 是单列集合 
List: 元素是有序的(元素存取是有序)、可重复. 有序的 collection，可以对列表中每个元素的插入位置进行精确地控制。可以根据元素的整数索引（在列表中的位置）访问元素，并搜索列表中的元素。可存放重复元素，元素存取是有序的。

List接口中常用类：

· Vector：线程安全，但速度慢，已被ArrayList替代。底层数据结构是**数组结构**

· ArrayList：线程不安全，查询速度快。底层数据结构是数组结构

· LinkedList：线程不安全。增删速度快。底层数据结构是**链表结构**

Set(集) 元素不可重复: 取出元素的方法只有迭代器。**不可以存放重复元素，元素存取是无序的**。Set接口中常用的类:

· HashSet：线程不安全，内部是基于**散列函数**实现,存取速度快。它是如何保证元素唯一性的呢？依赖的是元素的hashCode方法和euqals方法。

· LinkedHashSet:具有HashSet的查询速度，且内部采用**双向链表维护元素的顺序**（默认保持插入顺序排序，如果初始化时将accessOrder设置为true将使用最近最少顺序，即最近使用的元素插在链表尾部）。元素必须实现hashCode(）方法。内部是由链表实现。

· TreeSet：线程不安全，可以对Set集合中的元素**进行排序**,底层采用了**红黑树**。它的排序是如何进行的呢？通过compareTo或者compare方法中的来保证元素的唯一性。元素是以二叉树的形式存放的。意味着TreeSet中的元素要实现Comparable接口。或者有一个自定义的比较器。

Map　是一个双列集合:

· Hashtable:线程安全，速度快。底层是**哈希表数据**结构。是同步的。不允许null作为键，null作为值。

· Properties:用于配置文件的定义和操作，使用频率非常高，同时键和值都是字符串。是集合中可以和IO技术相结合的对象。(到了IO在学习它的特有和io相关的功能。)

· HashMap:线程不安全，速度慢。底层也是哈希表数据结构。是不同步的。 允许null作为键，null作为值。替代了Hashtable.

· LinkedHashMap: 可以保证HashMap集合有序。存入的顺序和取出的顺序一致。

· TreeMap：可以用来对Map集合中的键进行排序.底层是采用红黑树．

Collection 和 Collections的区别：

· Collection是集合类的上级接口，子接口主要有Set 和List、Map。

· Collections是针对集合类的一个帮助类，提供了操作集合的工具方法：一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作。

以下这张图能体现出上面总结的集合关系： ![img](file:///C:\Users\NIGHT_~1\AppData\Local\Temp\ksohtml7664\wps2.jpg)

### **接口：Collection**

Collection是最基本的集合接口，**一个Collection代表一组Object，即Collection的元素（Elements）**。一些Collection允许相同的元素而另一些不行。一些能排序而另一些不行。Java SDK不提供直接继承自Collection的类，Java SDK提供的类都是继承自Collection的“子接口”如List和Set。

所有实现Collection接口的类都必须提供**两个标准的构造函数**：无参数的构造函数用于创建一个空的Collection，有一个Collection参数的构造函数用于创建一个新的Collection，这个新的Collection与传入的Collection有相同的元素。后一个构造函数允许用户复制一个Collection。

主要的一个接口方法：boolean add(Ojbect c)虽然返回的是boolean，但不是表示添加成功与否，这个返回值表示的意义是add()执行后，集合的内容是否改变了（就是元素的数量、位置等有无变化）。类似的addAll，remove，removeAll，remainAll也是一样的。

用Iterator模式实现遍历集合,Collection**有一个重要的方法：iterator()，返回一个Iterator（迭代器），用于遍历集合的所有元素**。Iterator模式可以把访问逻辑从不同的集合类中抽象出来，从而避免向客户端暴露集合的内部结构。典型的用法如下：

Iterator it = collection.iterator(); // 获得一个迭代器

while(it.hasNext()) {

​	Object obj = it.next(); // 得到下一个元素

}

不需要维护遍历集合的“指针”，所有的内部状态都由Iterator来维护，而这个Iterator由集合类通过工厂方法生成。每一种集合类返回的Iterator具体类型可能不同，但它们都实现了Iterator接口，因此，我们不需要关心到底是哪种Iterator，它只需要获得这个Iterator接口即可，这就是接口的好处，面向对象的威力。

要确保遍历过程顺利完成，必须保证遍历过程中不更改集合的内容（Iterator的remove()方法除外），所以，确保遍历可靠的原则是：只在一个线程中使用这个集合，或者在多线程中对遍历代码进行同步。由Collection接口派生的两个接口是List和Set。

### **Collection包结构，与Collections的区别**

· Collection是集合类，包含List有序列表，Set无序集合以及Map双列集合 Collection是集合类的上级接口，子接口主要有Set 和List、Map。

· Collections是针对集合类的一个**帮助类**，提供了操作集合的工具方法：一系列静态方法实现对各种集合的搜索、排序、线程安全化等操作

### **List、Map、Set 三个接口存储元素时各有什么特点**

1）**List**是有序的Collection，使用此接口**能够精确的控制每个元素插入的位置**。用户能够使用索引（元素在List中的位置，类似于数组下标）来访问List中的元素，这类似于Java的数组。和下面要提到的Set不同，List**允许有相同**的元素。

除了具有Collection接口必备的iterator()方法外，List还提供一个listIterator()方法，返回一个ListIterator接口，和标准的Iterator接口相比，**ListIterator**多了一些add()之类的方法，允许添加，删除，设定元素，还能向前或向后遍历。实现List接口的常用类有LinkedList，ArrayList，Vector和Stack。

2）**Set** 是一种不包含重复的元素的 Collection，即任意的两个元素 e1 和 e2 都有e1.equals(e2)=false，**Set 最多有一个 null 元素**。

3）**Map** 接口 ：请注意，Map 没有继承 Collection 接口，Map 提供 key 到 value 的映射．底层使用散列函数。

### **Map、Set、List、Queue、Stack的特点与用法**

· Set集合类似于一个罐子，"丢进"Set集合里的多个对象之间没有明显的顺序。

· List集合代表元素有序、可重复的集合，集合中每个元素都有其对应的顺序索引。

· Stack是Vector提供的一个子类，用于模拟"栈"这种数据结构(LIFO后进先出)

· Queue用于模拟"队列"这种数据结构(先进先出 FIFO)。

· Map用于保存具有**"映射关系"**的数据，因此Map集合里保存着两组值

### **Array和ArrayList有何区别？什么时候更适合用Array**

Array可以容纳**基本类型和对象**，而**ArrayList只能容纳对象**。 Array是**指定大小的**，而ArrayList大小是固定的。

**Array没有提供ArrayList那么多功能**，比如addAll、removeAll和iterator等。尽管ArrayList明显是更好的选择，但也有些时候Array比较好用。

如果列表的大小已经指定，大部分情况下是存储和遍历它们。

对于遍历**基本数据类型**，尽管Collections使用自动装箱来减轻编码任务，在指定大小的基本类型的列表上工作也会变得很慢。

如果你要使用**多维数组**，使用[][]比List更容易。

### **ArrayList 和 LinkedList**

ArrayList 和 LinkedList 都实现了 List 接口，他们有以下的不同点：

· ArrayList 是基于索引的数据接口，它的底层是数组。它可以以O(1)时间复杂度对元素进行**随机访问**。与此对应，LinkedList 是以元素列表的形式存储它的数据，每一个元素都和它的前一个和后一个元素链接在一起，在这种情况下，查找某个元素的时间复杂度是O(n)。

· 相对于 ArrayList，LinkedList的**插入，添加，删除操作速度更快**，因为当元素被添加到集合任意位置的时候，不需要像数组那样重新计算大小或者是更新索引。

· LinkedList 比 ArrayList **更占内存**，因为 LinkedList 为每一个节点存储了两个引用，一个指向前一个元素，一个指向下一个元素。

### **ArrayList和Vector异同点**

ArrayList和Vector在很多时候都很类似：

· （1）两者都是基于索引的，内部由一个**数组支持**。

· （2）两者维护插入的顺序，我们可以**根据插入顺序来获取元素**。

· （3）ArrayList和Vector的迭代器实现都是**fail-fast**的。

· （4）ArrayList和Vector两者**允许null值**，也可以使用索引值对元素进行随机访问。

以下是ArrayList和Vector的不同点：

· （1）Vector是**同步**的，而ArrayList不是。然而，如果你寻求在迭代的时 候对列表进行改变，你应该使用CopyOnWriteArrayList。

· （2）ArrayList比Vector**快**，它因为有同步，不会过载。

· （3）ArrayList更加通用，因为我们可以使用Collections工具类轻易地获取同步列表和只读列表。

### **遍历一个List有哪些不同的方式**

List<String> strList = new ArrayList<>();

//使用for-each循环

for(String obj : strList){

  System.out.println(obj);

}

//using iterator

Iterator<String> it = strList.iterator();

while(it.hasNext()){

​	String obj = it.next();

​	System.out.println(obj);

}

使用**迭代器更加线程安全，因为它可以确保，在当前遍历的集合元素被更改的时候，它会抛出ConcurrentModificationException**。

### **LinkedList 和PriorityQueue 的区别**

**·** **Queue中只有两个实现类LinkedList 和PriorityQueue**。他们都是属于队列，即拥有先进先出（FIFO）的特点。而这两个类的区别在于他们的排序行为并非性能。

· LinkedList 支持双向列表操作，

· PriorityQueue 按优先权控制队列元素的出队次序。（列表中的排序顺序是通过实现Comparable来控制的）

### **HashMap的工作原理**

HashMap在Map.Entry**静态内部类**实现中存储key-value对。HashMap使用哈希算法，在put和get方法中，它使用hashCode()和equals()方法。当我们通过传递key-value对调用put方法的时候，HashMap使用Key hashCode()和哈希算法来找出存储key-value对的索引。Entry存储在LinkedList中，所以如果映射到同一个桶后，它使用equals()方法来检查传递的key是否entry已经存在，如果存在，它会覆盖value，如果不存在，它会创建一个新的entry然后保存。当我们通过传递key调用get方法时，它再次使用hashCode()来找到数组中的索引，然后使用equals()方法找出正确的Entry，然后返回它的值。

其它关于HashMap比较重要的问题**是容量、加载因子和阀值调整**。HashMap默认的初始容量是16，**负荷系数是0.75**。阀值是为负荷系数乘以容量，无论何时我们尝试添加一个entry，如果map的大小比阀值大的时候，HashMap会对map的内容进行重新哈希，且使用更大的容量。**容量总是2的幂**，所以如果你知道你需要存储大量的key-value对，比如缓存从数据库里面拉取的数据，使用正确的容量和负荷系数对HashMap进行初始化是个不错的做法。

### **HashMap实现原理**

**数据结构**： HashMap基于哈希算法，采用链地址法来避免hash冲突，所以其内部采用**链表数组数据结构**。我们通过put()和get()方法储存和获取对象。HashMap里面实现一个静态内部类Entry, Entry其重要的属性有key , value, next.用该Entry定义了一个链表的数组用来存放数据，这种方法叫做连地址法，是为了避免hash冲突。

HashMap的存取实现:

\1. put

首先会根据对象的hashCode计算得到**散列桶坐标**（数组下表），因为数组中存放的是**Entry链表结构**，所以还需要对该链表进行遍历，通过调用key.equals方法判断是否存在该key，如果存在则修改内容。如果不存在则**采用头插入**的方式在链表头部插入一个新的节点存储这个新的映射关系。

**null key总是存放在Entry[]数组的第一个元素，而且仅保留一个null key**。插入成功后，判断实际存在的键值对数量size是否超多了最大容量threshold，如果超过，进行扩容。

\1. get

首先也会根据hashCode的值定位到散列桶，并遍历存放在该桶中的链表。如果存在的该key则返回对应的value，**如果不存在则返回null**。（比较时调用key.equals) 具体比较：

(e.hash == hash && ((k = e.key) == key || key.equals(k)))）

· 3） 再散列rehash过程：

Entry[]的长度一定后，随着map里面数据的越来越长，超过了加载因子，必须调整table的大小。每次将数组拓展到原来数据长度的两倍。这时，需要创建一张新表，将原表的映射到新表中。 注：**在存储当前值后再判断是否进行扩展容器**，这样的扩容方式有可能导致拓展后容器没有被使用造成浪费。

\1. 红黑树的引入

为了避免链表过长，查询速度变为了线性，java1.8 引入了红黑树。当链表长度大于8时就采用红黑树结构。

解决hash冲突的常用方法办法：

\1. 开放定址法（线性探测再散列，二次探测再散列，伪随机探测再散列）

\2. 再哈希法

\3. 链地址法

\4. 建立一个公共溢出区

Java中hashmap的解决办法就是采用的链地址法。

HashMap实现原理：

·

· [美团点评][Java 8系列之重新认识HashMap](https://tech.meituan.com/java-hashmap.html) | 写的比较好

### **我们能否使用任何类作为Map的key**

我们可以使用任何类作为Map的key，然而在使用它们之前，需要考虑以下几点：

· （1）**如果类重写了equals()方法，它也应该重写hashCode()方法**。

· （2）**类的所有实例需要遵循与equals()和hashCode()相关的规则**。请参考之前提到的这些规则。

· （3）如果一个类没有使用equals()，你不应该在hashCode()中使用它。

· （4）**用户自定义key类的最佳实践是使之为不可变的**，这样，hashCode()值可以被缓存起来，拥有更好的性能。不可变的类也可以确保hashCode()和equals()在未来不会改变，这样就会解决与可变相关的问题了。

比如，我有一个类MyKey，在HashMap中使用它

// 传递给MyKey的name参数被用于equals()和hashCode()中

MyKey key = new MyKey('Pankaj'); //assume hashCode=1234

myHashMap.put(key, 'Value');

// 以下的代码会改变key的hashCode()和equals()值

key.setName('Amit'); //assume new hashCode=7890

// 下面会返回null，因为HashMap会尝试查找存储同样索引的key，而key已被改变了，匹配失败，返回null

myHashMap.get(new MyKey('Pankaj'));

那就是为何String和Integer被作为HashMap的key大量使用

### **如何决定选用HashMap还是TreeMap**

对于在**Map中插入、删除和定位元素这类操作，HashMap是最好的选择**。然而，**假如你需要对一个有序的key集合进行遍历，TreeMap是更好的选择**。基于你的collection的大小，也许向HashMap中添加元素会更快，将map换为TreeMap进行有序key的遍历。

### **HashMap和HashTable的区别**

HashMap和Hashtable都实现了Map接口，因此很多特性非常相似。但是，他们有以下不同点：

· HashMap允许键和值是null，而Hashtable不允许键或者值是null。

· Hashtable是同步的，而HashMap不是。因此，HashMap更适合于单线程环境，而Hashtable适合于多线程环境。

· HashMap的**迭代器(Iterator)是fail-fast迭代器**，而Hashtable的**enumerator(列举)迭代器不是fail-fast的**。所以当有其它线程改变了HashMap的结构（增加或者移除元素），将会抛出ConcurrentModificationException，但迭代器本身的remove()方法移除元素则不会抛出ConcurrentModificationException异常。但这并不是一个一定发生的行为，要看JVM。这条同样也是Enumeration和Iterator的区别。一般认为Hashtable是一个遗留的类。如果你寻求在迭代的时候修改Map，你应该使用CocurrentHashMap

<http://www.importnew.com/7010.html>

### **Enumeration 接口和 Iterator 接口的区别**

· Enumeration 速度是 Iterator 的2倍，**同时占用更少的内存**。

· Iterator远远比 Enumeration 安全，因为其他线程不能够修改正在被 iterator 遍历的集合里面的对象。

· Iterator 允许调用者删除底层集合里面的元素，这对 Enumeration 来说是不可能的。

### **通过迭代器fail-fast属性**

每次我们尝试获取下一个元素的时候，Iterator fail-fast属性检查当前集合结构里的任何改动。如果发现任何改动，它抛出ConcurrentModificationException。Collection中所有Iterator的实现都是按fail-fast来设计。在遍历一个集合的时候，我们可以使用并发集合类来避免ConcurrentModificationException，比如使用CopyOnWriteArrayList，而不是ArrayList

### **快速失败(fail-fast)和安全失败(fail-safe)的区别**

Iterator的fail-fast属性与当前的集合共同起作用，因此它不会受到集合中任何改动的影响。java.util包下面的所有的集合类都是快速失败的，而java.util.concurrent包下面的所有的类都是安全失败的。快速失败的迭代器会抛出ConcurrentModificationException异常，而安全失败的迭代器永远不会抛出这样的异常。

### **HashSet,TreeSet,LinkedHashSet 之间的区别**

首先这三个类都是实现了Set接口，并且LinkedHashSet继承HashSet ，TreeSet实现了SortedSet。所以它们都拥有Set的基本特性，如：集合中的元素不能重复（这个需要和容器转载的类中的**equals()方法**有关）. 这三个容器所接受的类必须实现equals() 方法:

**·** **HashSet**： 为查询速度所设计的，存入HashSet的元素必须定义hashCode()方法。内部是基于散列函数实现。

**·** **TreeSet**： 实现了SortedSet（SortedSet的元素可以保证处于排序状态）,所以内部的元素是保持一定次序的（次序与元素实现的compareTo()方法有关），且底层是树状结构。使用它可以从Set中提取有序的序列。要求存入的元素必须实现**Comparable接口**,或则需要传入一个比较器**Comparator**。否则报ClassCastException。内部采用了**红黑树**实现。

**·** **LinkedHashSet**： 具有HashSet的查询速度，且内部链表维护元素的顺序（按插入顺序排序）。元素必须实现hashCode(）方法。内部是由链表实现。

### **HashMap ,LinkedHashMap ,TreeMap,WeakHashMap,ConcurrentHashMap,IdentityHashMap的区别**

**Map** 中任何键的比较都是通过equals进行比较的，所以如果键用于映射的话需要由恰当的hashCode() 方法。如果键值用于TreeMap，它必须实现Comparable。

**HashMap** 基于散列表来的实现，即使用hashCode()进行快速查询元素的位置，显著提高性能。插入和查询“键值对”的开销是固定的。可以通过设置容量和负载因子，以调整容器的性能。

**LinkedHashMap**, 类似于HashMap,但是迭代遍历它时，取得“键值对”的顺序是其**插入的次序**，只比HashMap慢一点。而在迭代访问时反而更快，**因为它使用链表维护内部次序**。

**TreeMap**, 是基于**红黑树**的实现。实现了SortedMap，SortedMap 可以确保键处于排序状态。所以查看“键”和“键值对”时，所有得到的结果都是经过排序的，次序由Comparable或Comparator决定。SortedMap拥有其他额外的功能，如：Comparator comparator()返回当前Map使用的Comparator或者null. T firstKey() 返回Map的第一个键，T lastKey() 返回最后一个键。SortedMap headMap(toKey),生成一个键小于toKey的Map子集。SortedMap tailMap(fromKey) 也是生成一个子集。TreeMap是唯一的带有subMap()方法的Map,它可以返回一个子树

**WeakHashMap** 表示**弱键映射**，允许释放映射所指向的对象。这是为了解决某类特殊问题而设计的，如果映射之外没有引用指向某个“键”，则“键”可以被垃圾收集器回收。

**ConcurrentHashMap** 一种线程安全的Map,它不涉及同步加锁。

**IdentityHashMap** 使用==代替equals() 对“键”进行比较的散列映射。专为解决特殊问题而设计。

**Hashtable** (已经摒弃了)

[Map 综述（二）：彻头彻尾理解 LinkedHashMap](http://blog.csdn.net/justloveyou_/article/details/71713781)

### **Map接口提供了哪些不同的集合视图**

Map接口提供三个集合视图：

（1）**Set keyset()**：**返回map中包含的所有key的一个Set视图**。**集合是受map支持的，map的变化会在集合中反映出来，反之亦然**。当一个迭代器正在遍历一个集合时，若map被修改了（除迭代器自身的移除操作以外），迭代器的结果会变为未定义。集合支持通过**Iterator**的Remove、Set.remove、removeAll、retainAll和clear操作进行元素移除，从map中移除对应的映射。它不支持add和addAll操作。

（2）**Collection values()**：**返回一个map中包含的所有value的一个Collection视图**。这个collection受map支持的，map的变化会在collection中反映出来，反之亦然。当一个迭代器正在遍历一个collection时，若map被修改了（除迭代器自身的移除操作以外），迭代器的结果会变为**未定义**。集合支持通过Iterator的Remove、Set.remove、removeAll、retainAll和clear操作进行元素移除，从map中移除对应的映射。它不支持add和addAll操作

（3）Set< Map.Entry < K,V > > entrySet()：**返回一个map钟包含的所有映射的一个集合视图**。这个集合受map支持的，map的变化会在collection中反映出来，反之亦然。当一个迭代器正在遍历一个集合时，若map被修改了（除迭代器自身的移除操作，以及对迭代器返回的entry进行setValue外），**迭代器的结果会变为未定义**。集合支持通过Iterator的Remove、Set.remove、removeAll、retainAll和clear操作进行元素移除，从map中移除对应的映射。它不支持add和addAll操作。

### **hashCode()和equals()方法有何重要性**

**HashMap使用Key对象的hashCode()和equals()方法去决定key-value对的索引**。当我们试着从HashMap中获取值的时候，这些方法也会被用到。如果这些方法没有被正确地实现，在这种情况下，两个不同Key也许会产生相同的hashCode()和equals()输出，HashMap将会认为它们是相同的，然后覆盖它们，而非把它们存储到不同的地方。同样的，所有不允许存储重复数据的集合类都使用hashCode()和equals()去查找重复，所以正确实现它们非常重要。equals()和hashCode()的实现应该遵循以下规则：

（1）如果o1.equals(o2)，那么o1.hashCode() == o2.hashCode()总是为true的。

（2）如果o1.hashCode() == o2.hashCode()，并不意味着o1.equals(o2)会为true。

### **Iterator是什么**

Iterator接口提供遍历任何Collection的接口。我们可以从一个Collection中使用迭代器方法来获取迭代器实例。迭代器取代了Java集合框架中的Enumeration。迭代器允许调用者在迭代过程中移除元素。

### **Iterator和ListIterator的区别是什么**

下面列出了他们的区别：

· Iterator 可用来遍历 Set 和 List 集合，但是 ListIterator 只能用来遍历 List 。

· Iterator 对集合只能是前向遍历，ListIterator 既可以前向也可以后向。

· ListIterator 实现了 Iterator 接口，并包含其他的功能，比如：增加元素，替换元素，获取前一个和后一个元素的索引，等等。

### **为何Iterator接口没有具体的实现**

Iterator接口定义了遍历集合的方法，但它的实现则是集合实现类的责任。每个能够返回用于遍历的Iterator的集合类都有它自己的Iterator实现内部类。

这就允许集合类去选择迭代器是fail-fast还是fail-safe的。比如，ArrayList迭代器是fail-fast的，而CopyOnWriteArrayList迭代器是fail-safe的

### **EnumSet是什么**

java.util.EnumSet是使用**枚举类型**的集合实现。当集合创建时，枚举集合中的所有元素必须来自单个指定的枚举类型，可以是显示的或隐示的。EnumSet是不同步的，不允许值为null的元素。它也提供了一些有用的方法，比如copyOf(Collection c)、of(E first,E…rest)和complementOf(EnumSet s)。

### **哪些集合类是线程安全的**

Vector、HashTable、Properties和Stack是同步类，所以它们是线程安全的，可以在多线程环境下使用。Java1.5并发API包括一些集合类，允许迭代时修改，因为它们都工作在集合的克隆上，所以它们在多线程环境中是安全的。

### **BockingQueue是什么**

Java.util.concurrent.BlockingQueue是一个队列，在进行检索或移除一个元素的时候，它会等待队列变为非空；当在添加一个元素时，它会等待队列中的可用空间。BlockingQueue接口是Java集合框架的一部分，主要用于实现生产者-消费者模式。我们不需要担心等待生产者有可用的空间，或消费者有可用的对象，因为它都在BlockingQueue的实现类中被处理了。Java提供了集中BlockingQueue的实现，比如ArrayBlockingQueue、LinkedBlockingQueue、PriorityBlockingQueue,、SynchronousQueue等。

### **我们如何对一组对象进行排序**

如果我们需要对一个对象数组进行排序，我们可以使用Arrays.sort()方法。如果我们需要排序一个对象列表，我们可以使用Collections.sort()方法。两个类都有用于自然排序（使用Comparable）或基于标准的排序（使用Comparator）的重载方法sort()。Collections内部使用数组排序方法，所有它们两者都有相同的性能，只是Collections需要花时间将列表转换为数组。

### **Comparable和Comparator接口**

Comparable & Comparator 都是用来实现集合中元素的比较、排序的，只是 Comparable 是在集合内部定义的方法实现的排序，Comparator 是在集合外部实现的排序，所以，如想实现排序，就需要在集合外定义 Comparator 接口的方法或在集合内实现 Comparable 接口的方法。

· 

\1. Comparator位于包java.util下，而Comparable位于包java.lang下

· 

**1.** **Comparable 是在集合内部定义的方法实现的排序,Comparator 是在集合外部实现的排序**.Comparable 是一个对象本身就已经支持自比较所需要实现的接口,自定义的类要在加入list容器中后能够排序，可以实现Comparable接口.在用Collections类的sort方法排序时，如果不指定Comparator，那么就以自然顺序排序.而 Comparator 是一个专用的比较器，当这个对象不支持自比较或者自比较函数不能满足你的要求时，你可以写一个比较器来完成两个对象之间大小的比较。**用 Comparator 是策略模式（strategy design pattern），就是不改变对象自身，而用一个策略对象（strategy object）来改变它的行为**。

· 

\1. Comparator定义了俩个方法，分别是int compare(T o1,T o2)和boolean equals(Object obj).Comparable接口只提供了int compareTo(T o)方法.

也就是说我定义了一个Person类，这个类实现了Comparable接口，那么当我实例化Person类的person1后，我想比较person1和一个现有的Person对象person2的大小时，我就可以这样来调用：

person1.comparTo(person2)

通过返回值就可以判断了；而此时如果你定义了一个PersonComparator（实现了Comparator接口）的话，那你就可以这样：

PersonComparator   comparator=   new   PersonComparator();

comparator.compare(person1,person2);。

### **Java集合框架是什么？说出一些集合框架的优点？**

每种编程语言中都有集合，最初的Java版本包含几种集合类：Vector、Stack、HashTable和Array。随着集合的广泛使用，Java1.2提出了囊括所有集合接口、实现和算法的集合框架。在保证线程安全的情况下使用泛型和并发集合类，Java已经经历了很久。它还包括在Java并发包中，阻塞接口以及它们的实现。集合框架的部分优点如下：

· （1）使用核心集合类降低开发成本，而非实现我们自己的集合类。

· （2）随着使用经过严格测试的集合框架类，代码质量会得到提高。

· （3）通过使用JDK附带的集合类，可以降低代码维护成本。

· （4）复用性和可操作性。

### **集合框架中的泛型有什么优点**

Java1.5引入了泛型，所有的集合接口和实现都大量地使用它。泛型允许我们为集合提供一个可以容纳的对象类型，因此，如果你添加其它类型的任何元素，它会在编译时报错。这避免了在运行时出现ClassCastException，因为你将会在编译时得到报错信息。泛型也使得代码整洁，我们不需要使用显式转换和instanceOf操作符。它也给运行时带来好处，因为不会产生类型检查的字节码指令。

### **为何Map接口不继承Collection接口**

尽管Map接口和它的实现也是集合框架的一部分，但Map不是集合，集合也不是Map。因此，Map继承Collection毫无意义，反之亦然。

如果Map继承Collection接口，那么元素去哪儿？Map包含key-value对，它提供抽取key或value列表集合的方法，但是它不适合“一组对象”规范。

### **为什么集合类没有实现Cloneable和Serializable接口**

Collection接口指定一组对象，对象即为它的元素。**如何维护这些元素由Collection的具体实现决定**。例如，一些如List的Collection实现允许重复的元素，而其它的如Set就不允许。**很多Collection实现有一个公有的clone方法。然而，把它放到集合的所有实现中也是没有意义的。这是因为Collection是一个抽象表现。重要的是实现**。

**当与具体实现打交道的时候，克隆或序列化的语义和含义才发挥作用**。所以，具体实现应该决定如何对它进行克隆或序列化，或它是否可以被克隆或序列化。

**在所有的实现中授权克隆和序列化，最终导致更少的灵活性和更多的限制**。特定的实现应该决定它是否可以被克隆和序列化。

### **与Java集合框架相关的有哪些最好的实践**

· (1) 根据需要选择正确的集合类型。比如，如果指定了大小，我们会选用Array而非ArrayList。如果我们想根据插入顺序遍历一个Map，我们需要使用TreeMap。如果我们不想重复，我们应该使用Set。如果涉及到堆栈，队列等操作，应该考虑用List，对于需要快速插入，删除元素，应该使用LinkedList，如果需要快速随机访问元素，应该使用ArrayList。

· (2) 如果程序在单线程环境中，或者访问仅仅在一个线程中进行，考虑非同步的类，其效率较高，如果多个线程可能同时操作一个类，应该使用同步的类。

· (3) 要特别注意对哈希表的操作，作为key的对象要正确复写equals和hashCode方法。使用JDK提供的不可变类作为Map的key，可以避免自己实现hashCode()和equals()。 性。

· (4) 尽量返回接口而非实际的类型，如返回List而非ArrayList，这样如果以后需要将ArrayList换成LinkedList时，客户端代码不用改变。这就是针对抽象编程。

· (5) 尽可能使用Collections工具类，或者获取只读、同步或空的集合，而非编写自己的实现。它将会提供代码重用性，它有着更好的稳定性和可维护

· (6) 一些集合类允许指定**初始容量**，所以如果我们能够估计到存储元素的数量，我们可以使用它，就避免了重新哈希或大小调整。

· (7) 基于接口编程，而非基于实现编程，它允许我们后来轻易地改变实现。

· (8) 总是使用类型安全的泛型，避免在运行时出现ClassCastException。

### **ArrayList 是否支持序列化**

支持， 实现了　serlializable接口，并实现了以下两个方法：

 `private void writeObject(java.io.ObjectOutputStream s)`

​	`throws java.io.IOException{`

​	`// Write out element count, and any hidden stuff`

​	`int expectedModCount = modCount;`

​	`s.defaultWriteObject();`

`` 

​	`// Write out size as capacity for behavioural compatibility with clone()`

​	`s.writeInt(size);`

`` 

​	`// Write out all elements in the proper order.`

​	`for (int i=0; i<size; i++) {`

​	    `s.writeObject(elementData[i]);`

​	`}`

`` 

​	`if (modCount != expectedModCount) {`

​	    `throw new ConcurrentModificationException();`

​	`}`

   `}`

`` 

   `/**`

​    `\* Reconstitute the <tt>ArrayList</tt> instance from a stream (that is,`

​    `\* deserialize it).`

​    `*/`

   `private void readObject(java.io.ObjectInputStream s)`

​	`throws java.io.IOException, ClassNotFoundException {`

​	`elementData = EMPTY_ELEMENTDATA;`

`` 

​	`// Read in size, and any hidden stuff`

​	`s.defaultReadObject();`

`` 

​	`// Read in capacity`

​	`s.readInt(); // ignored`

`` 

​	`if (size > 0) {`

​	    `// be like clone(), allocate array based upon size not capacity`

​	    `ensureCapacityInternal(size);`

`` 

​	    `Object[] a = elementData;`

​	    `// Read in all elements in the proper order.`

​	    `for (int i=0; i<size; i++) {`

​	        `a[i] = s.readObject();`

​	    `}`

​	`}`

   `}`

`ArrayList`

 `public Object clone() {`

​	`try {`

​	    `ArrayList<?> v = (ArrayList<?>) super.clone();`

​	    `v.elementData = Arrays.copyOf(elementData, size);`

​	    `v.modCount = 0;`

​	    `return v;`

​	`} catch (CloneNotSupportedException e) {`

​	    `// this shouldn't happen, since we are Cloneable`

​	    `throw new InternalError(e);`

​	`}`

​    `}`



## **多线程**

### **什么叫线程安全？举例说明**

多个线程访问某个类时，不管运行时环境采用何种调度方式或者这些线程将如何交替执行，并且在主调代码中不需要任何额外的同步或者协同，这个类都能表现出正确的行为，那么就称这个类是线程安全的。 比如无状态对象一定是线程安全的。

### **进程和线程的区别**

调度: 线程是调度的基本单位，进程是拥有资源的基本单位。同一进程的中线程的切换不会引起进程的切换，不同进程中进行线程切换会引起进程的切换。

拥有资源：进程是拥有资源的基本单位，线程除了自身的栈外一般不拥有资源。而是和其他线程共享同一进程中的资源。

系统开销：由于创建进程或者撤销进程时，系统都要分配和回收资源，如内存空间，I/O设备等，操作系统所付出的开销远大于创建或撤销进程时的开销。

### **volatile的理解**

**Volatile自身特性**：

\1. Volatile 是轻量级的synchronized，它在多处理器开发过程中保证了共享变量的“**可见性**”，可见性是指当一个线程的某个共享变量发生改变时，另一个线程能够读取到这个修改的值。Voaltile变量修饰的变量在进行写操作时在多核处理器下首先将当前处理器缓存行的数据写回到系统内存中。为了保证一致性，其他处理器嗅探到总线上传播的数据，发现数据被修改了使自己缓存地址的数据无效。

\2. Volatile 可以**禁止重排序**，

\3. Volatile 能保持单个简单volatile变量的读/写操作的具有原子性。但不能保证自增自减的**原子性**。

从**内存语义**来讲:

· volatile变量的写-读与锁的释放-获取具有相同语义，volatile的写与锁的释放有相同的内存语义，volatile读与锁的获取具有相同语义。

· 线程A写一个volatile变量，实质上是线程A向接下来要读这个volatile变量的某个线程发出消息

· 线程B读一个volatile变量，实质上是线程B接收了之前某个线程发出的消息。

· 线程A写volatile变量，随后线程B读这个变量，这个过程实质上线程A通过内存向B发送消息。

内存语义的实现，也是禁止重排序特性： 为了实现volatile内存语义，JMM限制了对volatile重排序做了限制：

\1. 当第二个操作是volatile写时，不管第一个操作时什么，都不能重排序。

\2. 当第一个操作是volatile读时，不管第二个操作是什么，都不能重排序。

\3. 当第一个操作是volatile写，第二个操作是volatile读时，不重排序。

为了实现volatile的内存语义，编译器生成字节码时，会在指令序列中插入内存屏障来禁止特定类型的处理器重排序。JMM采取保守策略:

\1. 在每个volatile写操作前面插入一个StoreStore屏障

\2. 在每个volatile写操作后面插入一个StoreLoad屏障

\3. 在每个volatile读操作后面插入一个LoadLoad屏障

\4. 在每个volatile读操作后面插入一个LoadStore屏障

具体参考《java并发编程的艺术》

### **原子性实现机制**

处理器提供总线锁定和缓存锁定两种方式来保证复杂内存操作的原子性。

总线型：就是使用处理器提供一个LOCK信号，当一个处理器在总线传输信号时，其他处理器的请求将被阻塞住，那么该处理独占内存。所以总线锁定开销大。

缓存锁定：内存区域如果被缓存在缓存行中，且在在lock期间被锁定，当它执行锁操作写回内存时，处理器总线不在锁定而是通过修改内部的内存地址并使用缓存一致性制阻止同时修改保证操作的原子性。缓存一致性进制两个以上的处理器同时修改内存区域数据，其他处理器回写被锁定并且使其缓存行无效。

### **Java原子性操作实现原理**

使用循环CAS实现原子性操作，CAS是在操作期间先比较旧值，如果旧值没有发生改变，才交换成新值，发生了变化则不交换。这种方式会产生以下几种问题：

\1. ABA问题，通过加版本号解决；

\2. 循环时间过长开销大，一般采用自旋方式实现；

\3. 只能保证一个共享变量的原子操作。

### **Java内存模型**

Java内存模型控制线程之间的通信，决定了一个线程对共享变量的写入何时对另一个线程可见。它属于语言级的内存模型，它确保在不同编译器和不同的处理平台之上，通过禁止特定类型的编译器重排序和处理器重排序，为程序员提供一致的内存可见性保证。JMM的核心目标是找到一个好的平衡点，一方面是为程序员提供足够强的内存可见性保证（提供happens-before规则），另一方面对编译器和处理器的限制尽可能地放松（只要不改变程序结果，怎么优化都可以）

**1.** **可见性保证**

为了提供内存可见性保证，JMM向程序员保证了以下hapens-before规则:

**1.** **程序顺序规则**：一个线程的每个操作happen-before与该线程的任意后续操作。

**2.** **监视器锁规则**：一个锁的解锁，happens-before于随后这个锁的加锁。

**3.** **Volatile变量规则**：对一个volatile域的写，happens-before于任意后续这个域的读。

**4.** **传递性**, 如果A happens-before B, 且B happens-before C 那么A happens-before C

**5.** **线程启动规则**：如果线程A执行操作ThreadB.start().那么线程A中的任意操作happens-before与线程B中的任意操作。

**6.** **线程结束规则**: 线程中的任何操作都必须在其线程检测到该线程已经结束之前执行，或者从Thread.join中成功返回，或者在调用Thread.isAlive时返回false.

**7.** **中断规则**:当一个线程在另一个线程上调用interrupt时，必须在被中断线程检测到interrupt调用之前执行(通过抛出InterruptedException,或者调用isInterrupted和interrupted)

**8.** **终结器规则**: 对象的构造函数必须在启动该对象的终结器之前执行完成。

**2) 禁止重排序**

为了保证内存可见性，java编辑器在生成指令序列的适当位置插入内存屏障指令来禁止特定类型的处理器重排序。

重排序：编译器和处理器为了优化程序性能对指令进行重新排序的一种手段。

· 

\1. 编译器优化的重排序: 编译器在不改变单线程程序语义的前提下可以重新安排语句顺序。

· 

\1. 指令级并行的重排序.现代处理器采用指令级并行技术来将多条指令重叠执行。如果不存在数据依赖性，处理器可以改变对应指令的执行顺序。

· 

\1. 内存系统重排序。由于处理器使用缓存和读/写缓冲区，这使得加载和存储操作看上去可能在乱序执行。

### **Final域的内存语义**

对于final域编译器和处理器要遵守两个重排序规则：

\1. 在构造器函数内对final域的写入，与随后把这个被构造对象的引用赋值给一个引用变量，这两个操作之间不能重排序。（保证了对象引用为任何线程可见之前，对象的final域已经被正确初始化过）

\2. 初次读一个包含final域的对象引用，与随后初次读这个final域这两个操作不能重排序。

为何保证其内存语义：可以为java程序员提供安全保证，只要对象是正确构造的，那么不需要使用同步就可以保证线程都能看到这个fianal域在构造函数中被初始化之后的值。

### **避免死锁的常见方法：**

· 1)避免一个线程同时获取多个锁

· 2)避免一个线程在锁内同时占用多个资源，尽量保证每个锁只占用一个资源

· 3)尝试使用定时锁，使用lock.tryLock(timeout)来替代使用内部锁机制。

· 4)对数据库锁，加锁和解锁必须在一个数据库连接里，否则会出现解锁失败的情况。

### **死锁的必要条件？怎么克服？**

答：产生死锁的四个必要条件：

**·** **互斥条件**：一个资源每次只能被一个进程使用。

**·** **请求与保持条件**：一个进程因请求资源而阻塞时，对已获得的资源保持不放。

**·** **不剥夺条件**:进程已获得的资源，在末使用完之前，不能强行剥夺。

**·** **循环等待条件**:若干进程之间形成一种头尾相接的循环等待资源关系。

这四个条件是死锁的必要条件，只要系统发生死锁，这些条件必然成立，而只要上述条件之一不满足，就不会发生死锁。

死锁的解决方法:

· 撤消陷于死锁的全部进程；

· 逐个撤消陷于死锁的进程，直到死锁不存在；

· 从陷于死锁的进程中逐个强迫放弃所占用的资源，直至死锁消失。

· 从另外一些进程那里强行剥夺足够数量的资源分配给死锁进程，以解除死锁状态

### **CountDownLatch(闭锁) 与CyclicBarrier(栅栏)的区别**

CountDownLatch: **允许一个或多个线程等待其他线程完成操作**.

CyclicBarrier：**让一组线程到达一个屏障(同步点)被阻塞，直到最后一个线程到达屏障时，所有被屏障拦截的线程才会往下执行**。

\1. 闭锁用于等待事件、栅栏是等待线程.

\2. 闭锁CountDownLatch做减计数，而栅栏CyclicBarrier则是加计数。

\3. CountDownLatch是一次性的，CyclicBarrier可以重用。

\4. CountDownLatch一个线程(或者多个)，等待另外N个线程完成某个事情之后才能执行。CyclicBarrier是N个线程相互等待，任何一个线程完成之前，所有的线程都必须等待。

CountDownLatch 是**计数器**, 线程完成一个就记一个,就像报数一样, 只不过是递减的.

而CyclicBarrier更像一个**水闸**, 线程执行就像水流, 在水闸处都会堵住, 等到水满(线程到齐)了, 才开始泄流.

### **execute 和submit的区别**

Execute()用于提交不需要返回值得任务，submit()用于提交需要返回值的任务，发挥Future类型的对象。

### **Shutdown和shutdownNow的区别**

它们的原理都是遍历线程池中的工作线程，然后逐个调用线程的Internet方法来中断线程，所以无法响应中断的任务可能永远无法终止。

ShutdownNow首先将线程池的状态设置成STOP, 然后尝试停止所有正在执行或暂停的任务，并返回等待执行任务的列表。而shutdown只是将线程池设置成SHUTDOWN状态，然后中断没有正在执行任务的线程。

### **ThreadLocal的设计理念与作用。**

ThreadLocal并不是一个Thread，而是Thread的局部变量, 当使用ThreadLocal维护变量时，ThreadLocal为每个使用该变量的线程提供独立的变量副本，所以每一个线程都可以独立地改变自己的副本，而不会影响其它线程所对应的副本



### **同步**

同步就是协同步调，按预定的先后次序进行运行。

### **sleep() 和 wait() 区别**

答：sleep()方法是**线程类（Thread）的静态方法**，导致此线程暂停执行指定时间，将执行机会给其他线程，但是监控状态依然保持，到时后会自动恢复（线程回到就绪（ready）状态），因为调用 sleep **不会释放对象锁**。

wait() 是 **Object 类的方法**，对此对象调用 wait()方法导致本线程放弃对象锁(线程暂停执行)，**释放资源并**进入等待此对象的等待锁定池，只有针对此对象发出 notify 方法（或 notifyAll）后本线程才进入对象锁定池准备获得对象锁进入就绪状态。

### **sleep() 和 yield() 区别**

· ① sleep() 方法给其他线程运行机会时**不考虑线程的优先级**，因此会给低优先级的线程以运行的机会；yield() 方法**只会给相同优先级或更高优先级**的线程以运行的机会；

· ② 线程执行 sleep() 方法后转入**阻塞**（blocked）状态，而执行 yield() 方法后转入**就绪（ready）**状态；

· ③ sleep() 方法声明抛出InterruptedException，而 yield() 方法没有声明任何异常；

· ④ sleep() 方法比 yield() 方法（跟操作系统相关）具有更好的可移植性。

### **线程同步相关的方法。**

**·** **wait()**:使一个线程处于等待（阻塞）状态，并且释放所持有的对象的锁；

**·** **sleep()**:使一个正在运行的线程处于睡眠状态，是一个静态方法，调用此方法要捕捉InterruptedException 异常；

**·** **notify()**:唤醒一个处于等待状态的线程，当然在调用此方法的时候，并不能确切的唤醒某一个等待状态的线程，而是由JVM确定唤醒哪个线程，而且与优先级无关；

**·** **notityAll()**:唤醒所有处入等待状态的线程，注意并不是给所有唤醒线程一个对象的锁，而是让它们竞争；

### **什么是线程池（thread pool）**

在面向对象编程中，**创建和销毁对象是很费时间的**，因为创建一个对象要获取内存资源或者其它更多资源。在 Java 中更是如此，虚拟机将试图跟踪每一个对象，以便能够在对象销毁后进行垃圾回收。所以提高服务程序效率的一个手段就是**尽可能减少创建和销毁对象的次数**，特别是一些很耗资源的对象创建和销毁，这就是"**池化资源**"技术产生的原因。

线程池顾名思义就是事先创建若干个可执行的线程放入一个池（容器）中，需要的时候从池中获取线程不用自行创建，使用完毕不需要销毁线程而是放回池中，从而减少创建和销毁线程对象的开销。



### **ConcurrentHashMap实现原理**

ConcurrentHashMap和Hashtable主要区别就是围绕着锁的粒度以及如何锁。 Hashtabl在竞争激烈的环境下表现效率低下的原因是一把锁锁住整张表，导致所有线程同时竞争一个锁。ConcurrentHashMap采用**分段锁**，每把锁锁住容器中的一个Segment。那么多线程访问容器里不同的Segment的数据时线程就不会存在竞争，从而有效提高并发访问效率。首先是将数据分层多个Segment存储，并为每个Segment分配一把锁，当一个线程范围其中一段数据时，其他线程可以访问其他段的数据。

数据结构：

ConcurrentHashMap内部是有**Segment**数组和**HashEntry**数组组成。一个ConcurrentHashMap里包含一个Segment数组，而Segment的结构和HashMap一样，里面是由一个数组和链表结构组成，所以一个Segment内部包含一个HashEntry数组。每个HashEntry是一个链表结构，对于HashEntry数组进行修改时首先需要获取与它对应的Segment锁。默认情况下有16个Segment

Segment的定位:

使用Wang/Jenkins hash变种算法对元素的hashCode进行一次再散列，目的是为了减少散列冲突。

ConcurrentHashMap的操作:

· get

get操作实现非常简单高效。先经过一次**再散列**，然后用这个散列值通过散列运算定位到Segment，**再通过散列算法定位到元素**。get之所以高效是因为整个get过程不需要加锁，除非读到空值才会加锁重读。实现该技术的技术保证是保证**HashEntry是不可变的**。

第一步是访问count变量，这是一个volatile变量，由于所有的修改操作在进行结构修改时都会在最后一步写count 变量，通过这种机制保证get操作能够得到几乎最新的结构更新。对于非结构更新，也就是结点值的改变，由于HashEntry的value变量是 volatile的，也能保证读取到最新的值。接下来就是根据hash和key对hash链进行遍历找到要获取的结点，如果没有找到，直接访回null。

对hash链进行遍历**不需要加锁的原因在于链指针next是final的、entry是不可变类**。但是头指针却不是final的，这是通过getFirst(hash)方法返回，也就是存在 table数组中的值。这使得getFirst(hash)可能返回过时的头结点，例如，当执行get方法时，刚执行完getFirst(hash)之后，另一个线程执行了删除操作并更新头结点，这就导致get方法中返回的头结点不是最新的。这是可以允许，通过对count变量的协调机制，get能读取到几乎最新的数据，虽然可能不是最新的。要得到最新的数据，只有采用完全的同步。

· put

该方法也是在持有段锁(锁定当前segment)的情况下执行的，这当然是为了并发的安全，修改数据是不能并发进行的，必须得有个判断是否超限的语句以确保容量不足时能够rehash。首先根据计算得到的散列值定位到segment及该segment中的散列桶中。接着判断是否存在同样一个key的结点，如果存在就直接替换这个结点的值。否则创建一个新的结点并添加到hash链的头部，这时一定要修改modCount和count的值，同样修改count的值一定要放在最后一步。

· remove HashEntry中除了value不是final的，其它值都是final的，这意味着不能从hash链的中间或尾部添加或删除节点，因为这需要修改next 引用值，所有的节点的修改只能从头部开始。对于put操作，可以一律添加到Hash链的头部。但是对于remove操作，可能需要从中间删除一个节点，这就需要将要删除节点的前面所有节点整个复制一遍，最后一个节点指向要删除结点的下一个结点。

首先定位到要删除的节点e。如果不存在这个节点就直接返回null，否则就要将e前面的结点复制一遍，尾结点指向e的下一个结点。e后面的结点不需要复制，它们可以重用。

· size() 每个Segment都有一个count变量，是一个volatile变量。当调用size方法时，首先先尝试2次通过不锁住segment的方式统计各个Segment的count值得总和，如果两次值不同则将锁住整个ConcurrentHashMap然后进行计算。

参见《java并发编程的艺术》P156 <http://www.cnblogs.com/ITtangtang/p/3948786.html>

### **线程的几种可用状态**

线程在运行周期里有6中不同的状态：

\1. New 新建

\2. RUNNABLE 运行状态,操作系统中运行与就绪两种状态统称运行中

\3. BLOCKED 阻塞状态

\4. WAITING 等待状态

\5. TIME_WAITING 超时等待

\6. TERMINATED 终止状态

### **同步方法和同步代码块的区别是什么**

\1. 

同步方法只能锁定当前对象或class对象， 而同步方法块可以使用其他对象、当前对象及当前对象的class作为锁。

\2. 

\3. 

从反编译后的结果看，对于同步块使用了**monitorenter**和**monitorexit**指令，而同步方法则是依靠方法上的修饰符**ACC_SYNCHRONIZED**来完成，但它们的本质都是对一个对象监视器进行获取，而这个获取过程是排他的。

### **显示锁ReentrantLock与内置锁synchronized的相同与区别**

相同：显示锁与内置锁在加锁和内存上提供的语义相同(互斥访问临界区)

不同：

**1.** **使用方式**：内置无需指定释放锁，简化锁操作。显示锁拥有锁获取和释放的可操作性。

**2.** **功能上**：显示锁提供了其他很多功能如定时锁等待、可中断锁等待、公平性、尝试非阻塞获取锁、以及实现非结构化的加锁。（一个线程获取不到锁而被阻塞在synchronized之外时，对该线程进行中断操作，此时该线程的中断表示为会被修改，但线程依旧会被阻塞在synchronized上，等待获取锁。）

**3.** **对死锁的处理**：内置只能重启，显示可以通过设置超时获取锁来避免

**4.** **性能上**：java1.5 显示远超内置，java1.6 显示锁稍微比内置好

\5. atomicinteger和Volatile等线程安全操作的关键字的理解和使用

SOF你遇到过哪些情况。

### **实现多线程的3种方法：Thread与Runable。**

**·** **1)继承Tread类，重写run函数**

**·** **2)实现Runnable接口**

**·** **3)实现Callable接口**

### **如何选择多线程池**

\1. 线程同步的方法：sychronized、lock、reentrantLock等。

\2. 锁的等级：方法锁、对象锁、类锁。

\3. ThreadPool用法与优势。

\4. Callable和Runnable的区别

\5. Concurrent包里的其他东西：ArrayBlockingQueue、CountDownLatch等等。

\6. foreach与正常for循环效率对比。

\7. 反射的作用于原理。

\8. 泛型常用特点，List能否转为List。 

\9. 设计模式：单例、工厂、适配器、责任链、观察者等等。

\10. JNI的使用。

\11. java的代理是怎么实现的

\12. Java1.7与1.8新特性。

\13. lmbda表达式

\14. Java8新特性

\15. 连接池使用使用什么数据结构实现

\16. 实现连接池

\17. 结束一条 Thread 有什么方法？ interrupt 底层实现有看过吗？线程的状态是怎么样的？如果给你实现会怎么样做？

\18. Java 中有内存泄露吗？是怎么样的情景？为什么不用循环计数？

\19. java都有哪些加锁方式

\20. AIO与BIO的区别

\21. 生产者与消费者，手写代码

\22. Java创建线程之后，直接调用start()方法和run()的区别

\23. 常用的线程池模式以及不同线程池的使用场景

\24. newFixedThreadPool此种线程池如果线程数达到最大值后会怎么办，底层原理。

\25. 多线程之间通信的同步问题，synchronized锁的是对象，衍伸出和synchronized相关很多的具体问题，例如同一个类不同方法都有synchronized锁，一个对象是否可以同时访问。或者一个类的static构造方法加上synchronized之后的锁的影响。

\26. 了解可重入锁的含义，以及ReentrantLock 和synchronized的区别

\27. 同步的数据结构，例如concurrentHashMap的源码理解以及内部实现原理，为什么他是同步的且效率高

\28. 线程间通信，wait和notify

\29. 定时线程的使用

\30. 场景：在一个主线程中，要求有大量(很多很多)子线程执行完之后，主线程才执行完成。多种方式，考虑效率。

\31. 并发、同步的接口或方法

\32. J.U.C下的常见类的使用。 ThreadPool的深入考察； BlockingQueue的使用。（take，poll的区别，put，offer的区别）；原子类的实现。

\33. 简单介绍下多线程的情况，从建立一个线程开始。然后怎么控制同步过程，多线程常用的方法和结构

\34. 实现多线程有几种方式，多线程同步怎么做，说说几个线程里常用的方法

### **写出生产者消费者模式。**

`public class ProducerConsumerPattern {`

​    `public static void main(String args[]){`

​     `BlockingQueue sharedQueue = new LinkedBlockingQueue();`

​     `Thread prodThread = new Thread(new Producer(sharedQueue));`

​     `Thread consThread = new Thread(new Consumer(sharedQueue));`

​     `prodThread.start();`

​     `consThread.start();`

​    `}`

`}`

`` 

`//Producer Class in java`

`class Producer implements Runnable {`

​    `private final BlockingQueue sharedQueue;`

​    `public Producer(BlockingQueue sharedQueue) {`

​        `this.sharedQueue = sharedQueue;`

​    `}`

​    `@Override`

​    `public void run() {`

​        `for(int i=0; i<10; i++){`

​            `try {`

​                `System.out.println("Produced: " + i);`

​                `sharedQueue.put(i);`

​            `} catch (InterruptedException ex) {`

​                `Logger.getLogger(Producer.class.getName()).log(Level.SEVERE, null, ex);`

​            `}`

​        `}`

​    `}`

`}`

`` 

`//Consumer Class in Java`

`class Consumer implements Runnable{`

​    `private final BlockingQueue sharedQueue;`

​    `public Consumer (BlockingQueue sharedQueue) {`

​        `this.sharedQueue = sharedQueue;`

​    `}`

​    `@Override`

​    `public void run() {`

​        `while(true){`

​            `try {`

​                `System.out.println("Consumed: "+ sharedQueue.take());`

​            `} catch (InterruptedException ex) {`

​                `Logger.getLogger(Consumer.class.getName()).log(Level.SEVERE, null, ex);`

​            `}`

​        `}`

​    `}`

`}`



## **Java IO 分类**

· 

**Java BIO**： 同步并阻塞，服务器实现模式为一个连接一个线程，即客户端有连接请求时服务器端就需要启动一个线程进行处理，如果这个连接不做任何事情会造成不必要的线程开销，当然可以通过线程池机制改善。

**Java NIO** ： 同步非阻塞，服务器实现模式为一个请求一个线程，即当一个连接创建后，不需要对应一个线程，这个连接会被注册到**多路复用器**上面，所以所有的连接只需要一个线程就可以搞定，当这个线程中的多路复用器进行轮询的时候，发现连接上有请求的话，才开启一个线程进行处理，也就是一个请求一个线程模式。BIO与NIO一个比较重要的不同，是我们使用BIO的时候往往会引入多线程，每个连接一个单独的线程；而NIO则是使用单线程或者只使用少量的多线程，每个连接共用一个线程。

**Java AIO(NIO.2)** ： 异步非阻塞，服务器实现模式为一个有效请求一个线程，客户端的I/O请求都是由OS先完成了再通知服务器应用去启动线程进行处理。

### **名词解释**

**·** **同步**:指的是用户进程触发IO操作需要等待或者轮询的去查看IO操作执行完成才能执行其他操作.这种方式性能比较差，只有一些对数据安全性要求比较高的场景中才会使用．

**·** **异步**:异步是指用户进程触发IO操作以后便开始做自己的事情，而当IO操作已经完成的时候会得到IO完成的通知（异步的特点就是通知）

**·** **阻塞**：所谓阻塞方式的意思是指, 当试图对该文件描述符进行读写时, 如果当时没有东西可读,或者暂时不可写, 程序就进入等待 状态, 直到有东西可读或者可写为止

**·** **非阻塞**：非阻塞状态下, 如果没有东西可读, 或者不可写, 读写函数马上返回, 而不会等待

### **Java BIO**

在JDK 1.4推出Java NIO之前，基于Java的所有Socket通信都采用了同步阻塞模式（BIO），**这种一请求一应答的通信模型简化了上层的应用开发，但是在性能和可靠性方面却存在着巨大的瓶颈**。当并发访问量增大、响应时间延迟增大之后，采用Java BIO开发的服务端软件只有通过硬件的不断扩容来满足高并发和低时延，它极大地增加了企业的成本，并且随着集群规模的不断膨胀，系统的可维护性也面临巨大的挑战，只能通过采购性能更高的硬件服务器来解决问题，这会导致恶性循环,传统采用BIO的Java Web服务器如下所示（典型的如Tomcat的BIO模式）：

![img](file:///C:\Users\NIGHT_~1\AppData\Local\Temp\ksohtml7664\wps3.jpg) 

采用该线程模型的服务器调度特点如下：

\1. 服务端监听线程Acceptor负责客户端连接的接入，每当有新的客户端接入，就会创建一个新的I/O线程负责处理Socket

\2. 客户端请求消息的读取和应答的发送，都有I/O线程负责

\3. 除了I/O读写操作，默认情况下业务的逻辑处理，例如DB操作等，也都在I/O线程处理

\4. I/O操作采用同步阻塞操作，读写没有完成，I/O线程会同步阻塞

BIO线程模型主要存在如下三个问题：

**1.** **性能问题**：一连接一线程模型导致服务端的并发接入数和系统吞吐量受到极大限制

**2.** **可靠性问题**：由于I/O操作采用同步阻塞模式，当网络拥塞或者通信对端处理缓慢会导致I/O线程被挂住，阻塞时间无法预测

**3.** **可维护性问题**：I/O线程数无法有效控制、资源无法有效共享（多线程并发问题），系统可维护性差

### **BIO、NIO、AIO适用场景分析**

· BIO方式适用于**连接数目比较小且固定的架构**，这种方式对服务器**资源要求比较高**，并发局限于应用中，JDK1.4以前的唯一选择，但程序直观简单易理解。

· NIO方式适用于连接数目多且连接比较短（轻操作）的架构，比如聊天服务器，并发局限于应用中，编程比较复杂，JDK1.4开始支持。

· AIO方式使用于连接数目多且连接比较长（重操作）的架构，比如相册服务器，充分调用OS参与并发操作，编程比较复杂，JDK7开始支持。

### **Java NIO和IO的主要区别**

\1. 面向流与面向缓冲.

Java NIO和IO之间第一个最大的区别是，IO是面向流的，NIO是面向缓冲区的。Java IO面向流意味着每次从流中读一个或多个字节，直至读取所有字节，它们没有被缓存在任何地方。此外，它不能前后移动流中的数据。如果需要前后移动从流中读取的数据，需要先将它缓存到一个缓冲区。 Java NIO的缓冲导向方法略有不同。数据读取到一个它稍后处理的缓冲区，需要时可在缓冲区中前后移动。这就增加了处理过程中的灵活性。

\1. 阻塞与非阻塞IO

Java IO的各种流是阻塞的。这意味着，当一个线程调用read() 或 write()时，该线程被阻塞，直到有一些数据被读取，或数据完全写入。该线程在此期间不能再干任何事情了。 Java NIO的非阻塞模式，使一个线程从某通道发送请求读取数据，但是它仅能得到目前可用的数据，如果目前没有数据可用时，该线程可以继续做其他的事情。 非阻塞写也是如此。一个线程请求写入一些数据到某通道，但不需要等待它完全写入，这个线程同时可以去做别的事情。线程通常将非阻塞IO的空闲时间用于在其它通道上执行IO操作，所以一个单独的线程现在可以管理多个输入和输出通道（channel）。

\1. 选择器（Selectors）

Java NIO的选择器允许一个单独的线程来监视多个输入通道，你可以注册多个通道使用一个选择器，然后使用一个单独的线程来“选择”通道：这些通道里已经有可以处理的输入，或者选择已准备写入的通道。这种选择机制，使得一个单独的线程很容易来管理多个通道。



## **JVM虚拟机**

虚拟机面试一般包含以下几个知识点：

· JVM内存划分

· JVM垃圾回收，垃圾回收可从几个点出发： 

o 什么对象需要回收

o 什么时候回收

o 怎么回收 

§ 垃圾回收算法

§ 垃圾收集器

· 如何使用工具观察和解决虚拟机问题

· 参数调优

· 类加载机制 

o 加载过程

o 双亲委派原理

· 执行引擎 

o 动态委派和静态委派。这里涉及到java多态的概念。

### **介绍JVM中7个区域，然后把每个区域可能造成内存的溢出的情况说明**

· 

**程序计数器**：看做当前线程所执行的**字节码行号指示器**。是线程**私有**的内存，且唯一一块不报OutOfMemoryError异常的内存区域。

· 

· 

**Java虚拟机栈**：用于描述java方法的**内存模型**：每个方法被执行时都会同时创建一个**栈帧**用于存储**局部变量表、操作数栈、动态链接、方法出口**等信息。每一个方法被调用直至执行完成的过程就对应着一个栈帧在虚拟机中从入栈到出栈的过程。如果线程请求的**栈深度**大于虚拟机所允许的深度就报StackOverflowError, 如果虚拟机栈可以动态**扩展**，当拓展时无法申请到足够的内存会抛出OutOfMemoryError. 是线程**私有**的。

· 

· 

**本地方法栈**：与虚拟机栈相似，不同的在于它是为虚拟机使用到**Native**方法服务的。会抛出StackOverflowError和OutOfMemoryError。是线程**私有**的。

· 

· 

**Java堆**: 是所有线程共享的一块内存，在虚拟机启动时创建。此内存区域的唯一目的就是存放对象实例，几乎所有的对象实例都在这里分配内存。如果堆上没有内存完成实例的分配就会报OutOfMemoryError.

· 

· 

**方法区（永久代）**：用于存储已被虚拟机加载的**类信息、常量、静态变量、即时编译器编译后的代码**等数据。当方法区无法满足内存分配需求时，会抛出OutOfMemoryError。是共享内存。

· 

· 

**运行时常量池**：用于存放编译器生成的各种字面量和符号引用，是方法区的一部分。无法申请内存时抛出OutOfMemoryError。

· 

· 

**直接内存**：不是虚拟机运行时数据的一部分，也不是java虚拟机规范中定义的区域，是计算机直接的内存空间。这部分也被频繁使用，如JAVA NIO的引入基于通道和缓存区的I/O使用native函数直接分配堆外内存。如果内存不足会报OutOfMemoryError。

### **GC的两种判定方法：引用计数与根搜索算法**

· 

**引用计数**： 给对象添加一个引用计数器，每当有一个地方引用该对象时，计数器值加1，当引用失效时，计数器值减1,。任何时候计数器都为0的对象就是不可能再被使用的。它很难解决对象之间相互**循环引用**问题。

· 

· 

**根搜索算法（GC Roots Traceing）:** 通过一系列名为“GC Roots”的对象作为起点，从这些节点开始向下搜索，搜索走过的路径成为**引用链**，当一个对象到GC Roots没有任何引用链相连时，则证明此对象不可用。

· 

GC Roots对象一般是：虚拟机栈中的引用对象，方法区中类静态属性引用的对象，方法区常量引用的对象等。

### **Java中的四种引用**

Java中提供这四种引用类型主要有两个目的：第一是可以让程序员通过代码的方式决定某些对象的生命周期；第二是有利于JVM进行垃圾回收。

· 

**强引用**：程序代码中的普通引用。如Object obj = new Object(),只要强引用存在，垃圾回收器就不会回收。在不使用对象时应及时将引用设置为null，便于垃圾回收。

· 

· 

**软引用**：描述一些有用但并非必须的对象。对于软引用关联的对象在系统将要**发生内存溢出异常之前**，将会把这些对象列进回收范围之中进行第二次回收。**SoftRefence**

· 

· 

**弱引用**：描述非必须对象，比软引用弱一些。被弱引用关联的对象只能**生存到下一次垃圾收集发生之前**。无论当前内存是否足够，都会回收掉只被弱引用关联的对象。**WeakRefence**

· 

· 

**虚引用**：最弱的引用，不管是否有虚引用存在，完全不会对对象生存时间构成影响，也无法通过虚引用来取得一个对象实例。唯一目的是希望能够在这个对象被垃圾回收器之前收到系统通知。**PhantomReference**

· 

相关参考：[Java 如何有效地避免OOM：善于利用软引用和弱引用](https://www.cnblogs.com/dolphin0520/p/3784171.html)

### **对象创建方法，对象的内存分配，对象的访问定位。**

Object obj = new Object();

obj 保存在java栈中的局部变量表里，作为一个引用数据出现。 New Object()会在java堆上分配一块存储Object类型实例的所有数值的结构化内存，根据类型以及虚拟机实现的对象内存布局不同。这块内存是不固定的。

对象访问方式有两种：**句柄和直接指针**。

· 

**句柄**：在java堆中会划分出一块内存作为句柄池，reference中存储的对象是句柄地址。**而句柄中包含对象实例数据和类型数据各自的具体地址信息**。最大的好处是如果对象地址发生变化不需要改变reference的值，只需要改变句柄中实例数据指针。

· 

· 

**直接指针访问**：reference直接存储对象的地址，最大的好处是**速度更快**。

### **内存溢出和内存泄漏**

· 

**内存溢出**：通俗理解就是**内存不够**，程序所需要的内存远远超出了你虚拟机分配的内存大小，就叫内存溢出

· 

· 

**内存泄露**：内存泄漏也称作“存储渗漏”，用动态存储分配函数动态开辟的空间，在**使用完毕后未释放**，结果导致**一直占据该内存单元**。直到程序结束。（其实说白了就是该内存空间使用完毕之后未回收）即所谓内存泄漏

### **内存溢出了怎么办**

通过内存映像工具如jhat、jconsole等对dump出来的堆转存储快照进行分析，重点是确认内存是出现内存泄露还是内存溢出。

如果是**内存泄露**进一步使用工具查看泄露的对象到GC Roots的引用链。于是就能找到泄露对象是通过怎样的路径与GC Roots相关联并导致垃圾收集器无法自动回收它们。掌握泄露对象的信息，以及GC Roots引用链的信息，就可以比较准确定位泄露代码的位置。

如果不存在**内存泄露**，那就需要通过jinfo、Jconsole等工具分析java堆参数与机器物理内存对比是否还可以调大，从代码上检查是否存在某些对象生命周期过长，持有状态过长的情况，尝试减少程序的运行消耗。

### **Java 中有内存泄露吗？**

有，Java中，造成内存泄露的原因有很多种。典型的例子是**长生命周期的对象持有短生命周期对象的引用就很可能发生内存泄露**，尽管短生命周期对象已经不再需要，但是因为长生命周期对象持有它的引用而导致不能被回收，这就是java中内存泄露的发生场景，通俗地说，就是程序员可能创建了一个对象，以后一直不再使用这个对象，这个对象却一直被引用，即这个对象无用但是却无法被垃圾回收器回收的，这就是java中可能出现内存泄露的情况，例如，缓存系统，我们加载了一个对象放在缓存中(例如放在一个全局map对象中)，然后一直不再使用它，这个对象一直被缓存引用，但却不再被使用。

检查java中的内存泄露，一定要让程序将各种分支情况都完整执行到程序结束，然后看某个对象是否被使用过，如果没有，则才能判定这个对象属于内存泄露。（采用什么工具？）

**如果一个外部类的实例对象的方法返回了一个内部类的实例对象**，这个内部类对象被长期引用了，即使那个外部类实例对象不再被使用，但由于内部类持久外部类的实例对象，这个外部类对象将不会被垃圾回收，这也会造成内存泄露。



### **什么时候会发生jvm堆（持久区）内存溢出**

简单的来说 java的堆内存分为两块:permantspace（持久代） 和 heap space。

持久带中主要存放用于存放静态类型数据，如 Java Class, Method 等， 与垃圾收集器要收集的Java对象关系不大。

而heapspace分为年轻代和年老代:

· 年轻代的垃圾回收叫 Young GC， 年老代的垃圾回收叫 Full GC。

· 在年轻代中经历了N次（可配置）垃圾回收后仍然存活的对象，就会被复制到年老代中。因此，可以认为年老代中存放的都是一些生命周期较长的对象

· 年老代溢出原因有 循环上万次的字符串处理、创建上千万个对象、在一段代码内申请上百M甚至上G的内存

**持久代溢出原因动态加载了大量Java类而导致溢出，以及生产大量的常量**。

**永久代内存泄露**: 以一个部署到应用程序服务器的Java web程序来说，当该应用程序被卸载的时候，你的EAR/WAR包中的所有类都将变得无用。只要应用程序服务器还活着，JVM将继续运行，但是一大堆的类定义将不再使用，理应将它们从永久代（PermGen）中移除。如果不移除的话，我们在永久代（PermGen）区域就会有内存泄漏。

### **堆里面的分区：Eden，survivor from to，老年代，各自的特点。**

新生代：朝生夕死

老年代一般是放对象和长期存活对象。当一个对象分配的内存空间大于某个阈值时或则年龄增加到一定程度（默认15岁）就进入老年代。

### **OOM你遇到过哪些情况**

· 

java.lang.OutOfMemoryError: Java heap space ------>java堆内存溢出，此种情况最常见，一般由于内存泄露或者堆的大小设置不当引起。

· 

· 

java.lang.OutOfMemoryError: PermGen space ------>java永久代溢出，即方法区溢出了，**一般出现于大量Class或者jsp页面**，或者采用cglib等反射机制的情况，因为上述情况会产生大量的Class信息存储于方法区。

· 

· 

java.lang.StackOverflowError ------> 不会抛OOM error，但也是比较常见的Java内存溢出。JAVA虚拟机栈溢出，一般是由于程序中存在**死循环或者深度递归调用**造成的，栈大小设置太小也会出现此种溢出。可以通过虚拟机参数**-Xss**来设置栈的大小。

### **GC的收集方法的原理与特点，分别用在什么地方，如果让你优化收集方法，有什么思路？**

· 

**标记清理**：首先标记所有需要回收的对象，在标记完成后**统一回收掉**所有被标记的对象，它的标记的对象。缺点是**效率低**，且存在**内存碎片**。主要用于老生代垃圾回收。

· 

· 

**标记整理**：首先标记所有需要回收的对象，在标记完成后让所有存活的对象都向一端移动，然后直接清理掉端边界意外的内存。用于老年代。

· 

· 

**复制算法**：将内存按容量划分为大小相等的一块，每次只用其中一块。当内存用完了，将还存活的对象复制到另一块内存，然后把已使用过的内存空间一次清理掉。实现简单，高效。一般用于新生代。一般是将内存分为一块较大的**Eden空间**和两块较小的**Survivor**空间。HotSpot虚拟机默认比例是**8:1**,。每次使用Eden和一块Survivor，当回收时将这两块内存中还存活的对象复制到Survivor然后清理掉刚才Eden和Survivor的空间。如果复制过程内存不够使用则向老年代分配担保。

· 

· 

**分代收集算法**：根据对象的生存周期将内存划分为新生代和老年代，根据年代的特点采用最适当的收集算法。

### **GC收集器有哪些？CMS收集器与G1收集器的特点。**

· 

**Serial**: 单线程收集器，只会使用一个CPU或一条收集器线程去完成，垃圾回收工作，更重要的是在进行垃圾回收时，必须暂停其他所有的工作线程。（Stop the world）。简单高效，用于新生代。

· 

· 

**ParNew**: 是Serial收集器的**多线程版本**，垃圾回收时采用多线程方式进行回收。默认情况下使用的线程数是cpu数量。除了serial收集器，目前只有它能和CMS收集器配合工作。是server模式下首选的新生代收集器。

· 

· 

**Parallel Scavenge**: 使用**复制算法**收集器，也是一个并行的多线程收集器。Parallel Scavenge收集器与其他收集器关注点不同，其它收集器主要关注缩短垃圾回收时用户线程的停顿时间。而它关心**吞吐量**，即**运行用户代码时间/(运行用户代码时间 + 垃圾收集时间)**。停顿时间越短越适合需要与用户交互的程序，高吞吐量则可以最高效率的利用CPU时间。

· 

· 

**Serial Old**: 老年代，单线程收集器，使用**标记整理算法**。主要有两个用途，一是和Parallel Scavenge 收集器配合使用，二是作为CMS的后备方案在并发收集器发生**Concurrent Mode Failure**时候使用。

· 

· 

**Parallel Old**:并行的老年代版本收集器，使用标记整理算法。主要与Parallel Scavenge配合使用。

· 

· 

**CMS**：是以获得**最短回收停顿时间为**目标的收集器，使用**标记清除算法**。整个过程包括4个：

· 

**o** **初始标记**: 标记Gc ROOTS能直接关联到的对象

**o** **并发标记**：进行Roots Traceing的过程

**o** **重新标记**：修正并发标记期间因用户继续工作导致标记产生变动

**o** **并发清除**：并发清除数据。 初始标记和重新标记需要stop the world. 并发标记和并发清除过程用户线程和收集器线程可以并行执行。

· 

**G1(Garbage First):** 基于**标记-整理算法**的收集器,不会产生空间碎片.它可以精确控制停顿,能够让使用者明确指定一个长度为M毫秒的时间片段内,消耗集上的时间不超过N秒.是不牺牲吞吐量的前提下完成低停顿的.**G1将整个java堆(新生和老生)划分为大小相同的区,并跟踪这些区上发生的变化.在后台维护一个优先列表,每次根据允许的收集时间优先回收垃圾最多的区域**.

· 

现在公司中很多都采用了G1 垃圾回收期，建议大家多深入了解下G1，更多参考: [G1垃圾回收器](https://github.com/zhengjianglong915/note-of-interview/blob/master/java/G1垃圾回收器.md)

### **Minor GC与Full GC分别在什么时候发生？**

FullGC 一般是发生在老年代的GC，出现一个FullGC经常会伴随至少一次的Minor GC。速度比MinorGC慢10倍以上。

#### **FUll GC**

FULL GC发生的情况:

**·** **1) 老年代空间不足** 老年代空间只有在新生代对象转入及创建为大对象、大数组时才会出现不足的现象，当执行Full GC后空间仍然不足，则抛出如下错误：java.lang.OutOfMemoryError: Java heap space.

措施:为避免以上两种状况引起的FullGC，调优时应尽量做到让对象在Minor GC阶段被回收、让对象在新生代多存活一段时间及不要创建过大的对象及数组

**·** **2) Permanet Generation(方法区或永久代)空间满** PermanetGeneration中存放的为一些class的信息等，当系统中要加载的类、反射的类和调用的方法较多时，Permanet Generation可能会被占满，在未配置为采用CMS GC的情况下会执行Full GC。如果经过Full GC仍然回收不了，那么JVM会抛出如下错误信息：java.lang.OutOfMemoryError: PermGen space

措施:为避免Perm Gen占满造成Full GC现象，可采用的方法为增大Perm Gen空间或转为使用CMS GC。

· 

**3) CMS GC时出现promotion failed和concurrent mode failure** 对于采用CMS进行老年代GC的程序而言，尤其要注意GC日志中是否有promotion failed和concurrent mode failure两种状况，当这两种状况出现时可能会触发Full GC。promotion failed是在进行Minor GC时，survivor space放不下、对象只能放入老年代，而此时老年代也放不下造成的；

· 

concurrent mode failure: CMS在执行垃圾回收时需要一部分的内存空间并且此刻用户程序也在运行需要预留一部分内存给用户程序，如果预留的内存无法满足程序需求就出现一次"Concurrent mod failure",并触发一次Full GC。

· 

应对措施为：增大survivor space、老年代空间或调低触发并发GC的比率，

· 

· 

**4) 空间分配担保** 统计得到的Minor GC晋升到老年代的平均大小大于老年代的剩余空间，Hotspot为了避免由于新生代对象晋升到老年代导致旧生代空间不足的现象，在进行Minor GC时，做了一个判断。如果之前统计所得到的Minor GC晋升到老年代的平均大小大于老年代的剩余空间，那么就直接触发Full GC。如果小于并且不允许担保失败也会发生一次Full GC。

#### **MinorGC**

MinorGC 指发生在新生代的垃圾收集动作，非常频繁，回收速度也快。一般发生在新生代空间不足时,另外一个FullGC经常会伴随至少一次的Minor GC. 当虚拟检测晋升到到老年代的平均大小是否小于老年代剩余空间大小,如果小于并且允许担保失败,则执行Minor GC.

### **几种常用的内存调试工具：jmap、jstack、jconsole。**

(如何用工具分析jvm状态)

**·** **jps**: 列出正在虚拟机运行的虚拟机进程，并显示虚拟机执行主类的名称，以及这些进程的本地虚拟机的唯一ID。

**·** **jstat** : 监视虚拟机各种运行状态信息的命令。可以显示本地或远程虚拟机进程中**类装载、垃圾收集、JIT编译、内存**等数据。

**·** **jinfo**: 实时查看和调整虚拟机的各项参数。

**·** **jmap**: 生成**堆转存储快照**，查询fianlize执行队列、java堆和永生代详细信息，如空间使用率，当前用的是那种收集器。

**·** **Jhat**: 和jmap搭配使用，来分析jmap生成的堆转存储快照。内置一个微型的HTTP/HTML服务器，生成dump文件的分析结果后，可以通过浏览器查看。

**·** **jstack**:用于生成当前时刻**线程快照**.线程快照是当前虚拟机内每一条线程正在执行的方法堆栈的集合.生成线程快照的主要目的是为了定位线程长时间停顿的原因.如死锁、死循环、请求外部资源导致的长时间等待.

**·** **JConsole**: 可视化监视和管理工具,几乎包括以上工具的所有功能

**·** **VisualVM**

### **GC 是什么？为什么要有 GC**

GC 是垃圾收集的意思，内存处理是编程人员容易出现问题的地方，忘记或者错误的内存回收会导致程序或系统的不稳定甚至崩溃，Java 提供的 GC 功能可以自动监测对象是否超过作用域从而达到自动回收内存的目的，Java 语言没有提供释放已分配内存的显示操作方法。Java 程序员不用担心内存管理，因为垃圾收集器会自动进行管理。要请求垃圾收集，可以调用下面的方法之一：System.gc() 或Runtime.getRuntime().gc() ，但 JVM 可以屏蔽掉显示的垃圾回收调用。

垃圾回收可以有效的防止内存泄露，有效的使用可以使用的内存。垃圾回收器通常是作为一个单独的低优先级的线程运行，不可预知的情况下对内存堆中已经死亡的或者长时间没有使用的对象进行清除和回收，程序员不能实时的调用垃圾回收器对某个对象或所有对象进行垃圾回收。在 Java 诞生初期，垃圾回收是 Java 最大的亮点之一，因为服务器端的编程需要有效的防止内存泄露问题，然而时过境迁，如今 Java 的垃圾回收机制已经成为被诟病的东西。移动智能终端用户通常觉得 iOS 的系统比 Android 系统有更好的用户体验，其中一个深层次的原因就在于 Android 系统中垃圾回收的不可预知性。

### **JVM 加载 class 文件的原理机制**

JVM 中类的装载是由类加载器（ClassLoader） 和它的子类来实现的，Java 中的类加载器是一个重要的 Java 运行时系统组件，它负责在运行时查找和装入类文件中的类。

由于 Java 的跨平台性，经过编译的 Java 源程序并不是一个可执行程序，而是一个或多个类文件。当 Java 程序需要使用某个类时，JVM 会确保这个类已经被加载、连接(验证、准备和解析)和初始化。类的加载是指把类的 .class 文件中的数据读入到内存中，通常是创建一个字节数组读入 .class 文件，然后产生与所加载类对应的 Class 对象。加载完成后，Class 对象还不完整，所以此时的类还不可用。当类被加载后就进入连接阶段，这一阶段包括验证、准备(为静态变量分配内存并设置默认的初始值)和解析(将符号引用替换为直接引用)三个步骤。最后 JVM 对类进行初始化，包括：

\1. 如果类存在直接的父类并且这个类还没有被初始化，那么就先初始化父类；

\2. 如果类中存在初始化语句，就依次执行这些初始化语句。

类的加载是由类加载器完成的，类加载器包括：**启动类加载器（BootStrap）、扩展加载器（Extension）、应用程序加载器（Application）和用户自定义类加载器（java.lang.ClassLoader的子类）**。从JDK 1.2开始，类加载过程采取了父亲委托机制(PDM)。PDM 更好的保证了 Java 平台的安全性，在该机制中，JVM 自带的 Bootstrap 是根加载器，其他的加载器都有且仅有一个父类加载器。类的加载首先请求父类加载器加载，父类加载器无能为力时才由其子类加载器自行加载。JVM 不会向 Java 程序提供对 Bootstrap 的引用。下面是关于几个类加载器的说明：

**·** **Bootstrap**：启动类加载器，一般用本地代码实现，负责加载JVM基础核心类库。加载存放在<JAVA_HOME>/lib目录中的类库（如rt.jar）；

**·** **Extension ClassLoader**：扩展加载器， 负责加载<JAVA_HOME>/lib/ext目录中的 ，或被java.ext.dirs 系统属性所指定的目录中加载类库，它的父加载器是 Bootstrap；

**·** **Application ClassLoader**：应用程序加载器，其父类是Extension。它是应用最广泛的类加载器。它从环境变量 classpath 或者系统属性 java.class.path 所指定的目录中记载类，是用户自定义加载器的默认父加载器。

缺点:

· 双亲委派模型很好地解决了各个类加载器的基础类统一问题(越基础的类由越上层的加载器进行加载)，基础类之所以被称为“基础”，是因为它们总是作为被调用代码调用的API。但是，如果基础类又要调用用户的代码时，双亲委派模型无法满足要求。 因为Bootstrap加载器无法找到永不代码类。

为了解决这个困境，Java设计团队只好引入了一个不太优雅的设计：**线程上下文件类加载器(Thread Context ClassLoader)**。这个类加载器可以通过java.lang.Thread类的setContextClassLoader()方法进行设置，如果创建线程时还未设置，它将会从父线程中继承一个；如果在应用程序的全局范围内都没有设置过，那么这个类加载器默认就是应用程序类加载器。了有线程上下文类加载器，JNDI服务使用这个线程上下文类加载器去加载所需要的SPI代码，也就是父类加载器请求子类加载器去完成类加载动作，这种行为实际上就是打通了双亲委派模型的层次结构来逆向使用类加载器，已经违背了双亲委派模型，但这也是无可奈何的事情。**Java中所有涉及SPI的加载动作基本上都采用这种方式**，例如JNDI,JDBC,JCE,JAXB和JBI等。 Dubbo的SPI也是采用这种机制实现。

### **类加载的五个过程：加载、验证、准备、解析、初始化。**

· 

**加载**: 根据全限定名来获取定义类的二进制字节流,然后将该字节流所代表的静态结构转化为方法区的运行时数据结构,最后在生成一个代表该类的Class对象,作为方法区这些数据的访问入口.

· 

· 

**验证**:主要时为了确保class文件的字节流中包含的信息符合当前虚拟机的要求,并且不会危害虚拟机自身的安全.包含四个阶段的验证过程:

· 

**o** **文件格式验证**:保证输入的字节流能够正确地解析并存储在方法区之内,格式上符合描述一个java类型信息的要求

**o** **元数据验证**:字节码语义信息的验证,以保证描述的信息符合java语言规范.验证点有:这个类是否有父类等.

**o** **字节码验证**:主要是进行数据流和控制流分析,保证被校验类的方法在运行时不会做出危害虚拟机安全的行为.

**o** **符号引用验证**:对符号引用转化为直接引用过程的验证.

· 

**准备**:为类变量分配内存并设置变量的初始值,这些内存在方法区进行分配.

· 

· 

**解析**:将虚拟机常量池中的符号引用转化为直接引用的过程.解析主要是针对类或接口、字段、类方法、类接口方法四类.

· 

· 

**初始化**:执行静态变量的赋值操作以及静态代码块,完成初识化.初始化过程保证了父类中定义的初始化优先于子类的初始化.但接口不需要执行父类的初始化.

### **双亲委派模型**

除了顶层的启动类加载器外,其余的类加载器都应当有自己的父类加载器.顺序依次是:

· Bootstrap ClassLoader: 启动类加载器,加载java_home/lib中的类

· Extension ClassLoader: 扩展类加载器,加载java_home/lib/ext目录下的类库

· Application ClassLoader: 应用程序类加载器,加载用户类路径上指定类库.

双亲委派模型的工作原理是:如果一个类加载器受到了类加载请求,它首先不会自己去尝试加载这个类,而把这个请求委派给父类加载器去完成,每一层次的类加载器都是如此,因此所有的加载请求最终都应该传送到顶层的启动类加载器中,只有当父类加载器反馈自己无法完成加载请求时,加载器才尝试自己加载.这种方式保证了Oject类(JDK 核心类)在各个加载器加载环境中都是同一个类.

### **分派：静态分派与动态分派。**

多态性特征的一些最基本的体现. **静态类型是编译期可知的,动态类型是在运行时可知**.Human h =new Man(); Human是静态类型,Man时动态类型.

所有依赖于静态类型定位方法执行版本的分派动作称作**静态分派**,最典型的应用是方法重载.静态分派发生在编译阶段。

**动态分派**是根据动态类型来确定执行的版本,所以只有到运行时才能确定具体的执行方法版本.典型的代表时重写.其过程如下:

· 

\1. 首先找到操作数栈栈顶的第一个元素所执向对象的实际类型,记做C.

· 

\1. 如果在类型C中找到和常量中的描述符和简单名称都相符的方法,则进行范围权限校验.如果通过则返回该方法的直接引用,否则抛出IllegalAccessError异常.

· 

\1. 否则按照继承关系从下往上一次对C的各个父类进行第2步的搜索和验证过程.

· 

\1. 如果始终没有找到就抛出AbstractMethodError异常. 方法的接受者和方法的参数统称方法宗量,根据分配基于多少中宗量可以分为单分派和多分派.java是静态多分派,动态分派属于单分派.

**动态分派的实现:** 动态分派时非常频繁的动作,而且动态分派的方法版本选择过程需要运行时在类的方法元数据中搜索合适的目标方法,因此出于性能的考虑,在方法区中建立一个**虚方法表**,用来保存各个方法的实际入口地址.如果某个方法的子类中没有被重写,那么子类的虚方法表里面的地址入口和父类相同方法的地址入口是一致的.都是指向父类的实现入口,如果子类中重写了这个方法,子类方法表中的地址将会被替换为指向子类实现版本的入口地址.虚方法表在类加载的连接阶段进行初始化.

### **Jvm 自动内存管理（什么时候触发 gc ）**

FULL GC 和 Minor GC 的触发时间 程序员不能具体控制时间，系统在不可预测的时间调用System.gc()函数的时候；当然可以通过调优，用NewRatio控制newObject和oldObject的比例，用MaxTenuringThreshold 控制进入oldObject的次数，使得oldObject 存储空间延迟达到full gc,从而使得计时器引发gc时间延迟OOM的时间延迟，以延长对象生存期。

### **GC停顿原因，如何降低停顿**

### **JVM如何调优、参数怎么调**

### **jvm的体系结构及各个部分的职责**

JVM都有两种机制，一个是装载具有合适名称的类(类或是接口)，包含类的装载 连接 初始化的过程叫做**类装载子系统**；另外的一个负责执行包含在已装载的类或接口中的指令，叫做**运行引擎**。每个JVM又包括方法区、堆、Java栈、程序计数器和本地方法栈这五个部分，这几个部分和类装载机制与运行引擎机制一起组成的体系结构图为:

![img](file:///C:\Users\NIGHT_~1\AppData\Local\Temp\ksohtml7664\wps4.jpg) 

· JVM的每个实例都有一个它自己的方法域和一个堆，运行于JVM内的所有的线程都共享这些区域；

· 当虚拟机装载类文件的时候，它解析其中的二进制数据所包含的类信息，并把它们放到方法域中；

· 当程序运行的时候，JVM把程序初始化的所有对象置于堆上；

· 而每个线程创建的时候，都会拥有自己的程序计数器和Java栈，其中程序计数器中的值指向下一条即将被执行的指令，线程的Java栈则存储为该线程调用Java方法的状态；

· 本地方法调用的状态被存储在本地方法栈，该方法栈依赖于具体的实现。



### **如果想不被 GC 怎么办**

可以先说那些对象可以被GC,然后说java对象会不会回收，决定于是否还被引用，不被引用了就有可能被GC回收，一直被引用着就不会被回收.

\1. jvm性能调优都做了什么

\2. 介绍GC 和GC Root不正常引用。

\3. 自己从classload 加载方式，加载机制说开去，从程序运行时数据区，讲到内存分配，讲到String常量池，讲到JVM垃圾回收机制，算法，hotspot。反正就是各种扩展

\4. 数组多大放在 JVM 老年代（不只是设置 PretenureSizeThreshold ，问通常多大，没做过一问便知）

\5. 老年代中数组的访问方式

\6. GC 算法，永久代对象如何 GC ， GC 有环怎么处理

\7. jvm 如何分配直接内存??

\8. new 对象如何不分配在堆而是栈上?

\9. 常量池解析

### **运行期优化**

### **最佳实践**

### **Student s= new Student(),在内存中做了那些事情**

\1. 加载Student.class 文件进内存

\2. 在栈内存为s开辟空间

\3. 在堆内存为Student对象开辟空间

\4. 学生对象的成员变量进行显示初始化

\5. 通过构造方法对学生对象变量赋值

\6. 学生对象初始完毕，把对象地址赋值给s变量

### **常用参数配置**

| **参数**                   | **含义**                                                     | **默认值**                                                   | **备注**                                                     |
| -------------------------- | ------------------------------------------------------------ | ------------------------------------------------------------ | ------------------------------------------------------------ |
| -Xms                       | 表示初始堆大小                                               | 默认为物理内存的1/64(<1GB)                                   | 默认(MinHeapFreeRatio参数可以调整)空余堆内存小于40%时，JVM就会增大堆直到-Xmx的最大限制. |
| -Xmx                       | 最大堆大小                                                   | 物理内存的1/4(<1GB)                                          | (MaxHeapFreeRatio参数可以调整)空余堆内存大于70%时，JVM会减少堆直到 -Xms的最小限制 |
| -Xmn                       | 年轻代大小(1.4or lator)                                      |                                                              | 注意：此处的大小是（eden+ 2 survivor space).与jmap -heap中显示的New gen是不同的整个堆大小=年轻代大小 + 年老代大小 + 持久代大小.增大年轻代后,将会减小年老代大小.此值对系统性能影响较大,Sun官方推荐配置为整个堆的3/8 |
| -XX:NewSize                | 设置年轻代大小(for 1.3/1.4)                                  |                                                              |                                                              |
| -XX:MaxNewSize             | 年轻代最大值(for 1.3/1.4)                                    |                                                              |                                                              |
| -XX:PermSize               | 设置持久代(perm gen)初始值                                   | 物理内存的1/64                                               |                                                              |
| -XX:MaxPermSize            | 设置持久代最大值                                             | 物理内存的1/4                                                |                                                              |
| -Xss                       | 每个线程的堆栈大小                                           |                                                              | JDK5.0以后每个线程堆栈大小为1M,以前每个线程堆栈大小为256K.更具应用的线程所需内存大小进行 调整.在相同物理内存下,减小这个值能生成更多的线程.但是操作系统对一个进程内的线程数还是有限制的,不能无限生成,经验值在3000~5000左右一般小的应用， 如果栈不是很深， 应该是128k够用的 大的应用建议使用256k。这个选项对性能影响比较大，需要严格的测试。（校长）和threadstacksize选项解释很类似,官方文档似乎没有解释,在论坛中有这样一句话-Xss is translated in a VM flag named ThreadStackSize一般设置这个值就可以了。 |
| -XX:NewRatio               | 年轻代(包括Eden和两个Survivor区)与年老代的比值(除去持久代)   |                                                              |                                                              |
| -XX:NewRatio               | =4表示年轻代与年老代所占比值为1:4, 年轻代占整个堆栈的1/5 Xms = Xmx并且设置了Xmn的情况下，该参数不需要进行设置。 |                                                              |                                                              |
| -XX:SurvivorRatio          | Eden区与Survivor区的大小比值                                 |                                                              | 设置为8,则两个Survivor区与一个Eden区的比值为2:8,一个Survivor区占整个年轻代的1/10 |
| -XX:MaxTenuringThreshold   | 垃圾最大年龄                                                 | 如果设置为0的话,则年轻代对象不经过Survivor区,直接进入年老代. 对于年老代比较多的应用,可以提高效率.如果将此值设置为一个较大值,则年轻代对象会在Survivor区进行多次复制,这样可以增加对象再年轻代的存活 时间,增加在年轻代即被回收的概率该参数只有在串行GC时才有效. |                                                              |
| -XX:PretenureSizeThreshold | 对象超过多大是直接在旧生代分配                               | 0 单位字节                                                   | 新生代采用Parallel Scavenge GC时无效另一种直接在旧生代分配的情况是大的数组对象,且数组中无外部引用对象. |

相关资料： <http://blog.csdn.net/wisgood/article/details/16818243>

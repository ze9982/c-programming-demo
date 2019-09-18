#浅谈JAVA中的命名规范  
##一、命名规范  
1.包名统一使用小写，点分隔符之间有且仅有一个自然语义的英语单词。包名统一使用单数形式，但是类名如果有复数含义，类名可以使用复数形式。  
正例：应用工具包名为com.java.util、类名为StringUtils  
  
2.类名、接口名使用UpperCamelCase风格，必须遵从驼峰形式，但以下情形例外：DO/BO/DTO/VO/AO/PO/UID等。  
正例：
```
UserLoginCheckService/UserDO  
```
反例：
```
userlogincheckservice/UserDo  
```
  
3.方法名、参数名、成员变量、局部变量都统一使用lowerCamelCase风格，必须遵从驼峰形式。  
正例：
```
userServiceImpl  
```
反例：
```
userserviceimpl  
```

4.常量命名全部大写，单词间用下划线隔开，力求语义表达完整清楚，不要嫌名字长。  
正例：
```
MAX_BOOK_COUNT/CACHE_EXPIRED_TIME  
```

反例：
```
MAX_COUNT/EXPIRED_TIME  
```

5.为了达到代码自解释的目标，任何自定义编程元素在命名时，使用尽量完整的单词组合来表达其意，即要做到“见名知意”。  
正例：在 JDK 中，表达原子更新的类名为：AtomicReferenceFieldUpdater  
  
反例：String a = "李四"; // 天啦噜，鬼知道你这个a是啥意思啊  
  
6.定义数组时，类型与中括号紧挨相连  
正例：  
```c
int[] array = new int[10];

int array[] = new int[10]; // 不建议这样写
```
  
7.抽象类命名使用 Abstract 或 Base 开头；异常类命名使用 Exception 结尾；测试类命名以它要测试的类的名称开始，以 Test 结尾。  
正例：
```
AbstractService/CommonException/DemoTest  
```

8.杜绝完全不规范的缩写，避免望文不知义。  
反例：AbstractClass“缩写”命名成 AbsClass；condition“缩写” 命名成 condi，此类随意缩写严重降低了代码的可阅读性。  
  
9.如果模块、 接口、类、方法使用了设计模式，在命名时需体现出具体模式  
说明：将设计模式体现在名字中，有利于阅读者快速理解架构设计理念。  
  
正例：  
```c
public class OrderFactory;
public class LoginProxy;
public class ResourceObserver;
```
  
10.对于 Service 和 DAO 类，基于 SOA 的理念，暴露出来的服务一定是接口，内部的实现类用Impl 的后缀与接口区别。     
正例：CacheServiceImpl实现CacheService接口  
  
11.如果是形容能力的接口名称，取对应的形容词为接口名（通常是–able 的形容词）。  
正例：JDK中的Comparable接口  
  
12.在long或者Long赋值时，数值后使用大写的 L，不能是小写的 l，小写容易跟数字 1 混淆，造成误解。  
说明：Long a = 2l；写的是数字的 21，还是 Long 型的 2 ？？  
  
13.不允许任何魔法值（即未经预先定义的常量）直接出现在代码中  
正例：  
```c
public static final ORDER_REDIS_KEY_PREFIX = "orderId_";
String orderRedisKey = ORDER_REDIS_KEY_PREFIX + orderId;
```
  
反例：  
```c
String redisKey = "orderId_" + orderId;
```
  
14.枚举类名带上Enum后缀，枚举成员名称需要全大写，单词间用下划线隔开。  
正例：枚举名字为ProcessStatusEnum的成员名称：SUCCESS / UNKNOWN_REASON  
  
##二、注释规范  
  
1、类注释  
  
在每个类前面必须加上类注释，注释模板如下：  
```
/**
* Copyright (C), 2006-2010, ChengDu Lovo info. Co., Ltd.
* FileName: Test.java
* 类的详细说明
*
* @author 类创建者姓名
    * @Date    创建日期
* @version 1.00
*/
```
  
2、属性注释  
在每个属性前面必须加上属性注释，注释模板如下：  
```
/** 提示信息 */  
```
private String strMsg = null;  
  
3、方法注释  
在每个方法前面必须加上方法注释，注释模板如下：  
```
/**
* 类方法的详细使用说明
*
* @param 参数1 参数1的使用说明
* @return 返回结果的说明
* @throws 异常类型.错误代码 注明从此类方法中抛出异常的说明
*/
```
  
4、构造方法注释  
在每个构造方法前面必须加上注释，注释模板如下：  
```
/**
* 构造方法的详细使用说明
*
* @param 参数1 参数1的使用说明
* @throws 异常类型.错误代码 注明从此类方法中抛出异常的说明
*/
```
  
5、方法内部注释  
在方法内部使用单行或者多行注释，该注释根据实际情况添加。  
如：  
```
//背景颜色  
       Color bgColor = Color.RED  
```

  
这是我对Martin Fowler的《重构：改进现有代码的设计》的总结。我在学习时使用它，并作为快速参考。它并不打算成为这本书的独立替代品，所以如果你真的想学习这里介绍的概念，请购买并阅读这本书，并将此存储库用作参考和指南。

  
如果你是发布者，并且认为这个仓库不应该公开，只要给我发一封电子邮件到huoxudong125 \[at\] gmail \[dot\] com，我会把它变成私人的。

  
贡献：问题，评论和拉请求是超级受欢迎的。

*   [1.内容表](#1-table-of-content)
*   [3.代码中的难闻气味](#3-bad-smells-in-code)
    *   [1.重复代码](#1-duplicated-code)
    *   [2.长方法](#2-long-method)
    *   [3.大班](#3-large-classes)
    *   [4.长参数列表](#4-long-parameter-list)
    *   [5.分歧的变化](#5-divergent-change)
    *   [6.散弹枪手术](#6-shotgun-surgery)
    *   [7.功能羡慕](#7-feature-envy)
    *   [8.数据块](#8-data-clumps)
    *   [9.原始痴迷](#9-primitive-obsession)
    *   [10\. Switch语句](#10-switch-statements)
    *   [11.并行继承层次](#11-parallel-inheritance-hierarchies)
    *   [12.懒惰的阶级](#12-lazy-class)
    *   [13.投机性的普遍性](#13-speculative-generality)
    *   [14.临时外勤](#14-temporary-field)
    *   [15.消息间链](#15-message-chain)
    *   [16.中间人](#16-middle-man)
    *   [17.不适当的亲密](#17-inappropriate-intimacy)
    *   [18.具有不同接口的替代类](#18-alternative-classes-with-different-interfaces)
    *   [19.不完整的库类](#19-incomplete-library-class)
    *   [20.数据类](#20-data-class)
    *   [21.拒绝遗赠](#21-refused-bequest)
    *   [22.评论](#22-comments)
*   [6.合成方法](#6-composing-methods)
    *   [1.提取方法](#1-extract-method)
    *   [2.内联方法](#2-inline-method)
    *   [3.在线温度](#3-inline-temp)
    *   [4.将Temp替换为Query](#4-replace-temp-with-query)
    *   [5.引入解释变量](#5-introduce-explaining-variable)
    *   [6.拆分临时变量](#6-split-temporary-variable)
    *   [7.删除参数](#7-remove-assignments-to-parameters)
    *   [8.用方法对象替换方法](#8-replace-method-with-method-object)
    *   [9.替代算法](#9-substitute-algorithm)
*   [7.在元素之间移动要素](#7-moving-features-between-elements)
    *   [10\. Move方法](#10-move-method)
    *   [11.搬场](#11-move-field)
    *   [12.提取类](#12-extract-class)
    *   [13.内联类](#13-inline-class)
    *   [14.隐藏委托](#14-hide-delegate)
    *   [15.删除中间人](#15-remove-middle-man)
    *   [16.引进国外方法](#16-introduce-foreign-method)
    *   [17.引入本地扩展](#17-introduce-local-extension)
*   [8.组织数据](#8-organizing-data)
    *   [18.自封装字段](#18-self-encapsulate-field)
    *   [19.将数据值替换为对象](#19-replace-data-value-with-object)
    *   [20.将值更改为参考](#20-change-value-to-reference)
    *   [21.更改对值的引用](#21-change-reference-to-value)
    *   [22.将数组替换为对象](#22-replace-array-with-object)
    *   [23.重复观察数据](#23-duplicate-observed-data)
    *   [24.将单向关联更改为双向关联](#24-change-unidirectional-association-to-bidirectional)
    *   [25.将双向关联更改为单向](#25-change-bidirectional-association-to-unidirectional)
    *   [26.用符号常数代替幻数](#26-replace-magic-number-with-symbolic-constant)
    *   [27.封装字段](#27-encapsulate-field)
    *   [28.封装集合](#28-encapsulate-collection)
    *   [29.删除带有数据类的记录](#29-remove-record-with-data-class)
    *   [30.将类型代码替换为类](#30-replace-type-code-with-class)
    *   [31.用子类替换类型代码](#31-replace-type-code-with-subclasses)
    *   [32.将类型代码替换为状态/策略](#32-replace-type-code-with-statestrategy)
    *   [32.用字段替换子类](#32-replace-subclass-with-fields)
*   [9.条件表达式的简化](#9-simplifying-conditional-expressions)
    *   [33.分解条件](#33-decompose-conditional)
    *   [34.合并条件表达式](#34-consolidate-conditional-expression)
    *   [35.合并重复的条件片段](#35-consolidate-duplicate-conditional-fragments)
    *   [36.删除控制标志](#36-remove-control-flag)
    *   [37.用Guard子句替换嵌套条件句](#37-replace-nested-conditional-with-guard-clauses)
    *   [38.将条件替换为多态](#38-replace-conditional-with-polymorphism)
    *   [39.介绍对象](#39-introduce-null-object)
    *   [40.介绍断言](#40-introduce-assertion)
*   [10.让方法更简单](#10-making-method-calls-simpler)
    *   [41.反渗透法](#41-rename-method)
    *   [42.添加参数](#42-add-parameter)
    *   [43.删除参数](#43-remove-parameter)
    *   [44.将查询与修改器分开](#44-separate-query-from-modifier)
    *   [45.参数化方法](#45-parameterize-method)
    *   [46.用显式方法替换参数](#46-replace-parameter-with-explicit-methods)
    *   [47.保留整个对象](#47-preserve-whole-object)
    *   [48.将参数替换为方法](#48-replace-parameter-with-method)
    *   [49.引入参数对象](#49-introduce-parameter-object)
    *   [50.删除设置方法](#50-remove-setting-method)
    *   [51\. Hide方法](#51-hide-method)
    *   [52.将构造函数替换为工厂方法](#52-replace-constructor-with-factory-method)
    *   [53.封装Downcast](#53-encapsulate-downcast)
    *   [54.将错误代码替换为异常](#54-replace-error-code-with-exception)
    *   [55.将异常替换为测试](#55-replace-exception-with-test)
*   [11.处理泛化](#11-dealing-with-generalization)
    *   [56.上拉场](#56-pull-up-field)
    *   [57.上拉法](#57-pull-up-method)
    *   [58.上拉构造器主体](#58-pull-up-constructor-body)
    *   [59.下推法](#59-push-down-method)
    *   [60.下推字段](#60-push-down-field)
    *   [61.提取子类](#61-extract-subclass)
    *   [62.提取超类](#62-extract-superclass)
    *   [63.提取接口](#63-extract-interface)
    *   [64.折叠层次结构](#64-collapse-hierarchy)
    *   [65.表单模板方法](#65-form-template-method)
    *   [66.将继承替换为委托](#66-replace-inheritance-with-delegation)
    *   [67.将委托替换为继承](#67-replace-delegation-with-inheritance)
*   [12.大重构](#12-big-refactorings)
    *   [68.第1113章挑拨传承](#68-tease-apart-inheritance)
    *   [69.将程序设计转换为对象](#69-convert-procedural-design-to-objects)
    *   [70.将域与表示分离](#70-separate-domain-from-presentation)
    *   [71.提取层次结构](#71-extract-hierarchy)

  
在多个地方有相同的代码结构。

  
程序越长，理解起来就越困难。

  
当一个类试图做太多的事情时，重复的代码不会太远。

  
它们难以理解，不一致，难以使用。

  
当一个类通常由于不同的原因以不同的方式改变时。

  
当你每次做一种改变时，你必须对很多不同的类做很多小的改变。

  
一个方法似乎对一个类比它实际所在的类更感兴趣。

  
数据包（字段、参数等）一起玩的人

  
使用基本类型而不是小对象。

  
同样的switch语句分散在程序的不同地方。使用多态性。

  
每当你创建一个类的子类时，你也必须创建另一个类的子类。

  
一个没有做足够的工作来支付自己的班级应该被淘汰。

  
各种各样的钩子和特殊的箱子来处理不需要的东西。

  
仅在某些情况下设置的实例变量。

  
当客户端向一个对象请求另一个对象时，客户端又向另一个对象请求...

  
当一个对象委托了它的大部分功能时。

### 17\. Inappropriate Intimacy

[](#17-inappropriate-intimacy)

When classes access to much to another classes.

### 18\. Alternative Classes with Different Interfaces

[](#18-alternative-classes-with-different-interfaces)

Classes with methods that look to similar.

### 19\. Incomplete Library Class

[](#19-incomplete-library-class)

When we need extra features in libraries.

Don't allow manipulation in Data Classes. Use encapsulation and immutability.

Subclasses that don't make uses of parents methods.

Not all comments but the ones that are there because the code is bad.

You have a code fragment that can be grouped together.

```java
	void printOwing(double amount) {
		printBanner();
		//print details
		System.out.println ("name:" + _name);
		System.out.println ("amount" + amount);
	}
```

to

```java
	void printOwing(double amount) {
		printBanner();
		printDetails(amount);
	}

	void printDetails (double amount) {
		System.out.println ("name:" + _name);
	System.out.println ("amount" + amount);
	}
```

**Motivation**

*   Increases the chances that other methods can use a method
*   Allows the higher-level methods to read more like a series of comments

```java
	void printOwing(double previousAmount) {
		Enumeration e = _orders.elements();
		double outstanding = previousAmount * 1.2;
		printBanner();

		// calculate outstanding
		while (e.hasMoreElements()) {
			Order each = (Order) e.nextElement();
			outstanding += each.getAmount();
		}
		printDetails(outstanding);
	}
```

to

```java
	void printOwing(double previousAmount) {
		printBanner();
		double outstanding = getOutstanding(previousAmount * 1.2);
		printDetails(outstanding);
	}

	double getOutstanding(double initialValue) {
		double result = initialValue;
		Enumeration e = _orders.elements();

		while (e.hasMoreElements()) {
			Order each = (Order) e.nextElement();
			result += each.getAmount();
		}
		return result;
	}
```

A method's body is just as clear as its name.

```java
	int getRating() {
		return (moreThanFiveLateDeliveries()) ? 2 : 1;
	}

	boolean moreThanFiveLateDeliveries() {
		return _numberOfLateDeliveries > 5;
	}
```

to

```java
	int getRating() {
		return (_numberOfLateDeliveries > 5) ? 2 : 1;
	}
```

**Motivation**

*   When Indirection is needless (simple delegation) becomes irritating.
*   If group of methods are badly factored and grouping them makes it clearer

You have a temp that is assigned to once with a simple expression, and the temp is getting in the way of other refactorings.

```java
	double basePrice = anOrder.basePrice();
	return (basePrice > 1000)
```

to

```java
	return (anOrder.basePrice() > 1000)
```

**Motivation**

*   Use it with [4\. Replace Temp with Query](#4-replace-temp-with-query)

4\. Replace Temp with Query
---------------------------

[](#4-replace-temp-with-query)

You are using a temporary variable to hold the result of an expression.

```java
	double basePrice = _quantity * _itemPrice;
	if (basePrice > 1000)
		return basePrice * 0.95;
	else
		return basePrice * 0.98;
```

to

```java
	if (basePrice() > 1000)
		return basePrice() * 0.95;
	else
		return basePrice() * 0.98;
	...
	double basePrice() {
		return _quantity * _itemPrice;
	}
```

**Motivation**

*   Replacing the temp with a query method, any method in the class can get at the information.
*   Is a vital step before [1\. Extract Method](#1-extract-method)

5\. Introduce Explaining Variable
---------------------------------

[](#5-introduce-explaining-variable)

You have a complicated expression

```java
	if ( (platform.toUpperCase().indexOf("MAC") > -1) &&
		(browser.toUpperCase().indexOf("IE") > -1) &&
		wasInitialized() && resize > 0 )
	{
		// do something
	}
```

to

```java
	final boolean isMacOs = platform.toUpperCase().indexOf("MAC") >-1;
	final boolean isIEBrowser = browser.toUpperCase().indexOf("IE") >-1;
	final boolean wasResized = resize > 0;
	if (isMacOs && isIEBrowser && wasInitialized() && wasResized) {
		// do something
	}
```

**Motivation**

*   When expressions are hard to read

6\. Split Temporary Variable
----------------------------

[](#6-split-temporary-variable)

You have a temporary variable assigned to more than once, but is not a loop variable nor a collecting temporary variable.

```java
	double temp = 2 * (_height + _width);
	System.out.println (temp);
	temp = _height * _width;
	System.out.println (temp);
```

to

```java
	final double perimeter = 2 * (_height + _width);
	System.out.println (perimeter);
	final double area = _height * _width;
	System.out.println (area);
```

**Motivation**

*   Variables should not have more than one responsibility.
*   Using a temp for two different things is very confusing for the reader.

7\. Remove Assignments to Parameters
------------------------------------

[](#7-remove-assignments-to-parameters)

The code assign to a parameter

```java
	int discount (int inputVal, int quantity, int yearToDate) {
		if (inputVal > 50) inputVal -= 2;
```

to

```java
	int discount (int inputVal, int quantity, int yearToDate) {
		int result = inputVal;
		if (inputVal > 50) result -= 2;
```

**Motivation**

*   You can change the internals of object is passed but do not point to another object.
*   Use only the parameter to represent what has been passed.

8\. Replace Method with Method Object
-------------------------------------

[](#8-replace-method-with-method-object)

You have a long method that uses local variables in such a way that you cannot apply Extract Method.

```java
	class Order...
		double price() {
			double primaryBasePrice;
			double secondaryBasePrice;
			double tertiaryBasePrice;
			// long computation;
			...
		}
```

to

```java
	class Order...
		double price(){
			return new PriceCalculator(this).compute()
		}
	}

	class PriceCalculato...
	compute(){
		double primaryBasePrice;
		double secondaryBasePrice;
		double tertiaryBasePrice;
		// long computation;
		return ...
	}
```

**Motivation**

*   When a method has lot of local variables and applying decomposition is not possible

_This sample does not really needs this refactoring, but shows the way to do it._

```java
	Class Account
		int gamma (int inputVal, int quantity, int yearToDate) {
			int importantValue1 = (inputVal * quantity) + delta();
			int importantValue2 = (inputVal * yearToDate) + 100;
			if ((yearToDate - importantValue1) > 100)
			importantValue2 -= 20;
			int importantValue3 = importantValue2 * 7;
			// and so on.
			return importantValue3 - 2 * importantValue1;
		}
	}
```

to

```java
	class Gamma...
		private final Account _account;
		private int inputVal;
		private int quantity;
		private int yearToDate;
		private int importantValue1;
		private int importantValue2;
		private int importantValue3;

		Gamma (Account source, int inputValArg, int quantityArg, int yearToDateArg) {
			_account = source;
			inputVal = inputValArg;
			quantity = quantityArg;
			yearToDate = yearToDateArg;
		}

		int compute () {
			importantValue1 = (inputVal * quantity) + _account.delta();
			importantValue2 = (inputVal * yearToDate) + 100;
			if ((yearToDate - importantValue1) > 100)
			importantValue2 -= 20;
			int importantValue3 = importantValue2 * 7;
			// and so on.
			return importantValue3 - 2 * importantValue1;
		}

		int gamma (int inputVal, int quantity, int yearToDate) {
			return new Gamma(this, inputVal, quantity,yearToDate).compute();
		}
```

You want to replace an algorithm with one that is clearer.

```java
	String foundPerson(String[] people){
		for (int i = 0; i < people.length; i++) {
			if (people[i].equals ("Don")){
				return "Don";
			}
			if (people[i].equals ("John")){
				return "John";
			}
			if (people[i].equals ("Kent")){
				return "Kent";
			}
		}
		return "";
	}
```

to

```java
	String foundPerson(String[] people){
		List candidates = Arrays.asList(new String[] {"Don", "John","Kent"});
	for (int i = 0; i<people.length; i++)
		if (candidates.contains(people[i]))
			return people[i];
	return "";
	}
```

**Motivation**

*   Break down something complex into simpler pieces.
*   Makes easier apply changes to the algorithm.
*   Substituting a large, complex algorithm is very difficult; making it simple can make the substitution tractable.

A method is, or will be, using or used by more features of another class than the class on which it is defined.

_Create a new method with a similar body in the class it uses most. Either turn the old method into a simple delegation, or remove it altogether._

```java
	class Class1 {
		aMethod()
	}

	class Class2 {	}
```

to

```java
	class Class1 {	}

	class Class2 {
		aMethod()
	}
```

**Motivation**

When classes do to much work or when collaborate too much and are highly coupled

A field is, or will be, used by another class more than the class on which it is defined. _Create a new field in the target class, and change all its users._

```java
	class Class1 {
		aField
	}

	class Class2 {	}
```

to

```java
	class Class1 {	}

	class Class2 {
		aField
	}
```

**Motivation**

If a field is used mostly by outer classes and before [12\. Extract Class](#12-extract-class)

You have one class doing work that should be done by two. _Create a new class and move the relevant fields and methods from the old class into the new class._

```java
	class Person {
		name,
		officeAreaCode,
		officeNumber,
		getTelephoneNumber()
	}
```

to

```java
	class Person {
		name,
		getTelephoneNumber()
	}

	class TelephoneNumber {
		areaCode,
		number,
		getTelephoneNumber()
	}
```

**Motivation**

Classes grow. _Split them when_:

*   subsets of methods seem to be together
*   subsets of data usually change together or depend on each other

A class isn't doing very much. _Move all its features into another class and delete it._

```java
	class Person {
		name,
		getTelephoneNumber()
	}

	class TelephoneNumber {
		areaCode,
		number,
		getTelephoneNumber()
	}
```

to

```java
	class Person {
		name,
		officeAreaCode,
		officeNumber,
		getTelephoneNumber()
	}
```

**Motivation**

After refactoring normally there are a bunch of responsibilities moved out of the class, letting the class with little left.

A client is calling a delegate class of an object.  
_Create methods on the server to hide the delegate._

```java
	class ClientClass {
		//Dependencies
		Person person = new Person()
		Department department = new Department()
		person.doSomething()
		department.doSomething()
	}
```

to

```java
	class ClientClass {
		Person person = new Person()
		person.doSomething()
	}

	class Person{
		Department department = new Department()
		department.doSomething()
	}
```

_The solution_

```java
	class ClientClass{
		Server server = new Server()
		server.doSomething()
	}

	class Server{
		Delegate delegate = new Delegate()
		void doSomething(){
			delegate.doSomething()
		}
	}
	// The delegate is hidden to the client class.
	// Changes won't be propagated to the client they will only affect the server
	class Delegate{
		void doSomething(){...}
	}
```

**Motivation**

Key of encapsulation. Classes should know as less as possible of other classes.

`> manager = john.getDepartment().getManager();`

```java
	class Person {
		Department _department;
		public Department getDepartment() {
			return _department;
		}
		public void setDepartment(Department arg) {
			_department = arg;
			}
		}

	class Department {
		private String _chargeCode;
		private Person _manager;
		public Department (Person manager) {
			_manager = manager;
		}
		public Person getManager() {
			return _manager;
		}
		...
```

to

`> manager = john.getManager();`

```java
	class Person {
		...
		public Person getManager() {
			return _department.getManager();
		}
	}
```

A class is doing too much simple delegation. _Get the client to call the delegate directly._

```java
	class ClientClass {
		Person person = new Person()
		person.doSomething()
	}

	class Person{
		Department department = new Department()
		department.doSomething()
	}
```

to

```java
	class ClientClass {
		//Dependencies
		Person person = new Person()
		Department department = new Department()
		person.doSomething()
		department.doSomething()
	}
```

**Motivation**

When the "Middle man" (the server) does to much is time for the client to call the delegate directly.

16\. Introduce Foreign Method
-----------------------------

[](#16-introduce-foreign-method)

A server class you are using needs an additional method, but you can't modify the class.  
_Create a method in the client class with an instance of the server class as its first argument._

```java
	Date newStart = new Date(previousEnd.getYear(),previousEnd.getMonth(),previousEnd.getDate()+1);
```

to

```java
	Date newStart = nextDay(previousEnd);

	private static Date nextDay(Date date){
		return new Date(date.getYear(),date.getMonth(),date.getDate()+1);
	}
```

**Motivation**

When there is a lack of a method in class that you use a lot and you can not change that class.

17\. Introduce Local Extension
------------------------------

[](#17-introduce-local-extension)

A server class you are using needs several additional methods, but you can't modify the class. _Create a new class that contains these extra methods. Make this extension class a subclass or a wrapper of the original._

```java
	class ClientClass(){

		Date date = new Date()
		nextDate = nextDay(date);

		private static Date nextDay(Date date){
			return new Date(date.getYear(),date.getMonth(),date.getDate()+1);
		}
	}
```

to

```java
	class ClientClass() {
		MfDate date = new MfDate()
		nextDate = nextDate(date)
	}
	class MfDate() extends Date {
		...
		private static Date nextDay(Date date){
			return new Date(date.getYear(),date.getMonth(),date.getDate()+1);
		}
	}
```

**Motivation**

When plenty of [16\. Introduce Foreign Method](#16-introduce-foreign-method) need to be added to a class.

18\. Self Encapsulate Field
---------------------------

[](#18-self-encapsulate-field)

You are accessing a field directly, but the coupling to the field is becoming awkward.  
_Create getting and setting methods for the field and use only those to access the field._

```java
	private int _low, _high;
	boolean includes (int arg) {
		return arg >= _low && arg <= _high;
	}
```

to

```java
	private int _low, _high;
	boolean includes (int arg) {
		return arg >= getLow() && arg <= getHigh();
	}
	int getLow() {return _low;}
	int getHigh() {return _high;}
```

**Motivation**  
Allows a subclass to override how to get that information with a method and that it supports more flexibility in managing the data, such as lazy initialization.

19\. Replace Data Value with Object
-----------------------------------

[](#19-replace-data-value-with-object)

You have a data item that needs additional data or behavior.  
_Turn the data item into an object_

```java
	class Order...{
		private String _customer;
		public Order (String customer) {
			_customer = customer;
		}
	}
```

to

```java
	class Order...{
		public Order (String customer) {
			_customer = new Customer(customer);
		}
	}

	class Customer {
		public Customer (String name) {
			_name = name;
		}
	}
```

**Motivation**  
Simple data items aren't so simple anymore.

20\. Change Value to Reference
------------------------------

[](#20-change-value-to-reference)

You have a class with many equal instances that you want to replace with a single object.  
_Turn the object into a reference object._

```java
	class Order...{
		public Order (String customer) {
			_customer = new Customer(customer);
		}
	}

	class Customer {
		public Customer (String name) {
			_name = name;
		}
	}
```

to

```java
	//Use Factory Method
	class Customer...
		static void loadCustomers() {
			new Customer ("Lemon Car Hire").store();
			new Customer ("Associated Coffee Machines").store();
			new Customer ("Bilston Gasworks").store();
		}
		private void store() {
			_instances.put(this.getName(), this);
		}
		public static Customer create (String name) {
			return (Customer) _instances.get(name);
		}
```

**Motivation**  
Reference objects are things like customer or account. Each object stands for one object in the real world, and you use the object identity to test whether they are equal.

21\. Change Reference to Value
------------------------------

[](#21-change-reference-to-value)

You have a reference object that is small, immutable, and awkward to manage.  
_Turn it into a value object_

```java
	new Currency("USD").equals(new Currency("USD")) // returns false
```

to

```java
	
	// Add `equals` and `hashCode` to the Currency class 
	class Currency{ 
		...
		public boolean equals(Object arg) {
	 		if (! (arg instanceof Currency)) return false;
	 		Currency other = (Currency) arg;
			return (_code.equals(other._code));
		}

		public int hashCode() {
 			return _code.hashCode();
 		}
 	}

 	// Now you can do
	new Currency("USD").equals(new Currency("USD")) // now returns true
```

**Motivation**  
Working with the reference object becomes awkward. The reference object is immutable and small. Used in distributed or concurrent systems.

22\. Replace Array with Object
------------------------------

[](#22-replace-array-with-object)

You have an array in which certain elements mean different things.  
_Replace the array with an object that has a field for each element_

```java
	String[] row = new String[3];
	row [0] = "Liverpool";
	row [1] = "15";
```

to

```java
	Performance row = new Performance();
	row.setName("Liverpool");
	row.setWins("15");
```

**Motivation**  
Arrays should be used only to contain a collection of similar objects in some order.

23\. Duplicate Observed Data
----------------------------

[](#23-duplicate-observed-data)

You have domain data available only in a GUI control, and domain methods need access.  
_Copy the data to a domain object. Set up an observer to synchronize the two pieces of data_  
**Motivation**  
To separate code that handles the user interface from code that handles the business logic.

24\. Change Unidirectional Association to Bidirectional
-------------------------------------------------------

[](#24-change-unidirectional-association-to-bidirectional)

You have two classes that need to use each other's features, but there is only a one-way link.  
_Add back pointers, and change modifiers to update both sets_

```java
	class Order...
		Customer getCustomer() {
			return _customer;
		}
		void setCustomer (Customer arg) {
			_customer = arg;
		}
		Customer _customer;
	}
```

to

```java
	class Order...
		Customer getCustomer() {
			return _customer;
		}
		void setCustomer (Customer arg) {
			if (_customer != null) _customer.friendOrders().remove(this);
			_customer = arg;
			if (_customer != null) _customer.friendOrders().add(this);
		}
		private Customer _customer;

		class Customer...
			void addOrder(Order arg) {
				arg.setCustomer(this);
			}
			private Set _orders = new HashSet();

			Set friendOrders() {
				/** should only be used by Order */
				return _orders;
			}
		}
	}

	// Many to Many
	class Order... //controlling methods
		void addCustomer (Customer arg) {
			arg.friendOrders().add(this);
			_customers.add(arg);
		}
		void removeCustomer (Customer arg) {
			arg.friendOrders().remove(this);
			_customers.remove(arg);
		}
	class Customer...
		void addOrder(Order arg) {
			arg.addCustomer(this);
		}
		void removeOrder(Order arg) {
			arg.removeCustomer(this);
		}
	}
```

**Motivation**  
When the object referenced needs access access to the object that refer to it.

25\. Change Bidirectional Association to Unidirectional
-------------------------------------------------------

[](#25-change-bidirectional-association-to-unidirectional)

You have a two-way association but one class no longer needs features from the other.  
_Drop the unneeded end of the association_  
**Motivation**  
If Bidirectional association is not needed, reduce complexity, handle zombie objects, eliminate interdependency

26\. Replace Magic Number with Symbolic Constant
------------------------------------------------

[](#26-replace-magic-number-with-symbolic-constant)

You have a literal number with a particular meaning.  
_Create a constant, name it after the meaning, and replace the number with it_

```java
	double potentialEnergy(double mass, double height) {
		return mass * 9.81 * height;
	}
```

to

```java
	double potentialEnergy(double mass, double height) {
		return mass * GRAVITATIONAL_CONSTANT * height;
	}
	static final double GRAVITATIONAL_CONSTANT = 9.81;
```

**Motivation**  
Avoid using Magic numbers.

There is a public field.  
_Make it private and provide accessors_

to

```java
	private String _name;
	public String getName() {return _name;}
	public void setName(String arg) {_name = arg;}
```

**Motivation**  
You should never make your data public.

28\. Encapsulate Collection
---------------------------

[](#28-encapsulate-collection)

A method returns a collection.  
_Make it return a read-only view and provide add/remove methods_

```java
	class Person {
		Person (String name){
			HashSet set new HashSet()
		}
		Set getCourses(){}
		void setCourses(:Set){}
	}
```

to

```java
	class Person {
		Person (String name){
			HashSet set new HashSet()
		}
		Unmodifiable Set getCourses(){}
		void addCourses(:Course){}
		void removeCourses(:Course){}
	}
```

**Motivation**

*   Encapsulated reduce the coupling of the owning class to its clients.
*   The getter should not return the collection object itself.
*   The getter should return something that prevents manipulation of the collection and hides unnecessary details.
*   There should not be a setter for collection, only operations to add and remove elements.

29\. Remove Record with data class
----------------------------------

[](#29-remove-record-with-data-class)

You need to interface with a record structure in a traditional programming environment.  
_Make a dumb data object for the record._

**Motivation**

*   Copying a legacy program
*   Communicating a structured record with a traditional programming API or database.

30\. Replace Type Code with Class
---------------------------------

[](#30-replace-type-code-with-class)

A class has a numeric type code that does not affect its behavior.  
_Replace the number with a new class._

```java
	class Person{
		O:Int;
		A:Int;
		B:Int;
		AB:Int;
		bloodGroup:Int;
	}
```

to

```java
	class Person{
		bloodGroup:BloodGroup;
	}

	class BloodGroup{
		O:BloodGroup;
		A:BloodGroup;
		B:BloodGroup;
		AB:BloodGroup;
	}
```

**Motivation**  
Statically type checking.

31\. Replace Type Code with Subclasses
--------------------------------------

[](#31-replace-type-code-with-subclasses)

You have an immutable type code that affects the behavior of a class.  
_Replace the type code with subclasses._

```java
	class Employee...
		private int _type;

		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		Employee (int type) {
			_type = type;
		}
	}
```

to

```java
	abstract int getType();
	static Employee create(int type) {
		switch (type) {
			case ENGINEER:
				return new Engineer();
			case SALESMAN:
				return new Salesman();
			case MANAGER:
				return new Manager();
			default:
				throw new IllegalArgumentException("Incorrect type code value");
		}
	}
```

**Motivation**

*   Execute different code depending on the value of a type.
*   When each type code object has unique features.
*   Structure to implement [38\. Replace Conditional with Polymorphism](#38-replace-conditional-with-polymorphism)
*   Use of [30\. Replace Type Code with Class](#30-replace-type-code-with-class)

32\. Replace Type Code with State/Strategy
------------------------------------------

[](#32-replace-type-code-with-statestrategy)

You have a type code that affects the behavior of a class, but you cannot use subclassing.  
_Replace the type code with a state object_

```java
	class Employee {
		private int _type;

		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		Employee (int type) {
			_type = type;
		}
		int payAmount() {
			switch (_type) {
				case ENGINEER:
					return _monthlySalary;
				case SALESMAN:
					return _monthlySalary + _commission;
				case MANAGER:
					return _monthlySalary + _bonus;
				default:
					throw new RuntimeException("Incorrect Employee");
				}
			}
		}
	}
```

to

```java
	class Employee...
		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		void setType(int arg) {
			_type = EmployeeType.newType(arg);
		}
		class EmployeeType...
			static EmployeeType newType(int code) {
				switch (code) {
					case ENGINEER:
						return new Engineer();
					case SALESMAN:
						return new Salesman();
					case MANAGER:
						return new Manager();
					default:
						throw new IllegalArgumentException("Incorrect Employee Code");
				}
			}
		}
		int payAmount() {
			switch (getType()) {
				case EmployeeType.ENGINEER:
					return _monthlySalary;
				case EmployeeType.SALESMAN:
					return _monthlySalary + _commission;
				case EmployeeType.MANAGER:
					return _monthlySalary + _bonus;
				default:
					throw new RuntimeException("Incorrect Employee");
			}
		}
	}
```

**Motivation**

*   Similar to [31\. Replace Type Code with Subclasses](#31-replace-type-code-with-subclasses), but can be used if the type code changes during the life of the object or if another reason prevents subclassing.
*   It uses either the state or strategy pattern

32\. Replace Subclass with Fields
---------------------------------

[](#32-replace-subclass-with-fields)

You have subclasses that vary only in methods that return constant data.  
_Change the methods to superclass fields and eliminate the subclasses_

```java
	abstract class Person {
		abstract boolean isMale();
		abstract char getCode();
		...
	}
	class Male extends Person {
			boolean isMale() {
			return true;
		}
		char getCode() {
			return 'M';
		}
	}
	class Female extends Person {
		boolean isMale() {
			return false;
		}
		char getCode() {
			return 'F';
		}
	}
```

to

```java
	class Person{
		protected Person (boolean isMale, char code) {
			_isMale = isMale;
			_code = code;
		}
		boolean isMale() {
			return _isMale;
		}
		static Person createMale(){
			return new Person(true, 'M');
		}
		static Person createFemale(){
			return new Person(false, 'F');
		}
	}
```

**Motivation**

*   Subclasses that consists only of constant methods is not doing enough to be worth existing.
*   Remove such subclasses completely by putting fields in the superclass.
*   Remove the extra complexity of the subclasses.

33\. Decompose Conditional
--------------------------

[](#33-decompose-conditional)

You have a complicated conditional (if-then-else) statement.  
_Extract methods from the condition, then part, and else parts_

```java
	if (date.before (SUMMER_START) || date.after(SUMMER_END))
		charge = quantity * _winterRate + _winterServiceCharge;
	else charge = quantity * _summerRate;
```

to

```java
	if (notSummer(date))
		charge = winterCharge(quantity);
	else charge = summerCharge (quantity);
```

**Motivation**

*   Highlight the condition and make it clearly what you are branching on.
*   Highlight the reason for the branching

34\. Consolidate Conditional Expression
---------------------------------------

[](#34-consolidate-conditional-expression)

You have a sequence of conditional tests with the same result.  
_Combine them into a single conditional expression and extract it_

```java
	double disabilityAmount() {
	if (_seniority < 2) return 0;
	if (_monthsDisabled > 12) return 0;
	if (_isPartTime) return 0;
	// compute the disability amount
```

to

```java
	double disabilityAmount() {
	if (isNotEligableForDisability()) return 0;
	// compute the disability amount
```

**Motivation**

*   Makes the check clearer by showing that you are really making a single check
*   Sets you up for [1\. Extract Method](#1-extract-method).
*   Clarify your code (replaces a statement of what you are doing with why you are doing it.)

35\. Consolidate Duplicate Conditional Fragments
------------------------------------------------

[](#35-consolidate-duplicate-conditional-fragments)

The same fragment of code is in all branches of a conditional expression.  
_Move it outside of the expression._

```java
	if (isSpecialDeal()) {
		total = price * 0.95;
		send();
	}
	else {
		total = price * 0.98;
		send();
	}
```

to

```java
	if (isSpecialDeal()) {
		total = price * 0.95;
	}
	else {
		total = price * 0.98;
	}
	send();
```

**Motivation**  
Makes clearer what varies and what stays the same.

You have a variable that is acting as a control flag for a series of boolean expressions.  
_Use a break or return instead_

```java
	void checkSecurity(String[] people) {
		boolean found = false;
			for (int i = 0; i < people.length; i++) {
				if (! found) {
					if (people[i].equals ("Don")){
						sendAlert();
						found = true;
					}
					if (people[i].equals ("John")){
						sendAlert();
						found = true;
					}
				}
		}
	}
```

to

```java
	void checkSecurity(String[] people) {
		for (int i = 0; i < people.length; i++) {
			if (people[i].equals ("Don")){
				sendAlert();
				break; // or return
			}
			if (people[i].equals ("John")){
				sendAlert();
				break; // or return
			}
		}
	}
```

**Motivation**

*   Control flag are used to determine when to stop looking, but modern languages enforce the use of `break` and `continue`
*   Make the real purpose of the conditional much more clear.

37\. Replace Nested Conditional with Guard Clauses
--------------------------------------------------

[](#37-replace-nested-conditional-with-guard-clauses)

A method has conditional behavior that does not make clear the normal path of execution.  
_Use guard clauses for all the special cases_

```java
	double getPayAmount() {
		double result;
		if (_isDead) result = deadAmount();
		else {
			if (_isSeparated) result = separatedAmount();
			else {
				if (_isRetired) result = retiredAmount();
				else result = normalPayAmount();
			};
		}
		return result;
	};
```

to

```java
	double getPayAmount() {
		if (_isDead) return deadAmount();
		if (_isSeparated) return separatedAmount();
		if (_isRetired) return retiredAmount();
		return normalPayAmount();
	};
```

**Motivation**

*   If the condition is an unusual condition, check the condition and return if the condition is true.
*   This kind of check is often called a **guard clause** \[Beck\].
*   If you are using an if-then-else construct you are giving equal weight to the if leg and the else leg.
*   This communicates to the reader that the legs are equally likely and important.
*   Instead the **guard clause** says, _"This is rare, and if it happens, do something and get out."_

38\. Replace Conditional with Polymorphism
------------------------------------------

[](#38-replace-conditional-with-polymorphism)

You have a conditional that chooses different behavior depending on the type of an object.  
_Move each leg of the conditional to an overriding method in a subclass. Make the original method abstract_

```java
	class Employee {
		private int _type;

		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		Employee (int type) {
			_type = type;
		}
		int payAmount() {
			switch (_type) {
				case ENGINEER:
					return _monthlySalary;
				case SALESMAN:
					return _monthlySalary + _commission;
				case MANAGER:
					return _monthlySalary + _bonus;
				default:
					throw new RuntimeException("Incorrect Employee");
				}
			}
		}
	}
```

to

```java
	class Employee...
		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		void setType(int arg) {
			_type = EmployeeType.newType(arg);
		}
		int payAmount() {
			return _type.payAmount(this);
		}
	}

	class Engineer...
		int payAmount(Employee emp) {
			return emp.getMonthlySalary();
		}
	}
```

**Motivation**

*   Avoid writing an explicit conditional when you have objects whose behavior varies depending on their types.
*   Switch statements should be less common in object oriented programs

39\. Introduce Null Object
--------------------------

[](#39-introduce-null-object)

You have repeated checks for a null value.  
_Replace the null value with a null object_

```java
	if (customer == null) plan = BillingPlan.basic();
	else plan = customer.getPlan();
```

to

```java
	class Customer {}

	class NullCusomer extends Customer {}
```

**Motivation**

*   The object, depending on its type, does the right thing. Null objects should also apply this rule.
*   Use **Null Object Pattern** is the little brother of **Special Case Pattern**.

A section of code assumes something about the state of the program.  
_Make the assumption explicit with an assertion_

```java
	double getExpenseLimit() {
		// should have either expense limit or a primary project
		return (_expenseLimit != NULL_EXPENSE) ?
			_expenseLimit:
			_primaryProject.getMemberExpenseLimit();
	}
```

to

```java
	double getExpenseLimit() {
		Assert.isTrue (_expenseLimit != NULL_EXPENSE || _primaryProject	!= null);
		return (_expenseLimit != NULL_EXPENSE) ?
			_expenseLimit:
			_primaryProject.getMemberExpenseLimit();
	}
```

**Motivation**

*   Assertions are conditional statements that are assumed to be always true.
*   Assertion failures should always result in unchecked exceptions.
*   Assertions usually are removed for production code.
*   As communication aids: they help the reader understand the assumptions the code is making.
*   As debugging aids: assertions can help catch bugs closer to their origin.

The name of a method does not reveal its purpose.  
_Change the name of the method_

to

```java
	getInvoiceableCreditLimit
```

**Motivation**  
Methods names must communicate their intention.

A method needs more information from its caller.  
_Add a parameter for an object that can pass on this information_

to

**Motivation**  
After changed a method you require more information.

A parameter is no longer used by the method body.  
_Remove it_

to

**Motivation**  
A parameter is no more needed.

44\. Separate Query from Modifier
---------------------------------

[](#44-separate-query-from-modifier)

You have a method that returns a value but also changes the state of an object.  
_Create two methods, one for the query and one for the modification_

```java
	getTotalOutStandingAndSetReadyForSummaries()
```

to

```java
	getTotalOutStanding()
	SetReadyForSummaries()
```

**Motivation**  
Signaling methods with side effects and those without.

Several methods do similar things but with different values contained in the method body.  
_Create one method that uses a parameter for the different values_

```java
	fivePercentRaise()
	tenPercentRaise()
```

to

**Motivation**  
Removes duplicate code and increases flexibility.

46\. Replace Parameter with Explicit Methods
--------------------------------------------

[](#46-replace-parameter-with-explicit-methods)

You have a method that runs different code depending on the values of an enumerated parameter.  
_Create a separate method for each value of the parameter_

```java
	void setValue (String name, int value) {
		if (name.equals("height")){}
			_height = value;
			return;
		}
		if (name.equals("width")){
			_width = value;
			return;
		}
		Assert.shouldNeverReachHere();
	}
```

to

```java
	void setHeight(int arg) {
		_height = arg;
	}
	void setWidth (int arg) {
		_width = arg;
	}
```

**Motivation**

*   Avoid the conditional behavior
*   Gain compile time checking
*   Clearer Interface

47\. Preserve Whole Object
--------------------------

[](#47-preserve-whole-object)

You are getting several values from an object and passing these values as parameters in a method call.  
_Send the whole object instead_

```java
	int low = daysTempRange().getLow();
	int high = daysTempRange().getHigh();
	withinPlan = plan.withinRange(low, high);
```

to

```java
	withinPlan = plan.withinRange(daysTempRange());
```

**Motivation**

*   Make parameters list robust to changes
*   Make code more readeable
*   Remove possible duplicate code already done in the object passed
*   Negative: It creates a dependency between the parameter object and the called.

48\. Replace Parameter with Method
----------------------------------

[](#48-replace-parameter-with-method)

An object invokes a method, then passes the result as a parameter for a method. The receiver can also invoke this method.  
_Remove the parameter and let the receiver invoke the method_

```java
	int basePrice = _quantity * _itemPrice;
	discountLevel = getDiscountLevel();
	double finalPrice = discountedPrice (basePrice, discountLevel);
```

to

```java
	int basePrice = _quantity * _itemPrice;
	double finalPrice = discountedPrice (basePrice);
```

**Motivation**

*   If a method can get a value that is passed in as parameter by another means, it should.
*   If the receiving method can make the same calculation (does not reference any of the parameters of the calling method)
*   If you are calling a method on a different object that has a reference to the calling object.

49\. Introduce Parameter Object
-------------------------------

[](#49-introduce-parameter-object)

You have a group of parameters that naturally go together.  
_Replace them with an object_

```java
	class Customer{
		amountInvoicedIn (start : Date, end : Date)
		amountReceivedIn (start : Date, end : Date)
		amountOverdueIn (start : Date, end : Date)
	}
```

to

```java
	class Customer{
		amountInvoicedIn (: DateRange)
		amountReceivedIn (: DateRange)
		amountOverdueIn (: DateRange)
	}
```

**Motivation**

*   Reduces the size of the parameter list
*   Make the code more consistent

50\. Remove Setting Method
--------------------------

[](#50-remove-setting-method)

A field should be set at creation time and never altered.  
_Remove any setting method for that field_

```java
	class Employee{
		setImmutableValue()
	}
```

to

```java
	class Employee{
		¯\_(ツ)_/¯
	}
```

**Motivation**  
Make your intention clear: If you don't want that field to change once is created, then don't provide a setting method (and make the field final).

A method is not used by any other class.  
_Make the method private_

```java
	class Employee{
		public method()
	}
```

to

```java
	class Employee{
		private method()
	}
```

**Motivation**  
Whenever a method is not needed outside its class it should be hidden

52\. Replace Constructor with Factory Method
--------------------------------------------

[](#52-replace-constructor-with-factory-method)

You want to do more than simple construction when you create an object.  
_Replace the constructor with a factory method_

```java
	Employee (int type) {
		_type = type;
	}
```

to

```java
	static Employee create(int type) {
		return new Employee(type);
	}
```

**Motivation**  
Create an object depending on its subclasses (types). Constructors can only return an instance of the object that is asked for so a Factory method is needed.

A method returns an object that needs to be downcasted by its callers.  
_Move the downcast to within the method_

```java
	Object lastReading() {
		return readings.lastElement();
	}
```

to

```java
	Reading lastReading() {
		return (Reading) readings.lastElement();
	}
```

**Motivation**  
Provide as result type, the most specific type of the method signature.  
If the signature is to general, check the uses the clients do of that method and if coherent, provide a more specific one.

54\. Replace Error Code with Exception
--------------------------------------

[](#54-replace-error-code-with-exception)

A method returns a special code to indicate an error.  
_Throw an exception instead_

```java
	int withdraw(int amount) {
		if (amount > _balance)
			return -1;
		else {
			_balance -= amount;
			return 0;
		}
	}
```

to

```java
	void withdraw(int amount) throws BalanceException {
		if (amount > _balance)
			throw new BalanceException();
		_balance -= amount;
	}
```

**Motivation** When a program that spots an error can't figure out what to do about it. It needs to let its caller know, and the caller may pass the error up the chain.

55\. Replace Exception with Test
--------------------------------

[](#55-replace-exception-with-test)

You are throwing a checked exception on a condition the caller could have checked first.  
_Change the caller to make the test first_

```java
	double getValueForPeriod (int periodNumber) {
		try {
			return _values[periodNumber];
		} catch (ArrayIndexOutOfBoundsException e) {
			return 0;
		}
	}
```

to

```java
	double getValueForPeriod (int periodNumber) {
		if (periodNumber >= _values.length)
			return 0;
		return _values[periodNumber];
}
```

**Motivation**

*   Do not overuse Exceptions they should be used for exceptional behavior (behavior that is unexpected).
*   Do not use them as substitute for conditional tests.
*   Check expected wrong conditions before before calling the operation.

Two subclasses have the same field.  
_Move the field to the superclass_

```java
	class Salesman extends Employee{
		String name;
	}
	class Engineer extends Employee{
		String name;
	}
```

to

```java
	class Employee{
		String name;
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

**Motivation**

*   Removes the duplicate data declaration.
*   Allows to move behavior from the subclasses to the superclass.

You have methods with identical results on subclasses.  
_Move them to the superclass_

```java
	class Salesman extends Employee{
		String getName();
	}
	class Engineer extends Employee{
		String getName();
	}
```

to

```java
	class Employee{
		String getName();
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

**Motivation**

*   Eliminates duplicated behavior.

58\. Pull Up Constructor Body
-----------------------------

[](#58-pull-up-constructor-body)

You have constructors on subclasses with mostly identical bodies.  
_Create a superclass constructor; call this from the subclass methods_

```java
	class Manager extends Employee...
		public Manager (String name, String id, int grade) {
		_name = name;
		_id = id;
		_grade = grade;
	}
```

to

```java
	public Manager (String name, String id, int grade) {
		super (name, id);
		_grade = grade;
	}
```

**Motivation**

*   Constructors are not the same as methods.
*   Eliminates duplicated behavior.

Behavior on a superclass is relevant only for some of its subclasses.  
_Move it to those subclasses._

```java
	class Employee{
		int getQuota();
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

to

```java
	class Salesman extends Employee{
		int getQuota();
	}
	class Engineer extends Employee{}
```

**Motivation** When a method makes only sense in the subclass.

A field is used only by some subclasses.  
_Move the field to those subclasses_

```java
	class Employee{
		int quota;
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

to

```java
	class Salesman extends Employee{
		int quota;
	}
	class Engineer extends Employee{}
```

**Motivation** When a field makes only sense in the subclass.

A class has features that are used only in some instances.  
_Create a subclass for that subset of features_

```java
	class JobItem	{
		getTotalPrices()
		getUnitPrice()
		getEmployee()
	}
```

to

```java
	JobItem	{
		getTotalPrices()
		getUnitPrice()
	}
	class class LabotItem extends JobItem	{
		getUnitPrice()
		getEmployee()
	}
```

**Motivation** When a class has behavior used for some instances of the class and not for others.

You have two classes with similar features.  
_Create a superclass and move the common features to the superclass_

```java
	class Department{
		getTotalAnnualCost()
		getName()
		getHeadCount
	}
	class Employee{
		getAnnualCost()
		getName()
		getId
	}
```

to

```java
	class Party{
		getAnnualCost()
		getName()
	}
	class Department {
		getAnnualCost()
		getHeadCount
	}
	class Employee {
		getAnnualCost()
		getId
	}
```

**Motivation** When two classes that do similar things in the same way or similar things in different ways.

Several clients use the same subset of a class's interface, or two classes have part of their interfaces in common.  
_Extract the subset into an interface_

```java
	class Employee {
		getRate()
		hasSpecialSkill()
		getName()
		getDepartment()
	}
```

to

```java
	interface Billable	{
		getRate()
		hasSpecialSkill()
	}
	class Employee implements Billable	{
		getRate
		hasSpecialSkill()
		getName()
		getDepartment()
	}
```

**Motivation**

*   If only a particular subset of a class's responsibilities is used by a group of clients.
*   If a class needs to work with any class that can handle certain requests.
*   Whenever a class has distinct roles in different situations.

A superclass and subclass are not very different.  
_Merge them together_

```java
	class Employee{	}
	class Salesman extends Employee{	}
```

to

**Motivation** When a subclass that isn't adding any value.

You have two methods in subclasses that perform similar steps in the same order, yet the steps are different. _Get the steps into methods with the same signature, so that the original methods become the same. Then you can pull them up_

```java
	class Site{}
	class ResidentialSite extends Site{
		getBillableAmount()
	}
	class LifelineSite extends Site{
		getBillableAmount()
	}
```

to

```java
	class Site{ 	
		getBillableAmount()
		getBaseAmount()
		getTaxAmount()
	}
	class ResidentialSite extends Site{
		getBaseAmount()
		getTaxAmount()
	}
	class LifelineSite extends Site{
		getBaseAmount()
		getTaxAmount()
	}
```

**Motivation**

*   Use Inheritance with polymorphism for eliminating duplicate behavior that is slightly different.
*   When there are two similar methods in a subclass, bring them together in a superclass.
*   [Template Method](https://www.wikiwand.com/en/Template_method_pattern)[\[Gang of Four\]](https://www.wikiwand.com/en/Design_Patterns)

66\. Replace Inheritance with Delegation
----------------------------------------

[](#66-replace-inheritance-with-delegation)

A subclass uses only part of a superclasses interface or does not want to inherit data.  
_Create a field for the superclass, adjust methods to delegate to the superclass, and remove the subclassing_

```java
	class Vector{
		isEmpty()
	}

	class Stack extends Vector {}
```

to

```java
	class Vector {
		isEmpty()
	}

	class Stack {
		Vector vector
		isEmpty(){
			return vector.isEmpty()
		}
	}
```

**Motivation**

*   Using delegation makes clear that you are making only partial use of the delegated class.
*   You control which aspects of the interface to take and which to ignore.

Mechanics

67\. Replace Delegation with Inheritance
----------------------------------------

[](#67-replace-delegation-with-inheritance)

You're using delegation and are often writing many simple delegations for the entire interface.  
_Make the delegating class a subclass of the delegate_

```java
	class Person {
		getName()
	}

	class Employee {
		Person person
		getName(){
			return person.getName()
		}
	}
```

to

```java
	class Person{
		getName()
	}
	class Employee extends Person{}
```

**Motivation**

*   If you are using all the methods of the delegate.
*   If you aren't using all the methods of the class to which you are delegating, you shouldn't use it.
*   Beware of is that in which the delegate is shared by more than one object and is mutable. Data sharing is a responsibility that cannot be transferred back to inheritance.

68\. Tease Apart Inheritance
----------------------------

[](#68-tease-apart-inheritance)

You have an inheritance hierarchy that is doing two jobs at once.  
_Create two hierarchies and use delegation to invoke one from the other_

```java
	class Deal{}
	class ActiveDeal extends Deal{}
	class PassiveDeal extends Deal{}
	class TabularActiveDeal extends ActiveDeal{}
	class TabularPassiveDeal extends PassiveDeal{}
```

to

```java
	class Deal{
		PresentationStyle presettationStyle;
	}
	class ActiveDeal extends Deal{}
	class PassiveDeal extends Deal{}

	class PresentationStyle{}
	class TabularPresentationStyle extends PresentationStyle{}
	class SinglePresentationStyle extends PresentationStyle{}
```

**Motivation**

*   Tangled inheritance leads to code duplication.
*   If every class at a certain level in the hierarchy has subclasses that begin with the same adjective, you probably are doing two jobs with one hierarchy.

**Mechanics Note**  
Identify the different jobs being done by the hierarchy. Create a two-dimensional(or x-dimensional) grid and label the axes with the different jobs.

| Deal | Active Deal | Passive Deal |
| --- | --- | --- |
| Tabular Deal |  |  |

69\. Convert Procedural Design to Objects
-----------------------------------------

[](#69-convert-procedural-design-to-objects)

You have code written in a procedural style.  
_Turn the data records into objects, break up the behavior, and move the behavior to the objects_

```java
	class OrderCalculator{
		determinePrice(Order)
		determineTaxes(Order)
	}
	class Order{}
	class OrderLine{}
```

to

```java
	class Order{
		getPrice()
		getTaxes()
	}
	class OrderLine{
		getPrice()
		getTaxes()
	}
```

**Motivation** Use OOP (at least in JAVA)

70\. Separate Domain from Presentation
--------------------------------------

[](#70-separate-domain-from-presentation)

You have GUI classes that contain domain logic.  
_Separate the domain logic into separate domain classes_

to

```java
	class OrderWindow{
		Order order;
}
```

**Motivation**

*   Separates two complicated parts of the program into pieces that are easier to modify.
*   Allows multiple presentations of the same business logic.
*   Its worth is proved

You have a class that is doing too much work, at least in part through many conditional statements.  
_Create a hierarchy of classes in which each subclass represents a special case_

to

```java
	class BillingScheme{}
	class BusinessBillingScheme extends BillingScheme{}
	class ResidentialBillingScheme extends BillingScheme{}
	class DisabilityBillingScheme extends BillingScheme{}
```

**Motivation**

*   A class as implementing one idea become implementing two or three or ten.
*   Keep the Single Responsibility Principle.
  
这是我对Martin Fowler的《重构：改进现有代码的设计》的总结。我在学习时使用它，并作为快速参考。它并不打算成为这本书的独立替代品，所以如果你真的想学习这里介绍的概念，请购买并阅读这本书，并将此存储库用作参考和指南。

  
如果你是发布者，并且认为这个仓库不应该公开，只要给我发一封电子邮件到hugomatilla \[at\] gmail \[dot\] com，我会把它变成私人的。

  
贡献：问题，评论和拉请求是超级受欢迎的。

1.内容表
=====

[](#1-table-of-content)

*   [1.内容表](#1-table-of-content)
*   [  
    3.代码中的难闻气味](#3-bad-smells-in-code)
    *   [1.重复代码](#1-duplicated-code)
    *   [2.长方法](#2-long-method)
    *   [3.大班](#3-large-classes)
    *   [4.长参数列表](#4-long-parameter-list)
    *   [5.分歧的变化](#5-divergent-change)
    *   [6.散弹枪手术](#6-shotgun-surgery)
    *   [7.功能羡慕](#7-feature-envy)
    *   [8.数据块](#8-data-clumps)
    *   [9.原始痴迷](#9-primitive-obsession)
    *   [10\. Switch语句](#10-switch-statements)
    *   [  
        11.并行继承层次](#11-parallel-inheritance-hierarchies)
    *   [12.懒惰的阶级](#12-lazy-class)
    *   [  
        13.投机性的普遍性](#13-speculative-generality)
    *   [14.临时外勤](#14-temporary-field)
    *   [15.消息间链](#15-message-chain)
    *   [16.中间人](#16-middle-man)
    *   [  
        17.不适当的亲密](#17-inappropriate-intimacy)
    *   [  
        18.具有不同接口的替代类](#18-alternative-classes-with-different-interfaces)
    *   [  
        19.不完整的库类](#19-incomplete-library-class)
    *   [20.数据类](#20-data-class)
    *   [21.拒绝遗赠](#21-refused-bequest)
    *   [22.评论](#22-comments)
*   [6.合成方法](#6-composing-methods)
    *   [1.提取方法](#1-extract-method)
    *   [2.内联方法](#2-inline-method)
    *   [3.在线温度](#3-inline-temp)
    *   [  
        4.将Temp替换为Query](#4-replace-temp-with-query)
    *   [  
        5.引入解释变量](#5-introduce-explaining-variable)
    *   [  
        6.拆分临时变量](#6-split-temporary-variable)
    *   [  
        7.删除参数](#7-remove-assignments-to-parameters)
    *   [  
        8.用方法对象替换方法](#8-replace-method-with-method-object)
    *   [9.替代算法](#9-substitute-algorithm)
*   [  
    7.在元素之间移动要素](#7-moving-features-between-elements)
    *   [10\. Move方法](#10-move-method)
    *   [11.搬场](#11-move-field)
    *   [12.提取类](#12-extract-class)
    *   [13.内联类](#13-inline-class)
    *   [14.隐藏委托](#14-hide-delegate)
    *   [15.删除中间人](#15-remove-middle-man)
    *   [  
        16.引进国外方法](#16-introduce-foreign-method)
    *   [  
        17.引入本地扩展](#17-introduce-local-extension)
*   [8.组织数据](#8-organizing-data)
    *   [  
        18.自封装字段](#18-self-encapsulate-field)
    *   [  
        19.将数据值替换为对象](#19-replace-data-value-with-object)
    *   [  
        20.将值更改为参考](#20-change-value-to-reference)
    *   [  
        21.更改对值的引用](#21-change-reference-to-value)
    *   [  
        22.将数组替换为对象](#22-replace-array-with-object)
    *   [  
        23.重复观察数据](#23-duplicate-observed-data)
    *   [  
        24.将单向关联更改为双向关联](#24-change-unidirectional-association-to-bidirectional)
    *   [  
        25.将双向关联更改为单向](#25-change-bidirectional-association-to-unidirectional)
    *   [  
        26.用符号常数代替幻数](#26-replace-magic-number-with-symbolic-constant)
    *   [27.封装字段](#27-encapsulate-field)
    *   [  
        28.封装集合](#28-encapsulate-collection)
    *   [  
        29.删除带有数据类的记录](#29-remove-record-with-data-class)
    *   [  
        30.将类型代码替换为类](#30-replace-type-code-with-class)
    *   [  
        31.用子类替换类型代码](#31-replace-type-code-with-subclasses)
    *   [  
        32.将类型代码替换为状态/策略](#32-replace-type-code-with-statestrategy)
    *   [  
        32.用字段替换子类](#32-replace-subclass-with-fields)
*   [  
    9.条件表达式的简化](#9-simplifying-conditional-expressions)
    *   [  
        33.分解条件](#33-decompose-conditional)
    *   [  
        34.合并条件表达式](#34-consolidate-conditional-expression)
    *   [  
        35.合并重复的条件片段](#35-consolidate-duplicate-conditional-fragments)
    *   [36.删除控制标志](#36-remove-control-flag)
    *   [  
        37.用Guard子句替换嵌套条件句](#37-replace-nested-conditional-with-guard-clauses)
    *   [  
        38.将条件替换为多态](#38-replace-conditional-with-polymorphism)
    *   [  
        39.介绍对象](#39-introduce-null-object)
    *   [40.介绍断言](#40-introduce-assertion)
*   [  
    10.让方法更简单](#10-making-method-calls-simpler)
    *   [41.反渗透法](#41-rename-method)
    *   [42.添加参数](#42-add-parameter)
    *   [43.删除参数](#43-remove-parameter)
    *   [  
        44.将查询与修改器分开](#44-separate-query-from-modifier)
    *   [45.参数化方法](#45-parameterize-method)
    *   [  
        46.用显式方法替换参数](#46-replace-parameter-with-explicit-methods)
    *   [  
        47.保留整个对象](#47-preserve-whole-object)
    *   [  
        48.将参数替换为方法](#48-replace-parameter-with-method)
    *   [  
        49.引入参数对象](#49-introduce-parameter-object)
    *   [  
        50.删除设置方法](#50-remove-setting-method)
    *   [51\. Hide方法](#51-hide-method)
    *   [  
        52.将构造函数替换为工厂方法](#52-replace-constructor-with-factory-method)
    *   [53.封装Downcast](#53-encapsulate-downcast)
    *   [  
        54.将错误代码替换为异常](#54-replace-error-code-with-exception)
    *   [  
        55.将异常替换为测试](#55-replace-exception-with-test)
*   [  
    11.处理泛化](#11-dealing-with-generalization)
    *   [56.上拉场](#56-pull-up-field)
    *   [57.上拉法](#57-pull-up-method)
    *   [  
        58.上拉构造器主体](#58-pull-up-constructor-body)
    *   [59.下推法](#59-push-down-method)
    *   [60.下推字段](#60-push-down-field)
    *   [61.提取子类](#61-extract-subclass)
    *   [62.提取超类](#62-extract-superclass)
    *   [63.提取接口](#63-extract-interface)
    *   [64.折叠层次结构](#64-collapse-hierarchy)
    *   [65.表单模板方法](#65-form-template-method)
    *   [  
        66.将继承替换为委托](#66-replace-inheritance-with-delegation)
    *   [  
        67.将委托替换为继承](#67-replace-delegation-with-inheritance)
*   [12.大重构](#12-big-refactorings)
    *   [  
        68.第1113章挑拨传承](#68-tease-apart-inheritance)
    *   [  
        69.将程序设计转换为对象](#69-convert-procedural-design-to-objects)
    *   [  
        70.将域与表示分离](#70-separate-domain-from-presentation)
    *   [71.提取层次结构](#71-extract-hierarchy)

  
3.代码中的难闻气味
=============

[](#3-bad-smells-in-code)

### 1.重复代码

[](#1-duplicated-code)

  
在多个地方有相同的代码结构。

### 2.长方法

[](#2-long-method)

  
程序越长，理解起来就越困难。

### 3.大班

[](#3-large-classes)

  
当一个类试图做太多的事情时，重复的代码不会太远。

### 4.长参数列表

[](#4-long-parameter-list)

  
它们难以理解，不一致，难以使用。

### 5.分歧的变化

[](#5-divergent-change)

  
当一个类通常由于不同的原因以不同的方式改变时。

### 6.散弹枪手术

[](#6-shotgun-surgery)

  
当你每次做一种改变时，你必须对很多不同的类做很多小的改变。

### 7.功能羡慕

[](#7-feature-envy)

  
一个方法似乎对一个类比它实际所在的类更感兴趣。

### 8.数据块

[](#8-data-clumps)

  
数据包（字段、参数等）一起玩的人

### 9.原始痴迷

[](#9-primitive-obsession)

  
使用基本类型而不是小对象。

### 10\. Switch语句

[](#10-switch-statements)

  
同样的switch语句分散在程序的不同地方。使用多态性。

###   
11.并行继承层次

[](#11-parallel-inheritance-hierarchies)

  
每当你创建一个类的子类时，你也必须创建另一个类的子类。

### 12.懒惰的阶级

[](#12-lazy-class)

  
一个没有做足够的工作来支付自己的班级应该被淘汰。

###   
13.投机性的普遍性

[](#13-speculative-generality)

  
各种各样的钩子和特殊的箱子来处理不需要的东西。

### 14.临时外勤

[](#14-temporary-field)

  
仅在某些情况下设置的实例变量。

### 15.消息间链

[](#15-message-chain)

  
当客户端向一个对象请求另一个对象时，客户端又向另一个对象请求...

### 16.中间人

[](#16-middle-man)

  
当一个对象委托了它的大部分功能时。

###   
17.不适当的亲密

[](#17-inappropriate-intimacy)

  
当一个类访问到另一个类的时候。

###   
18.具有不同接口的替代类

[](#18-alternative-classes-with-different-interfaces)

  
具有看起来相似的方法的类。

###   
19.不完整的库类

[](#19-incomplete-library-class)

  
当我们需要额外的功能在图书馆。

### 20.数据类

[](#20-data-class)

  
不允许在数据类中进行操作。使用封装和不变性。

### 21.拒绝遗赠

[](#21-refused-bequest)

  
不使用父方法的子类。

### 22.评论

[](#22-comments)

  
不是所有的注释，而是那些因为代码不好而出现的注释。

6.合成方法
======

[](#6-composing-methods)

1.提取方法
------

[](#1-extract-method)

  
你有一个可以组合在一起的代码片段。

```java
	void printOwing(double amount) {
		printBanner();
		//print details
		System.out.println ("name:" + _name);
		System.out.println ("amount" + amount);
	}
```

到

```java
	void printOwing(double amount) {
		printBanner();
		printDetails(amount);
	}

	void printDetails (double amount) {
		System.out.println ("name:" + _name);
	System.out.println ("amount" + amount);
	}
```

**动机**

*     
    增加了其他方法可以使用某个方法的机会
*     
    允许更高级别的方法更像是一系列注释

```java
	void printOwing(double previousAmount) {
		Enumeration e = _orders.elements();
		double outstanding = previousAmount * 1.2;
		printBanner();

		// calculate outstanding
		while (e.hasMoreElements()) {
			Order each = (Order) e.nextElement();
			outstanding += each.getAmount();
		}
		printDetails(outstanding);
	}
```

到

```java
	void printOwing(double previousAmount) {
		printBanner();
		double outstanding = getOutstanding(previousAmount * 1.2);
		printDetails(outstanding);
	}

	double getOutstanding(double initialValue) {
		double result = initialValue;
		Enumeration e = _orders.elements();

		while (e.hasMoreElements()) {
			Order each = (Order) e.nextElement();
			result += each.getAmount();
		}
		return result;
	}
```

2.内联方法
------

[](#2-inline-method)

  
方法的主体和它的名字一样清楚。

```java
	int getRating() {
		return (moreThanFiveLateDeliveries()) ? 2 : 1;
	}

	boolean moreThanFiveLateDeliveries() {
		return _numberOfLateDeliveries > 5;
	}
```

到

```java
	int getRating() {
		return (_numberOfLateDeliveries > 5) ? 2 : 1;
	}
```

**动机**

*     
    当间接是不必要的（简单的委托）变得令人恼火。
*     
    如果一组方法分解得不好，那么将它们分组会更清楚

3.在线温度
------

[](#3-inline-temp)

  
你有一个临时变量，它被一个简单的表达式赋值一次，这个临时变量妨碍了其他的重构。

```java
	double basePrice = anOrder.basePrice();
	return (basePrice > 1000)
```

到

```java
	return (anOrder.basePrice() > 1000)
```

**动机**

*     
    使用它[4。将Temp替换为Query](#4-replace-temp-with-query)

  
4.将Temp替换为Query
------------------

[](#4-replace-temp-with-query)

  
您正在使用临时变量来保存表达式的结果。

```java
	double basePrice = _quantity * _itemPrice;
	if (basePrice > 1000)
		return basePrice * 0.95;
	else
		return basePrice * 0.98;
```

到

```java
	if (basePrice() > 1000)
		return basePrice() * 0.95;
	else
		return basePrice() * 0.98;
	...
	double basePrice() {
		return _quantity * _itemPrice;
	}
```

**动机**

*     
    用一个查询方法代替临时变量，类中的任何方法都可以获取信息。
*     
    是一个重要的步骤之前[1。提取方法](#1-extract-method)

  
5.引入解释变量
-----------

[](#5-introduce-explaining-variable)

  
你的表情很复杂

```java
	if ( (platform.toUpperCase().indexOf("MAC") > -1) &&
		(browser.toUpperCase().indexOf("IE") > -1) &&
		wasInitialized() && resize > 0 )
	{
		// do something
	}
```

到

```java
	final boolean isMacOs = platform.toUpperCase().indexOf("MAC") >-1;
	final boolean isIEBrowser = browser.toUpperCase().indexOf("IE") >-1;
	final boolean wasResized = resize > 0;
	if (isMacOs && isIEBrowser && wasInitialized() && wasResized) {
		// do something
	}
```

**动机**

*     
    当表情难以理解时

  
6.拆分临时变量
-----------

[](#6-split-temporary-variable)

  
你有一个临时变量被赋了不止一次，但它不是一个循环变量，也不是一个收集临时变量。

```java
	double temp = 2 * (_height + _width);
	System.out.println (temp);
	temp = _height * _width;
	System.out.println (temp);
```

到

```java
	final double perimeter = 2 * (_height + _width);
	System.out.println (perimeter);
	final double area = _height * _width;
	System.out.println (area);
```

**动机**

*     
    变量不应该有一个以上的责任。
*     
    对于读者来说，使用一个临时变量来做两件不同的事情是非常令人困惑的。

  
7.删除参数
---------

[](#7-remove-assignments-to-parameters)

  
赋给参数的代码

```java
	int discount (int inputVal, int quantity, int yearToDate) {
		if (inputVal > 50) inputVal -= 2;
```

到

```java
	int discount (int inputVal, int quantity, int yearToDate) {
		int result = inputVal;
		if (inputVal > 50) result -= 2;
```

**动机**

*     
    你可以改变对象的内部结构，但不能指向另一个对象.
*     
    仅使用参数来表示已传递的内容。

  
8.用方法对象替换方法
--------------

[](#8-replace-method-with-method-object)

  
您有一个长方法，它使用局部变量的方式使您无法应用Extract Method。

```java
	class Order...
		double price() {
			double primaryBasePrice;
			double secondaryBasePrice;
			double tertiaryBasePrice;
			// long computation;
			...
		}
```

到

```java
	class Order...
		double price(){
			return new PriceCalculator(this).compute()
		}
	}

	class PriceCalculato...
	compute(){
		double primaryBasePrice;
		double secondaryBasePrice;
		double tertiaryBasePrice;
		// long computation;
		return ...
	}
```

**动机**

*     
    当一个方法有很多局部变量并且不可能应用分解时

_  
此示例并不真正需要这种重构，但显示了实现这种重构的方法。_

```java
	Class Account
		int gamma (int inputVal, int quantity, int yearToDate) {
			int importantValue1 = (inputVal * quantity) + delta();
			int importantValue2 = (inputVal * yearToDate) + 100;
			if ((yearToDate - importantValue1) > 100)
			importantValue2 -= 20;
			int importantValue3 = importantValue2 * 7;
			// and so on.
			return importantValue3 - 2 * importantValue1;
		}
	}
```

到

```java
	class Gamma...
		private final Account _account;
		private int inputVal;
		private int quantity;
		private int yearToDate;
		private int importantValue1;
		private int importantValue2;
		private int importantValue3;

		Gamma (Account source, int inputValArg, int quantityArg, int yearToDateArg) {
			_account = source;
			inputVal = inputValArg;
			quantity = quantityArg;
			yearToDate = yearToDateArg;
		}

		int compute () {
			importantValue1 = (inputVal * quantity) + _account.delta();
			importantValue2 = (inputVal * yearToDate) + 100;
			if ((yearToDate - importantValue1) > 100)
			importantValue2 -= 20;
			int importantValue3 = importantValue2 * 7;
			// and so on.
			return importantValue3 - 2 * importantValue1;
		}

		int gamma (int inputVal, int quantity, int yearToDate) {
			return new Gamma(this, inputVal, quantity,yearToDate).compute();
		}
```

9.替代算法
------

[](#9-substitute-algorithm)

  
你想用一个更清晰的算法来代替一个算法。

```java
	String foundPerson(String[] people){
		for (int i = 0; i < people.length; i++) {
			if (people[i].equals ("Don")){
				return "Don";
			}
			if (people[i].equals ("John")){
				return "John";
			}
			if (people[i].equals ("Kent")){
				return "Kent";
			}
		}
		return "";
	}
```

到

```java
	String foundPerson(String[] people){
		List candidates = Arrays.asList(new String[] {"Don", "John","Kent"});
	for (int i = 0; i<people.length; i++)
		if (candidates.contains(people[i]))
			return people[i];
	return "";
	}
```

**动机**

*     
    把复杂的东西分解成简单的部分。
*     
    更容易将更改应用于算法。
*     
    替换一个大的、复杂的算法是非常困难的;使其简单可以使替换易于处理。

  
7.在元素之间移动要素
==============

[](#7-moving-features-between-elements)

10\. Move方法
-----------

[](#10-move-method)

  
一个方法正在或将要使用另一个类的更多特性，或者被另一个类的更多特性使用。

_  
创建一个新方法，在它最常用的类中使用类似的主体。要么将旧方法转换为简单的委托，要么将其完全删除。_

```java
	class Class1 {
		aMethod()
	}

	class Class2 {	}
```

到

```java
	class Class1 {	}

	class Class2 {
		aMethod()
	}
```

**动机**

  
当类做太多的工作或者协作太多并且高度耦合时

11.搬场
-----

[](#11-move-field)

  
一个字段现在或将要被另一个类使用，而不是被定义它的类使用。_在目标类中创建一个新字段，并更改其所有用户。_

```java
	class Class1 {
		aField
	}

	class Class2 {	}
```

到

```java
	class Class1 {	}

	class Class2 {
		aField
	}
```

**动机**

  
如果一个字段主要由外部类和12之前的类使用[。提取类](#12-extract-class)

12.提取类
------

[](#12-extract-class)

  
你让一个类做应该由两个类完成的工作。_创建一个新类，并将相关的字段和方法从旧类移动到新类中。_

```java
	class Person {
		name,
		officeAreaCode,
		officeNumber,
		getTelephoneNumber()
	}
```

到

```java
	class Person {
		name,
		getTelephoneNumber()
	}

	class TelephoneNumber {
		areaCode,
		number,
		getTelephoneNumber()
	}
```

**动机**

  
班级成长。_在以下情况下拆分它们_：

*     
    方法的子集似乎在一起
*     
    数据的子集通常一起变化或相互依赖

13.内联类
------

[](#13-inline-class)

  
一门课没有什么用。_将其所有特征移到另一个类中并删除它。_

```java
	class Person {
		name,
		getTelephoneNumber()
	}

	class TelephoneNumber {
		areaCode,
		number,
		getTelephoneNumber()
	}
```

到

```java
	class Person {
		name,
		officeAreaCode,
		officeNumber,
		getTelephoneNumber()
	}
```

**动机**

  
在重构之后，通常会有一堆责任被移出类，让类所剩无几。

14.隐藏委托
-------

[](#14-hide-delegate)

  
客户端正在调用对象的委托类。  
_  
在服务器上创建方法以隐藏委托。_

```java
	class ClientClass {
		//Dependencies
		Person person = new Person()
		Department department = new Department()
		person.doSomething()
		department.doSomething()
	}
```

到

```java
	class ClientClass {
		Person person = new Person()
		person.doSomething()
	}

	class Person{
		Department department = new Department()
		department.doSomething()
	}
```

_溶液_

```java
	class ClientClass{
		Server server = new Server()
		server.doSomething()
	}

	class Server{
		Delegate delegate = new Delegate()
		void doSomething(){
			delegate.doSomething()
		}
	}
	// The delegate is hidden to the client class.
	// Changes won't be propagated to the client they will only affect the server
	class Delegate{
		void doSomething(){...}
	}
```

**动机**

  
封装的关键。类应该尽可能少地了解其他类。

`> manager = john.getDepartment().getManager();`

```java
	class Person {
		Department _department;
		public Department getDepartment() {
			return _department;
		}
		public void setDepartment(Department arg) {
			_department = arg;
			}
		}

	class Department {
		private String _chargeCode;
		private Person _manager;
		public Department (Person manager) {
			_manager = manager;
		}
		public Person getManager() {
			return _manager;
		}
		...
```

到

`> manager = john.getManager();`

```java
	class Person {
		...
		public Person getManager() {
			return _department.getManager();
		}
	}
```

15.删除中间人
--------

[](#15-remove-middle-man)

  
一个类做了太多简单的委托。_让客户端直接调用委托。_

```java
	class ClientClass {
		Person person = new Person()
		person.doSomething()
	}

	class Person{
		Department department = new Department()
		department.doSomething()
	}
```

到

```java
	class ClientClass {
		//Dependencies
		Person person = new Person()
		Department department = new Department()
		person.doSomething()
		department.doSomething()
	}
```

**动机**

  
当“中间人”（服务器）做得太多时，客户端就有时间直接调用委托。

  
16.引进国外方法
------------

[](#16-introduce-foreign-method)

  
您正在使用的服务器类需要一个额外的方法，但您不能修改该类。  
_  
在客户端类中创建一个方法，并将服务器类的实例作为其第一个参数。_

```java
	Date newStart = new Date(previousEnd.getYear(),previousEnd.getMonth(),previousEnd.getDate()+1);
```

到

```java
	Date newStart = nextDay(previousEnd);

	private static Date nextDay(Date date){
		return new Date(date.getYear(),date.getMonth(),date.getDate()+1);
	}
```

**动机**

  
当类中缺少您经常使用的方法并且无法更改该类时。

  
17.引入本地扩展
------------

[](#17-introduce-local-extension)

  
您正在使用的服务器类需要几个额外的方法，但您不能修改该类。_创建一个包含这些额外方法的新类。使此扩展类成为原始扩展类的子类或包装器。_

```java
	class ClientClass(){

		Date date = new Date()
		nextDate = nextDay(date);

		private static Date nextDay(Date date){
			return new Date(date.getYear(),date.getMonth(),date.getDate()+1);
		}
	}
```

到

```java
	class ClientClass() {
		MfDate date = new MfDate()
		nextDate = nextDate(date)
	}
	class MfDate() extends Date {
		...
		private static Date nextDay(Date date){
			return new Date(date.getYear(),date.getMonth(),date.getDate()+1);
		}
	}
```

**动机**

  
当很多16。[需要将Introduce Foreign Method添加到类中。](#16-introduce-foreign-method)

8.组织数据
======

[](#8-organizing-data)

  
18.自封装字段
-----------

[](#18-self-encapsulate-field)

  
您正在直接访问一个字段，但是与字段的耦合变得很笨拙。  
_  
为字段创建获取和设置方法，并仅使用这些方法访问字段。_

```java
	private int _low, _high;
	boolean includes (int arg) {
		return arg >= _low && arg <= _high;
	}
```

到

```java
	private int _low, _high;
	boolean includes (int arg) {
		return arg >= getLow() && arg <= getHigh();
	}
	int getLow() {return _low;}
	int getHigh() {return _high;}
```

**动机**  
  
允许子类重写如何使用方法获取信息，并且它支持更灵活的数据管理，例如延迟初始化。

  
19.将数据值替换为对象
---------------

[](#19-replace-data-value-with-object)

  
您有一个数据项需要附加数据或行为。  
_  
将数据项转换为对象_

```java
	class Order...{
		private String _customer;
		public Order (String customer) {
			_customer = customer;
		}
	}
```

到

```java
	class Order...{
		public Order (String customer) {
			_customer = new Customer(customer);
		}
	}

	class Customer {
		public Customer (String name) {
			_name = name;
		}
	}
```

**动机**  
  
简单的数据项不再那么简单。

  
20.将值更改为参考
-------------

[](#20-change-value-to-reference)

  
你有一个类，它有许多相等的实例，你想用一个对象替换它们。  
_  
将对象转换为参考对象。_

```java
	class Order...{
		public Order (String customer) {
			_customer = new Customer(customer);
		}
	}

	class Customer {
		public Customer (String name) {
			_name = name;
		}
	}
```

到

```java
	//Use Factory Method
	class Customer...
		static void loadCustomers() {
			new Customer ("Lemon Car Hire").store();
			new Customer ("Associated Coffee Machines").store();
			new Customer ("Bilston Gasworks").store();
		}
		private void store() {
			_instances.put(this.getName(), this);
		}
		public static Customer create (String name) {
			return (Customer) _instances.get(name);
		}
```

**动机**  
  
引用对象是客户或帐户之类的东西。每个对象代表真实的世界中的一个对象，您使用对象标识来测试它们是否相等。

  
21.更改对值的引用
-------------

[](#21-change-reference-to-value)

  
您有一个引用对象，它很小，不可变，并且难以管理。  
_  
把它变成一个价值对象_

```java
	new Currency("USD").equals(new Currency("USD")) // returns false
```

到

```java
	
	// Add `equals` and `hashCode` to the Currency class 
	class Currency{ 
		...
		public boolean equals(Object arg) {
	 		if (! (arg instanceof Currency)) return false;
	 		Currency other = (Currency) arg;
			return (_code.equals(other._code));
		}

		public int hashCode() {
 			return _code.hashCode();
 		}
 	}

 	// Now you can do
	new Currency("USD").equals(new Currency("USD")) // now returns true
```

**动机**  
  
使用引用对象变得很笨拙。引用对象是不可变的，并且很小。用于分布式或并发系统。

  
22.将数组替换为对象
--------------

[](#22-replace-array-with-object)

  
你有一个数组，其中某些元素意味着不同的东西。  
_  
将数组替换为每个元素都有一个字段的对象_

```java
	String[] row = new String[3];
	row [0] = "Liverpool";
	row [1] = "15";
```

到

```java
	Performance row = new Performance();
	row.setName("Liverpool");
	row.setWins("15");
```

**动机**  
  
数组只应用于包含按某种顺序排列的类似对象的集合。

  
23.重复观察数据
------------

[](#23-duplicate-observed-data)

  
域数据仅在GUI控件中可用，并且域方法需要访问。  
_  
将数据复制到域对象。设置一个观察者来同步这两个数据_  
**动机**  
  
将处理用户界面的代码与处理业务逻辑的代码分开。

  
24.将单向关联更改为双向关联
------------------

[](#24-change-unidirectional-association-to-bidirectional)

  
您有两个类，它们需要使用彼此的特性，但只有一个单向链接。  
_  
添加返回指针，并更改修饰符以更新两个集合_

```java
	class Order...
		Customer getCustomer() {
			return _customer;
		}
		void setCustomer (Customer arg) {
			_customer = arg;
		}
		Customer _customer;
	}
```

到

```java
	class Order...
		Customer getCustomer() {
			return _customer;
		}
		void setCustomer (Customer arg) {
			if (_customer != null) _customer.friendOrders().remove(this);
			_customer = arg;
			if (_customer != null) _customer.friendOrders().add(this);
		}
		private Customer _customer;

		class Customer...
			void addOrder(Order arg) {
				arg.setCustomer(this);
			}
			private Set _orders = new HashSet();

			Set friendOrders() {
				/** should only be used by Order */
				return _orders;
			}
		}
	}

	// Many to Many
	class Order... //controlling methods
		void addCustomer (Customer arg) {
			arg.friendOrders().add(this);
			_customers.add(arg);
		}
		void removeCustomer (Customer arg) {
			arg.friendOrders().remove(this);
			_customers.remove(arg);
		}
	class Customer...
		void addOrder(Order arg) {
			arg.addCustomer(this);
		}
		void removeOrder(Order arg) {
			arg.removeCustomer(this);
		}
	}
```

**动机**  
  
当引用的对象需要访问引用它的对象时。

  
25.将双向关联更改为单向
----------------

[](#25-change-bidirectional-association-to-unidirectional)

  
你有一个双向关联，但是一个类不再需要另一个类的功能。  
_  
删除不需要的关联端_  
**动机**  
  
如果不需要双向关联，则降低复杂性，处理僵尸对象，消除相互依赖性

  
26.用符号常数代替幻数
---------------

[](#26-replace-magic-number-with-symbolic-constant)

  
你有一个字面上的数字，有一个特定的含义。  
_  
创建一个常数，根据含义命名，并用它替换数字_

```java
	double potentialEnergy(double mass, double height) {
		return mass * 9.81 * height;
	}
```

到

```java
	double potentialEnergy(double mass, double height) {
		return mass * GRAVITATIONAL_CONSTANT * height;
	}
	static final double GRAVITATIONAL_CONSTANT = 9.81;
```

**动机**  
  
避免使用魔法数字。

27.封装字段
-------

[](#27-encapsulate-field)

  
有一个公共领域。  
_  
将其设为私有并提供访问器_

```java
	public String _name
```

到

```java
	private String _name;
	public String getName() {return _name;}
	public void setName(String arg) {_name = arg;}
```

**动机**  
  
你永远不应该公开你的数据。

  
28.封装集合
----------

[](#28-encapsulate-collection)

  
方法返回一个集合。  
_  
使其返回只读视图并提供添加/删除方法_

```java
	class Person {
		Person (String name){
			HashSet set new HashSet()
		}
		Set getCourses(){}
		void setCourses(:Set){}
	}
```

到

```java
	class Person {
		Person (String name){
			HashSet set new HashSet()
		}
		Unmodifiable Set getCourses(){}
		void addCourses(:Course){}
		void removeCourses(:Course){}
	}
```

**动机**

*     
    封装减少了所属类与其客户端的耦合。
*     
    getter不应该返回集合对象本身。
*     
    getter应该返回一些防止操作集合和隐藏不必要的细节的东西。
*     
    集合不应该有setter，只有添加和删除元素的操作。

  
29.删除带有数据类的记录
----------------

[](#29-remove-record-with-data-class)

  
在传统的编程环境中，您需要与记录结构进行交互。  
_  
为记录创建一个哑数据对象。_

**动机**

*   美国国家航空航天局遗产计划
*     
    与传统编程API或数据库通信结构化记录。

  
30.将类型代码替换为类
---------------

[](#30-replace-type-code-with-class)

  
类具有不影响其行为的数字类型代码。  
_  
用一个新的类替换这个数字。_

```java
	class Person{
		O:Int;
		A:Int;
		B:Int;
		AB:Int;
		bloodGroup:Int;
	}
```

到

```java
	class Person{
		bloodGroup:BloodGroup;
	}

	class BloodGroup{
		O:BloodGroup;
		A:BloodGroup;
		B:BloodGroup;
		AB:BloodGroup;
	}
```

**动机**  
  
静态类型检查。

  
31.用子类替换类型代码
---------------

[](#31-replace-type-code-with-subclasses)

  
你有一个影响类行为的不可变类型代码。  
_  
用子类替换类型代码。_

```java
	class Employee...
		private int _type;

		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		Employee (int type) {
			_type = type;
		}
	}
```

到

```java
	abstract int getType();
	static Employee create(int type) {
		switch (type) {
			case ENGINEER:
				return new Engineer();
			case SALESMAN:
				return new Salesman();
			case MANAGER:
				return new Manager();
			default:
				throw new IllegalArgumentException("Incorrect type code value");
		}
	}
```

**动机**

*     
    根据类型的值执行不同的代码。
*     
    当每种类型的代码对象具有独特的功能。
*     
    第[38章.将条件替换为多态](#38-replace-conditional-with-polymorphism)
*     
    使用[30。将类型代码替换为类](#30-replace-type-code-with-class)

  
32.将类型代码替换为状态/策略
-------------------

[](#32-replace-type-code-with-statestrategy)

  
你有一个影响类行为的类型代码，但你不能使用子类化。  
_  
用状态对象替换类型代码_

```java
	class Employee {
		private int _type;

		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		Employee (int type) {
			_type = type;
		}
		int payAmount() {
			switch (_type) {
				case ENGINEER:
					return _monthlySalary;
				case SALESMAN:
					return _monthlySalary + _commission;
				case MANAGER:
					return _monthlySalary + _bonus;
				default:
					throw new RuntimeException("Incorrect Employee");
				}
			}
		}
	}
```

到

```java
	class Employee...
		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		void setType(int arg) {
			_type = EmployeeType.newType(arg);
		}
		class EmployeeType...
			static EmployeeType newType(int code) {
				switch (code) {
					case ENGINEER:
						return new Engineer();
					case SALESMAN:
						return new Salesman();
					case MANAGER:
						return new Manager();
					default:
						throw new IllegalArgumentException("Incorrect Employee Code");
				}
			}
		}
		int payAmount() {
			switch (getType()) {
				case EmployeeType.ENGINEER:
					return _monthlySalary;
				case EmployeeType.SALESMAN:
					return _monthlySalary + _commission;
				case EmployeeType.MANAGER:
					return _monthlySalary + _bonus;
				default:
					throw new RuntimeException("Incorrect Employee");
			}
		}
	}
```

**动机**

*     
    类似于[31。将类型代码替换为子类](#31-replace-type-code-with-subclasses)，但如果类型代码在对象的生命周期内发生更改，或者由于其他原因阻止子类化，则可以使用此选项。
*     
    它使用状态模式或策略模式

  
32.用字段替换子类
-------------

[](#32-replace-subclass-with-fields)

  
你有一些子类，它们只在返回常量数据的方法上有所不同。  
_  
将方法更改为超类字段并删除子类_

```java
	abstract class Person {
		abstract boolean isMale();
		abstract char getCode();
		...
	}
	class Male extends Person {
			boolean isMale() {
			return true;
		}
		char getCode() {
			return 'M';
		}
	}
	class Female extends Person {
		boolean isMale() {
			return false;
		}
		char getCode() {
			return 'F';
		}
	}
```

到

```java
	class Person{
		protected Person (boolean isMale, char code) {
			_isMale = isMale;
			_code = code;
		}
		boolean isMale() {
			return _isMale;
		}
		static Person createMale(){
			return new Person(true, 'M');
		}
		static Person createFemale(){
			return new Person(false, 'F');
		}
	}
```

**动机**

*     
    仅由常量方法组成的子类不值得存在。
*     
    通过在超类中放置字段来完全删除此类子类。
*     
    删除子类的额外复杂性。

  
9.条件表达式的简化
=============

[](#9-simplifying-conditional-expressions)

  
33.分解条件
----------

[](#33-decompose-conditional)

  
你有一个复杂的条件（if-then-else）语句。  
_  
从条件中提取方法，然后提取part，然后提取else part_

```java
	if (date.before (SUMMER_START) || date.after(SUMMER_END))
		charge = quantity * _winterRate + _winterServiceCharge;
	else charge = quantity * _summerRate;
```

到

```java
	if (notSummer(date))
		charge = winterCharge(quantity);
	else charge = summerCharge (quantity);
```

**动机**

*     
    突出显示条件，并清楚地表明你要分支的内容。
*     
    突出显示分支的原因

  
34.合并条件表达式
-------------

[](#34-consolidate-conditional-expression)

  
你有一个条件测试序列，结果相同。  
_  
将它们联合收割机组合成单个条件表达式并提取它_

```java
	double disabilityAmount() {
	if (_seniority < 2) return 0;
	if (_monthsDisabled > 12) return 0;
	if (_isPartTime) return 0;
	// compute the disability amount
```

到

```java
	double disabilityAmount() {
	if (isNotEligableForDisability()) return 0;
	// compute the disability amount
```

**动机**

*     
    通过显示您实际上正在进行一次检查来使检查更清晰
*     
    为您设置[1。提取方法](#1-extract-method)。
*     
    澄清你的代码（用你为什么要做的事情来代替你正在做的事情的陈述）。

  
35.合并重复的条件片段
---------------

[](#35-consolidate-duplicate-conditional-fragments)

  
条件表达式的所有分支中都存在相同的代码片段。  
_  
把它移到表达式外面。_

```java
	if (isSpecialDeal()) {
		total = price * 0.95;
		send();
	}
	else {
		total = price * 0.98;
		send();
	}
```

到

```java
	if (isSpecialDeal()) {
		total = price * 0.95;
	}
	else {
		total = price * 0.98;
	}
	send();
```

**动机**  
  
更清楚地表明了什么是变化的，什么是不变的。

36.删除控制标志
---------

[](#36-remove-control-flag)

  
您有一个变量，它充当一系列布尔表达式的控制标志。  
_  
使用break或return代替_

```java
	void checkSecurity(String[] people) {
		boolean found = false;
			for (int i = 0; i < people.length; i++) {
				if (! found) {
					if (people[i].equals ("Don")){
						sendAlert();
						found = true;
					}
					if (people[i].equals ("John")){
						sendAlert();
						found = true;
					}
				}
		}
	}
```

到

```java
	void checkSecurity(String[] people) {
		for (int i = 0; i < people.length; i++) {
			if (people[i].equals ("Don")){
				sendAlert();
				break; // or return
			}
			if (people[i].equals ("John")){
				sendAlert();
				break; // or return
			}
		}
	}
```

**动机**

*     
    控制标志用于确定何时停止查找，但现代语言强制使用`中断`和`继续`
*     
    使条件句的真实的目的更加清楚。

  
37.用Guard子句替换嵌套条件句
---------------------

[](#37-replace-nested-conditional-with-guard-clauses)

  
方法具有条件行为，该行为不明确正常的执行路径。  
_  
对所有特殊情况使用保护条款_

```java
	double getPayAmount() {
		double result;
		if (_isDead) result = deadAmount();
		else {
			if (_isSeparated) result = separatedAmount();
			else {
				if (_isRetired) result = retiredAmount();
				else result = normalPayAmount();
			};
		}
		return result;
	};
```

到

```java
	double getPayAmount() {
		if (_isDead) return deadAmount();
		if (_isSeparated) return separatedAmount();
		if (_isRetired) return retiredAmount();
		return normalPayAmount();
	};
```

**动机**

*     
    如果条件是异常条件，则检查条件，如果条件为真，则返回。
*     
    这种检查通常被称为**保护条款**\[贝克\]。
*     
    如果你使用的是if-then-else结构，那么你就给了if分支和else分支相等的权重。
*     
    这告诉读者，腿也同样重要。
*     
    相反，**保护条款**说，_“这是罕见的，如果发生了，做点什么，然后离开。"_

  
38.将条件替换为多态
--------------

[](#38-replace-conditional-with-polymorphism)

  
你有一个条件，它根据对象的类型选择不同的行为。  
_  
将条件的每个分支移动到子类中的重写方法。使原始方法抽象化_

```java
	class Employee {
		private int _type;

		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		Employee (int type) {
			_type = type;
		}
		int payAmount() {
			switch (_type) {
				case ENGINEER:
					return _monthlySalary;
				case SALESMAN:
					return _monthlySalary + _commission;
				case MANAGER:
					return _monthlySalary + _bonus;
				default:
					throw new RuntimeException("Incorrect Employee");
				}
			}
		}
	}
```

到

```java
	class Employee...
		static final int ENGINEER = 0;
		static final int SALESMAN = 1;
		static final int MANAGER = 2;

		void setType(int arg) {
			_type = EmployeeType.newType(arg);
		}
		int payAmount() {
			return _type.payAmount(this);
		}
	}

	class Engineer...
		int payAmount(Employee emp) {
			return emp.getMonthlySalary();
		}
	}
```

**动机**

*     
    当对象的行为随其类型而变化时，避免编写显式条件。
*     
    Switch语句在面向对象的程序中应该不太常见

  
39.介绍对象
----------

[](#39-introduce-null-object)

  
您已重复检查空值。  
_  
将空值替换为空对象_

```java
	if (customer == null) plan = BillingPlan.basic();
	else plan = customer.getPlan();
```

到

```java
	class Customer {}

	class NullCusomer extends Customer {}
```

**动机**

*     
    对象根据其类型做正确的事情。对象也应该应用此规则。
*     
    Use**Object Pattern**是**Special Case Pattern**的小兄弟。

40.介绍断言
-------

[](#40-introduce-assertion)

  
一段代码假定了程序的某些状态。  
_  
用断言来明确假设_

```java
	double getExpenseLimit() {
		// should have either expense limit or a primary project
		return (_expenseLimit != NULL_EXPENSE) ?
			_expenseLimit:
			_primaryProject.getMemberExpenseLimit();
	}
```

到

```java
	double getExpenseLimit() {
		Assert.isTrue (_expenseLimit != NULL_EXPENSE || _primaryProject	!= null);
		return (_expenseLimit != NULL_EXPENSE) ?
			_expenseLimit:
			_primaryProject.getMemberExpenseLimit();
	}
```

**动机**

*     
    断言是被假定为总是真的条件语句。
*     
    断言失败总是会导致未检查的异常。
*     
    断言通常在生产代码中被删除。
*     
    作为交流的辅助工具：它们帮助读者理解代码所做的假设。
*     
    作为调试辅助工具：断言可以帮助捕获更接近其起源的错误。

  
10.让方法更简单
============

[](#10-making-method-calls-simpler)

41.反渗透法
-------

[](#41-rename-method)

  
一个方法的名称并不能说明它的用途。  
_  
更改方法的名称_

```java
	getinvcdtlmt()
```

到

```java
	getInvoiceableCreditLimit
```

**动机**  
  
方法名称必须传达它们的意图。

42.添加参数
-------

[](#42-add-parameter)

  
方法需要来自其调用方的更多信息。  
_  
为可以传递此信息的对象添加参数_

```java
	getContact()
```

到

```java
	getContact(:Date)
```

**动机**  
  
改变方法后，您需要更多信息。

43.删除参数
-------

[](#43-remove-parameter)

  
方法体不再使用参数。  
_删除它_

```java
	getContact(:Date)
```

到

```java
	getContact()
```

**动机**  
  
不再需要参数。

  
44.将查询与修改器分开
---------------

[](#44-separate-query-from-modifier)

  
你有一个方法，它返回一个值，但也改变了对象的状态。  
_  
创建两个方法，一个用于查询，一个用于修改_

```java
	getTotalOutStandingAndSetReadyForSummaries()
```

到

```java
	getTotalOutStanding()
	SetReadyForSummaries()
```

**动机**  
  
有副作用和没有副作用的信号方法。

45.参数化方法
--------

[](#45-parameterize-method)

  
几个方法做类似的事情，但在方法体中包含不同的值。  
_  
创建一个方法，该方法使用参数表示不同的值_

```java
	fivePercentRaise()
	tenPercentRaise()
```

到

```java
	raise(percentage)
```

**动机**  
  
避免重复代码并增加灵活性。

  
46.用显式方法替换参数
---------------

[](#46-replace-parameter-with-explicit-methods)

  
您有一个方法，它根据枚举参数的值运行不同的代码。  
_  
为参数的每个值创建单独的方法_

```java
	void setValue (String name, int value) {
		if (name.equals("height")){}
			_height = value;
			return;
		}
		if (name.equals("width")){
			_width = value;
			return;
		}
		Assert.shouldNeverReachHere();
	}
```

到

```java
	void setHeight(int arg) {
		_height = arg;
	}
	void setWidth (int arg) {
		_width = arg;
	}
```

**动机**

*     
    避免条件行为
*     
    获得编译时检查
*   更清晰的界面

  
47.保留整个对象
------------

[](#47-preserve-whole-object)

  
你从一个对象中获取多个值，并在方法调用中将这些值作为参数传递。  
_  
而是发送整个对象_

```java
	int low = daysTempRange().getLow();
	int high = daysTempRange().getHigh();
	withinPlan = plan.withinRange(low, high);
```

到

```java
	withinPlan = plan.withinRange(daysTempRange());
```

**动机**

*     
    使参数列表对更改保持稳健
*   使代码更易读
*     
    删除传递的对象中可能已完成的重复代码
*     
    否定：它在参数对象和被调用对象之间创建依赖关系。

  
48.将参数替换为方法
--------------

[](#48-replace-parameter-with-method)

  
对象调用方法，然后将结果作为方法的参数传递。接收方也可以调用此方法。  
_  
移除参数并让接收方调用方法_

```java
	int basePrice = _quantity * _itemPrice;
	discountLevel = getDiscountLevel();
	double finalPrice = discountedPrice (basePrice, discountLevel);
```

到

```java
	int basePrice = _quantity * _itemPrice;
	double finalPrice = discountedPrice (basePrice);
```

**动机**

*     
    如果一个方法可以通过另一种方式获得作为参数传递的值，那么它应该。
*     
    如果接收方法可以进行相同的计算（不引用调用方法的任何参数）
*     
    如果您正在对具有对调用对象的引用的其他对象调用方法。

  
49.引入参数对象
------------

[](#49-introduce-parameter-object)

  
你有一组参数自然地结合在一起。  
_  
将它们替换为对象_

```java
	class Customer{
		amountInvoicedIn (start : Date, end : Date)
		amountReceivedIn (start : Date, end : Date)
		amountOverdueIn (start : Date, end : Date)
	}
```

到

```java
	class Customer{
		amountInvoicedIn (: DateRange)
		amountReceivedIn (: DateRange)
		amountOverdueIn (: DateRange)
	}
```

**动机**

*     
    减少参数列表的大小
*     
    使代码更加一致

  
50.删除设置方法
------------

[](#50-remove-setting-method)

  
字段应该在创建时设置，并且永远不要更改。  
_  
删除该字段的任何设置方法_

```java
	class Employee{
		setImmutableValue()
	}
```

到

```java
	class Employee{
		¯\_(ツ)_/¯
	}
```

**动机**  
  
明确你的意图：如果你不想让这个字段在创建后改变，那么就不要提供设置方法（并使这个字段成为final）。

51\. Hide方法
-----------

[](#51-hide-method)

  
方法不被任何其他类使用。  
_将方法设为私有_

```java
	class Employee{
		public method()
	}
```

到

```java
	class Employee{
		private method()
	}
```

**动机**  
  
当一个方法在它的类之外不需要时，它应该被隐藏

  
52.将构造函数替换为工厂方法
------------------

[](#52-replace-constructor-with-factory-method)

  
当你创建一个对象时，你需要做的不仅仅是简单的构造。  
_  
将构造函数替换为工厂方法_

```java
	Employee (int type) {
		_type = type;
	}
```

到

```java
	static Employee create(int type) {
		return new Employee(type);
	}
```

**动机**  
  
根据其子类（类型）创建对象。构造函数只能返回请求的对象的实例，因此需要Factory方法。

53.封装Downcast
-------------

[](#53-encapsulate-downcast)

  
方法返回一个需要由其调用方向下转换的对象。  
_  
将向下转换移动到方法内_

```java
	Object lastReading() {
		return readings.lastElement();
	}
```

到

```java
	Reading lastReading() {
		return (Reading) readings.lastElement();
	}
```

**动机**  
  
提供方法签名的最具体类型作为结果类型。  
  
如果签名是通用的，请检查客户端使用该方法的情况，如果一致，请提供一个更具体的签名。

  
54.将错误代码替换为异常
----------------

[](#54-replace-error-code-with-exception)

  
方法返回一个特殊的代码来指示错误。  
_  
而是引发异常_

```java
	int withdraw(int amount) {
		if (amount > _balance)
			return -1;
		else {
			_balance -= amount;
			return 0;
		}
	}
```

到

```java
	void withdraw(int amount) throws BalanceException {
		if (amount > _balance)
			throw new BalanceException();
		_balance -= amount;
	}
```

  
**动机**当一个程序发现一个错误时，它不知道该怎么做。它需要让它的调用者知道，而调用者可能会把错误传递到链的上游。

  
55.将异常替换为测试
--------------

[](#55-replace-exception-with-test)

  
在调用方可能首先检查的条件下，您正在引发检查异常。  
_  
更改调用方以首先进行测试_

```java
	double getValueForPeriod (int periodNumber) {
		try {
			return _values[periodNumber];
		} catch (ArrayIndexOutOfBoundsException e) {
			return 0;
		}
	}
```

到

```java
	double getValueForPeriod (int periodNumber) {
		if (periodNumber >= _values.length)
			return 0;
		return _values[periodNumber];
}
```

**动机**

*     
    不要过度使用异常，它们应该用于异常行为（意外的行为）。
*     
    不要用它们来代替条件测试。
*     
    在调用操作之前检查预期的错误条件。

  
11.处理泛化
==========

[](#11-dealing-with-generalization)

56.上拉场
------

[](#56-pull-up-field)

  
两个子类具有相同的字段。  
_  
将字段移到超类_

```java
	class Salesman extends Employee{
		String name;
	}
	class Engineer extends Employee{
		String name;
	}
```

到

```java
	class Employee{
		String name;
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

**动机**

*     
    删除重复的数据声明。
*     
    允许将行为从子类移动到超类。

57.上拉法
------

[](#57-pull-up-method)

  
你有方法在子类上有相同的结果。  
_  
将它们移到超类_

```java
	class Salesman extends Employee{
		String getName();
	}
	class Engineer extends Employee{
		String getName();
	}
```

到

```java
	class Employee{
		String getName();
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

**动机**

*     
    消除重复行为。

  
58.上拉构造器主体
-------------

[](#58-pull-up-constructor-body)

  
子类上的构造函数具有基本相同的主体。  
_  
创建一个超类构造函数;从子类方法调用它_

```java
	class Manager extends Employee...
		public Manager (String name, String id, int grade) {
		_name = name;
		_id = id;
		_grade = grade;
	}
```

到

```java
	public Manager (String name, String id, int grade) {
		super (name, id);
		_grade = grade;
	}
```

**动机**

*     
    构造函数不同于方法。
*     
    消除重复行为。

59.下推法
------

[](#59-push-down-method)

  
超类上的行为只与它的某些子类相关。  
_  
把它移到这些子类中。_

```java
	class Employee{
		int getQuota();
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

到

```java
	class Salesman extends Employee{
		int getQuota();
	}
	class Engineer extends Employee{}
```

  
当一个方法只在子类中有意义时。

60.下推字段
-------

[](#60-push-down-field)

  
字段仅由某些子类使用。  
_  
将字段移到这些子类中_

```java
	class Employee{
		int quota;
	}
	class Salesman extends Employee{}
	class Engineer extends Employee{}
```

到

```java
	class Salesman extends Employee{
		int quota;
	}
	class Engineer extends Employee{}
```

  
当一个字段只在子类中有意义时。

61.提取子类
-------

[](#61-extract-subclass)

  
类具有仅在某些实例中使用的功能。  
_  
为该要素子集创建子类_

```java
	class JobItem	{
		getTotalPrices()
		getUnitPrice()
		getEmployee()
	}
```

到

```java
	JobItem	{
		getTotalPrices()
		getUnitPrice()
	}
	class class LabotItem extends JobItem	{
		getUnitPrice()
		getEmployee()
	}
```

  
当一个类的行为用于类的某些实例而不用于其他实例时。

62.提取超类
-------

[](#62-extract-superclass)

  
您有两个具有相似特性的类。  
_  
创建一个超类，并将公共特性移到超类中_

```java
	class Department{
		getTotalAnnualCost()
		getName()
		getHeadCount
	}
	class Employee{
		getAnnualCost()
		getName()
		getId
	}
```

到

```java
	class Party{
		getAnnualCost()
		getName()
	}
	class Department {
		getAnnualCost()
		getHeadCount
	}
	class Employee {
		getAnnualCost()
		getId
	}
```

  
**动机**当两个类以相同的方式做类似的事情或以不同的方式做类似的事情。

63.提取接口
-------

[](#63-extract-interface)

  
多个客户端使用同一个类的接口的同一个子集，或者两个类的部分接口是公用的。  
_  
将子集提取到接口中_

```java
	class Employee {
		getRate()
		hasSpecialSkill()
		getName()
		getDepartment()
	}
```

到

```java
	interface Billable	{
		getRate()
		hasSpecialSkill()
	}
	class Employee implements Billable	{
		getRate
		hasSpecialSkill()
		getName()
		getDepartment()
	}
```

**动机**

*     
    如果一组客户端只使用类的特定职责子集。
*     
    如果一个类需要与任何可以处理某些请求的类一起工作。
*     
    每当一个类在不同的情况下有不同的角色时。

64.折叠层次结构
---------

[](#64-collapse-hierarchy)

  
超类和子类没有太大的区别。  
_将其合并在一起_

```java
	class Employee{	}
	class Salesman extends Employee{	}
```

到

```java
	class Employee{	}
```

  
**动机**当一个子类没有增加任何价值时。

65.表单模板方法
---------

[](#65-form-template-method)

  
子类中有两个方法，它们以相同的顺序执行类似的步骤，但步骤不同。_将步骤放入具有相同签名的方法中，以便原始方法变得相同。然后你可以把它们拉起来_

```java
	class Site{}
	class ResidentialSite extends Site{
		getBillableAmount()
	}
	class LifelineSite extends Site{
		getBillableAmount()
	}
```

到

```java
	class Site{ 	
		getBillableAmount()
		getBaseAmount()
		getTaxAmount()
	}
	class ResidentialSite extends Site{
		getBaseAmount()
		getTaxAmount()
	}
	class LifelineSite extends Site{
		getBaseAmount()
		getTaxAmount()
	}
```

**动机**

*     
    将继承与多态结合使用，以消除略有不同的重复行为。
*     
    当一个子类中有两个相似的方法时，将它们合并到一个超类中。
*     
    [模板法](https://www.wikiwand.com/en/Template_method_pattern)[\[四人帮\]](https://www.wikiwand.com/en/Design_Patterns)

  
66.将继承替换为委托
--------------

[](#66-replace-inheritance-with-delegation)

  
子类只使用超类接口的一部分，或者不想继承数据。  
_  
为超类创建一个字段，调整方法以委托给超类，并删除子类_

```java
	class Vector{
		isEmpty()
	}

	class Stack extends Vector {}
```

到

```java
	class Vector {
		isEmpty()
	}

	class Stack {
		Vector vector
		isEmpty(){
			return vector.isEmpty()
		}
	}
```

**动机**

*     
    使用委托可以清楚地表明您只是部分地使用了被委托的类。
*     
    您可以控制接口的哪些方面可以采用，哪些方面可以忽略。

力学

  
67.将委托替换为继承
--------------

[](#67-replace-delegation-with-inheritance)

  
您正在使用委托，并且经常为整个接口编写许多简单的委托。  
_  
使委托类成为委托的子类_

```java
	class Person {
		getName()
	}

	class Employee {
		Person person
		getName(){
			return person.getName()
		}
	}
```

到

```java
	class Person{
		getName()
	}
	class Employee extends Person{}
```

**动机**

*     
    如果您正在使用委托的所有方法。
*     
    如果你没有使用你委托的类的所有方法，你就不应该使用它。
*     
    要注意的是，委托由多个对象共享，并且是可变的。数据共享是一种责任，不能转移回继承。

12.大重构
======

[](#12-big-refactorings)

  
68.第1113章挑拨传承
----------------

[](#68-tease-apart-inheritance)

  
您有一个同时执行两项工作的继承层次结构。  
_  
创建两个层次结构，并使用委托从另一个层次结构中调用一个层次结构_

```java
	class Deal{}
	class ActiveDeal extends Deal{}
	class PassiveDeal extends Deal{}
	class TabularActiveDeal extends ActiveDeal{}
	class TabularPassiveDeal extends PassiveDeal{}
```

到

```java
	class Deal{
		PresentationStyle presettationStyle;
	}
	class ActiveDeal extends Deal{}
	class PassiveDeal extends Deal{}

	class PresentationStyle{}
	class TabularPresentationStyle extends PresentationStyle{}
	class SinglePresentationStyle extends PresentationStyle{}
```

**动机**

*     
    混乱的继承会导致代码重复。
*     
    如果层次结构中某个级别上的每个类都有开始使用同一个形容词的子类，那么您可能正在用一个层次结构做两项工作。

**力学注释**  
  
确定层次结构正在完成的不同工作。创建一个二维（或x维）网格，并在轴上标记不同的作业。

| 交易 | 活跃交易 | 被动交易 |
| --- | --- | --- |
| 表格式交易 |  |  |

  
69.将程序设计转换为对象
----------------

[](#69-convert-procedural-design-to-objects)

  
您拥有以过程风格编写的代码。  
_  
将数据记录转换为对象，分解行为，并将行为移动到对象_

```java
	class OrderCalculator{
		determinePrice(Order)
		determineTaxes(Order)
	}
	class Order{}
	class OrderLine{}
```

到

```java
	class Order{
		getPrice()
		getTaxes()
	}
	class OrderLine{
		getPrice()
		getTaxes()
	}
```

  
**使用**OOP（至少在JAVA中）

  
70.将域与表示分离
-------------

[](#70-separate-domain-from-presentation)

  
您有包含域逻辑的GUI类。  
_  
将域逻辑分离到单独的域类中_

```java
	class OrderWindow{}
```

到

```java
	class OrderWindow{
		Order order;
}
```

**动机**

*     
    将程序的两个复杂部分分离成更容易修改的部分。
*     
    允许同一业务逻辑的多个表示。
*   它的价值得到了证明

71.提取层次结构
---------

[](#71-extract-hierarchy)

  
您有一个类正在做太多的工作，至少部分是通过许多条件语句。  
_  
创建类的层次结构，其中每个子类表示一个特殊情况_

```java
	class BillingScheme{}
```

到

```java
	class BillingScheme{}
	class BusinessBillingScheme extends BillingScheme{}
	class ResidentialBillingScheme extends BillingScheme{}
	class DisabilityBillingScheme extends BillingScheme{}
```

**动机**

*     
    一个类实现一个想法变成实现两个或三个或十个。
*     
    坚持单一责任原则。

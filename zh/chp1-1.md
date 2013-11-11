---
layout: post
title: Linux 程序员题库
---

# 习题海选
## 四处搜刮

### 将一个字符串逆序

### 将一个链表逆序

### 计算一个字节里（byte）里面有多少bit被置1

### 搜索给定的字节
### 在一个字符串中找到可能的最长子字符串
### 字符串转换为整数
### 整数转换为字符串
### 解释C语言关键字extern ，static，volatile，const 的含义

static关键字至少有下列n个作用：

	1. 函数体内static变量的作用范围为该函数体，不同于auto变量，该变量的内存只被分配一次，因此其值在下次调用时仍维持上次的值；
	2. 在模块内的static全局变量可以被模块内所用函数访问，但不能被模块外其它函数访问；
	3. 在模块内的static函数只可被这一模块内的其它函数调用，这个函数的使用范围被限制在声明它的模块内；
	4. 在类中的static成员变量属于整个类所拥有，对类的所有对象只有一份拷贝；
	5. 在类中的static成员函数属于整个类所拥有，这个函数不接收this指针，因而只能访问类的static成员变量。

const关键字至少有下列n个作用：

	1. 欲阻止一个变量被改变，可以使用const关键字。在定义该const变量时，通常需要对它进行初始化，因为以后就没有机会再去改变它了；
	2. 对指针来说，可以指定指针本身为const，也可以指定指针所指的数据为const，或二者同时指定为const；
	3. 在一个函数声明中，const可以修饰形参，表明它是一个输入参数，在函数内部不能改变其值；
	4. 对于类的成员函数，若指定其为const类型，则表明其是一个常函数，不能修改类的成员变量；
	5. 对于类的成员函数，有时候必须指定其返回值为const类型，以使得其返回值不为“左值”。例如：
	const classA operator*(const classA& a1,const classA& a2);
	operator*的返回结果必须是一个const对象。如果不是，这样的变态代码也不会编译出错：
	classA a, b, c;
	(a * b) = c; // 对a*b的结果赋值
	操作(a * b) = c显然不符合编程者的初衷，也没有任何意义。

剖析：
惊讶吗？小小的static和const居然有这么多功能，我们能回答几个？如果只能回答1~2个，那还真得闭关再好好修炼修炼。

这个题可以考查面试者对程序设计知识的掌握程度是初级、中级还是比较深入，没有一定的知识广度和深度，不可能对这个问题给出全面的解答。大多数人只能回答出static和const关键字的部分功能。

#### 关键字volatile有什么含意 并给出三个不同的例子。

### 举例说明typedef和define的用法
### 语句 for(; 1; )有什么问题？它是什么意思？
### do... wehile 和 while...do有什么区别？
### 判断代码输出
	main()
	{
			int a,b,c,d;
		　　a=10;
		　　b=a++;
		　　c=++a;
		　　d=10*a++;
		　　printf("b，c，d：%d，%d，%d"，b，c，d）;
		　　return 0;
	} 
### 设有一下说明和定义：（32位编译器）
	typedef union {long i; int k[5]; char c;} DATE;
	struct data { int cat; DATE cow; double dog;} too;
	DATE max;
则语句 printf("%d",sizeof(struct date)+sizeof(max));的执行结果是：_______
### 谈谈汇编语言、C和C++三种语言在嵌入式开发中的区别和特点？简述你对嵌入式概念的理解？

### 什么是平衡二叉树？编写一个删除平衡二叉树的程序？

### 写一个程序，求有向有权图两点之间的最小权？

### 根据你的理解，写出Cstring类的构造函数和析构函数？

### 使用C语言实现对ini文件的访问，使程序可以对int，double，字符串类进行读写。

### n×n个方格（n为任意整数），定义若两个格有公共边则称两个格相邻。现将n个格中的N个格子图黑，使每个格子都与黑格子相邻。试编程，使N最小。

### 数据声明（Data declarations） 
- 一个整型数（An integer） 
- 一个指向整型数的指针（A pointer to an integer） 
-  一个指向指针的的指针，它指向的指针是指向一个整型数（A pointer to a pointer to an integer） 
- 一个有10个整型数的数组（An array of 10 integers） 
- 一个有10个指针的数组，该指针是指向一个整型数的（An array of 10 pointers to integers） 
- 一个指向有10个整型数数组的指针（A pointer to an array of 10 integers） 
- 一个指向函数的指针，该函数有一个整型参数并返回一个整型数（A pointer to a function that takes an integer as an argument and returns an integer） 
- 一个有10个指针的数组，该指针指向一个函数，该函数有一个整型参数并返回一个整型数（ An array of ten pointers to functions that take an integer argument and return an integer ）

### 嵌入式系统总是要用户对变量或寄存器进行位操作。给定一个整型变量a，写两段代码，第一个设置a的bit 3，第二个清除a 的bit 3。在以上两个操作中，要保持其它位不变。

### 下面的代码输出是什么，为什么？
	void foo(void) 
	{
		unsigned int a = 6; 
		int b = -20; 
		(a+b > 6) puts("> 6") : puts("<= 6"); 	
	}
这个问题测试你是否懂得C语言中的整数自动转换原则，我发现有些开发者懂得极少这些东西。不管如何，这无符号整型问题的答案是输出是">6"。原因是当表达式中存在有符号类型和无符号类型时所有的操作数都自动转换为无符号类型。 因此-20变成了一个非常大的正整数，所以该表达式计算出的结果大于6。这一点对于应当频繁用到无符号数据类型的嵌入式系统来说是丰常重要的。如果你答错了这个问题，你也就到了得不到这份工作的边缘。

### Typedef 在C语言中频繁用以声明一个已经存在的数据类型的同义字。也可以用预处理器做类似的事。例如，思考一下下面的例子：
	#define dPS struct s * 
	typedef struct s * tPS; 
以上两种情况的意图都是要定义dPS 和 tPS 作为一个指向结构s指针。哪种方法更好呢？（如果有的话）为什么？ 这是一个非常微妙的问题，任何人答对这个问题（正当的原因）是应当被恭喜的。答案是：typedef更好。思考下面的例子： 

	dPS p1,p2; 
	tPS p3,p4;

第一个扩展为 
	struct s * p1, p2;
上面的代码定义p1为一个指向结构的指，p2为一个实际的结构，这也许不是你想要的。第二个例子正确地定义了p3 和p4 两个指针。


### 以下代码中的两个sizeof用法有问题吗？
	void UpperCase( char str[] ) // 将 str 中的小写字母转换成大写字母
	{
		for( size_t i=0; iif( 'a'<=str[i] && str[i]<='z' )
		str[i] -= ('a'-'A' );
	}
	char str[] = "aBcDe";
	cout << "str字符长度为: " << sizeof(str)/sizeof(str[0]) << endl;
	UpperCase( str );
	cout << str << endl; 
答：函数内的sizeof有问题。根据语法，sizeof如用于数组，只能测出静态数组的大小，无法检测动态分配的或外部数组大小。函数外的str是一个静态定义的数组，因此其大小为6，函数内的str实际只是一个指向字符串的指针，没有任何额外的与数组相关的信息，因此sizeof作用于上只将其当指针看，一个指针为4个字节，因此返回4。 


### 判断地址加1输出结果
	main()
	{
		int a[5]={1,2,3,4,5};
		int *ptr=(int *)(&a+1); 
		printf("%d,%d",*(a+1),*(ptr-1));
	}
输出：2,5

    *(a+1）就是a[1]，*(ptr-1)就是a[4],执行结果是2，5

&a+1不是首地址+1，系统会认为加一个a数组的偏移，是偏移了一个数组的大小（本例是5个int）

int *ptr=(int *)(&a+1); 

则ptr实际是&(a[5]),也就是a+5

原因如下：

&a是数组指针，其类型为 int ( *)[5];而指针加1要根据指针类型加上一定的值，不同类型的指针+1之后增加的大小不同a是长度为5的int数组指针，所以要加 5*sizeof(int)所以ptr实际是a[5]但是prt与(&a+1)类型是不一样的(这点很重要)所以prt-1只会减去sizeof(int*)

a,&a的地址是一样的，但意思不一样，a是数组首地址，也就是a[0]的地址，&a是对象（数组）首地址，a+1是数组下一元素的地址，即a[1],&a+1是下一个对象的地址，即a[5]. 


### 交换两个变量的值，不使用第三个变量。即a=3,b=5,交换之后a=5,b=3;
有两种解法, 一种用算术算法, 一种用^(异或)
	a = a + b;
	b = a - b;
	a = a - b; 
	or
	a = a^b;// 只能对int,char..
	b = a^b;
	a = a^b;
	or
	a ^= b ^= a;

### c和c++中的struct有什么不同？
c和c++中struct的主要区别是c中的struct不可以含有成员函数，而c++中的struct可以。c++中struct和class的主要区别在于默认的存取权限不同，struct默认为public，而class默认为private

### 列举几种进程的同步机制，并比较其优缺点。

### 进程之间通信的途径

### 类的静态成员和非静态成员有何区别？
类的静态成员每个类只有一个，非静态成员每个对象一个
### 纯虚函数如何定义？使用时应注意什么？
	virtual void f()=0;
是接口，子类必须要实现

### 数组和链表的区别
数组：数据顺序存储，固定大小
连表：数据可以随机存储，大小可动态改变 

### 进程死锁的原因
资源竞争及进程推进顺序非法

### 死锁的处理
鸵鸟策略、预防策略、避免策略、检测与解除死锁

### 操作系统中进程调度策略有哪几种？
FCFS(先来先服务)，优先级，时间片轮转，多级反馈

### ISO的七层模型是什么？tcp/udp是属于哪一层？分别有何优缺点？
	应用层
	表示层
	会话层
	运输层
	网络层
	物理链路层
	物理层
	tcp /udp属于运输层
	TCP 服务提供了数据流传输、可靠性、有效流控制、全双工操作和多路复用技术等。
	与 TCP 不同， UDP 并不提供对 IP 协议的可靠机制、流控制以及错误恢复功能等。由于 UDP 比较简单， UDP 头包含很少的字节，比 TCP 负载消耗少。
	tcp: 提供稳定的传输服务，有流量控制，缺点是包头大，冗余性不好
	udp: 不提供稳定的服务，包头小，开销小

### 全局变量可不可以定义在可被多个.C文件包含的头文件中？为什么？
答：可以，在不同的C文件中以static形式来声明同名全局变量。
可以在不同的C文件中声明同名的全局变量，前提是其中只能有一个C文件中对此变量赋初值，此时连接不会出错

### 队列和栈有什么区别？

### 对于一个频繁使用的短小函数,在C语言中应用什么实现,在C++中应用什么实现?
c用宏定义，c++用inline

### 软件测试都有那些种类?

黑盒：针对系统功能的测试

白合：测试函数功能，各函数接口

### 接入网用的是什么接口?

### voip都用了那些协议?

### 确定模块的功能和模块的接口是在软件设计的那个队段完成的?
概要设计阶段

### 属于网络层协议的是:
	A.TCP;
	B.IP;
	C.ICMP;
	D.X.25

### TCP/IP通信建立的过程怎样，端口有什么作用？

### 描述一下嵌入式基于ROM的运行方式基于ram的运行方式有什么区别。

### task 有几种状态？

### C函数允许重入吗？

### 在一个包含 n 个元素的数组 M 中查找一个元素 x。 算法假设 M 已经按升序排列了，请写出二分搜索算法的步骤。

### 试将一个无序的线性表A=(11,16,8,5,14,10,38,23)转换成一个按升序排列的有序线性表（用链表实现）。 

### 何为栈和队列？简述两者的区别和联系。 

### 用const限定类的成员函数有什么作用？
类的成员函数后面加 const，表明这个函数不会对这个类对象的数据成员（准确地说是非静态数据成员）作任何改变。

在设计类的时候，一个原则就是对于不改变数据成员的成员函数都要在后面加 const，而对于改变数据成员的成员函数不能加 const。所以 const 关键字对成员函数的行为作了更加明确的限定：有 const 修饰的成员函数（指 const 放在函数参数表的后面，而不是在函数前面或者参数表内），只能读取数据成员，不能改变数据成员；没有 const 修饰的成员函数，对数据成员则是可读可写的。
除此之外，在类的成员函数后面加 const 还有什么好处呢？那就是常量（即 const）对象可以调用 const 成员函数，而不能调用非const修饰的函数。正如非const类型的数据可以给const类型的变量赋值一样，反之则不成立。
请看下面一个完整的例子，然后我再作一些说明。

	#include <iostream>
	#include <string>
	using namespace std; 
	class Student { 
		public: 
		Student() {} 
		Student( const string& nm, int sc = 0 ) 
		: name( nm ), score( sc ) {} 
		void set_student( const string& nm, int sc = 0 ) 
		{ 
		    name = nm; 
		    score = sc; 
		} 
		const string& get_name() const 
		{ 
			return name; 
		} 
		int get_score() const 
		{ 
			return score; 
		} 
	private: 
		string name; 
		int score; 
	}; 
	// output student  name and score 
	void output_student( const Student& student ) 
	{ 
		cout << student.get_name() << "\t"; 
		cout << student.get_score() << endl; 
	} 
	int main() 
	{ 
		Student stu( "Wang", 85 ); 
		output_student( stu ); 
	}

设计了一个类 Student，数据成员有 name 和 score，有两个构造函数，有一个设置成员数据函数 set_student()，各有一个取得 name 和 score 的函数 get_name() 和 get_score()。请注意 get_name() 和 get_score() 后面都加了 const，而 set_student() 后面没有（也不能有const）。

首先说一点题外话，为什么 get_name() 前面也加 const。如果没有前后两个 const 的话，get_name() 返回的是对私有数据成员 name 的引用，所以通过这个引用可以改变私有成员 name 的值，如

	Student stu( "Wang", 85 );
	stu.get_name() = "Li";

即把name 由原来的 "Wang" 变成了 "Li"，而这不是我们希望的发生的。所以在 get_name() 前面加 const 避免这种情况的发生。

那么，get_name() 和 get_score() 这两个后面应该加 const的成员函数，如果没有 const 修饰的话可不可以呢？回答是可以！但是这样做的代价是：const对象将不能再调用这两个非const成员函数了。如
const string& get_name(); // 这两个函数都应该设成 const 型

	int get_score();
	void output_student( const Student& student ) 
	{ 
		cout << student.get_name() << "\t"; // 如果 get_name() 和 get_score() 是非const成员函数，这一句和下一句调用是错误的
		cout << student.get_score() << endl; 
	}

由于参数student表示的是一个对const Student型对象的引用，所以 student 不能调用非const成员函数如 set_student()。如果 get_name() 和 get_score() 成员函数也变成非const型，那么上面的 student.get_name() 和 student.get_score() 的使用就是非法的，这样就会给我们处理问题造成困难。
因此，我们没有理由反对使用const，该加const时就应该加上const，这样使成员函数除了非const的对象之外，const对象也能够调用它。

### 如何一个strcpy考题中得到10分

找错题

	试题1：
	void test1()
	{
		char string[10];
		char * str1 = "0123456789";
		strcpy( string, str1 );
	}
	试题2：
	void test2()
	{
		char string[10], str1[10];
		int i;
		for(i=0; i<10; i++)
		{
			str1[i] = 'a';
		}
		strcpy( string, str1 );
	}
	试题3：
	void test3(char* str1)
	{
		char string[10];
		if( strlen( str1 ) <= 10 )
		{
			strcpy( string, str1 );
		}
	}

解答：

试题1字符串str1需要11个字节才能存放下(包括末尾的'\\0',而string只有10个字节的空间,strcpy会导致数组越界;

对试题2,如果面试者指出字符数组str1不能在数组内结束可以给3分;如果面试者指出strcpy(string, str1)调用使得从str1内存起复制到string内存起所复制的字节数具有不确定性可以给7分,在此基础上指出库函数strcpy工作方式的给10分;

对试题3,if(strlen(str1)  <= 10)应改为if(strlen(str1) < 10),因为strlen的结果未统计'\\0'所占用的1个字节。

剖析：

考查对基本功的掌握：字符串以'\\0'结尾；对数组越界把握的敏感度；库函数strcpy的工作方式，如果编写一个标准strcpy函数的总分值为10，下面给出几个不同得分的答案：

	2分
	void strcpy( char *strDest, char *strSrc )
	{
		while( (*strDest++ = * strSrc++) != '\\0' );
	}
	4分
	void strcpy( char *strDest, const char *strSrc )  //将源字符串加const，表明其为输入参数，加2分
	{
		while( (*strDest++ = * strSrc++) != '\\0' );
	}
	7分
	void strcpy(char *strDest, const char *strSrc) 
	{
		//对源地址和目的地址加非0断言，加3分
		assert( (strDest != NULL) && (strSrc != NULL) );
		while( (*strDest++ = * strSrc++) != '\\0');
	}
	10分
	//为了实现链式操作，将目的地址返回，加3分！
	char * strcpy( char *strDest, const char *strSrc ) 
	{
		assert( (strDest != NULL) && (strSrc != NULL) );
		char *address = strDest; 
		while( (*strDest++ = * strSrc++) !=  '\\0'); 
		return address;
	}

从2分到10分的几个答案我们可以清楚的看到，小小的strcpy竟然暗藏着这么多玄机，真不是盖的！需要多么扎实的基本功才能写一个完美的strcpy啊！

### 内功题:分别给出BOOL，int，float，指针变量 与“零值”比较的 if 语句（假设变量名为var）
解答：
	BOOL型变量：if(!var)
　　int型变量： if(var==0)
	float型变量：
	const float EPSINON = 0.00001;
	if ((x >= - EPSINON) && (x <= EPSINON)
	指针变量：　　if(var==NULL)

剖析：
考查对0值判断的“内功”，BOOL型变量的0判断完全可以写成if(var==0)，而int型变量也可以写成if(!var)，指针变量的判断也可以写成if(!var)，上述写法虽然程序都能正确运行，但是未能清晰地表达程序的意思。
一般的，如果想让if判断一个变量的“真”、“假”，应直接使用if(var)、if(!var)，表明其为“逻辑”判断；如果用if判断一个数值型变量(short、int、long等)，应该用if(var==0)，表明是与0进行“数值”上的比较；而判断指针则适宜用if(var==NULL)，这是一种很好的编程习惯。
浮点型变量并不精确，所以不可将float变量用“==”或“！=”与数字比较，应该设法转化成“>=”或“<=”形式。如果写成if (x == 0.0)，则判为错，得0分。

### 浅谈c++命名和c命名函数

作为一种面向对象的语言，C++支持函数重载，而过程式语言C则不支持。函数被C++编译后在symbol库中的名字与C语言的不同。例如，假设某个函数的原型为： 
	void foo(int x, int y);
该函数被C编译器编译后在symbol库中的名字为_foo，而C++编译器则会产生像_foo_int_int之类的名字。_foo_int_int这样的名字包含了函数名和函数参数数量及类型信息，C++就是考这种机制来实现函数重载的。

为了实现C和C++的混合编程，C++提供了C连接交换指定符号extern "C"来解决名字匹配问题，函数声明前加上extern "C"后，则编译器就会按照C语言的方式将该函数编译为_foo，这样C语言中就可以调用C++的函数了。

### 编写一个函数，作用是把一个char组成的字符串循环右移n个。比如原来是“abcdefghi”如果n=2，移位后应该是“hiabcdefgh” 

### 编写类String的构造函数、析构函数和赋值函数，已知类String的原型为：
	class String
	{ 
		public: 
			String(const char *str = NULL); // 普通构造函数 
			String(const String &other); // 拷贝构造函数 
			~ String(void); // 析构函数 
			String & operate =(const String &other); // 赋值函数 
		private: 
			char *m_data; // 用于保存字符串 
	};

解答：

	//普通构造函数
	String::String(const char *str) 
	{
		if(str==NULL) 
		{
			m_data = new char[1]; // 得分点：对空字符串自动申请存放结束标志'\0'的空
			//加分点：对m_data加NULL 判断
			*m_data = '\0'; 
		} 
		else
		{
			int length = strlen(str); 
			m_data = new char[length+1]; // 若能加 NULL 判断则更好 
			strcpy(m_data, str); 
		}
	}
	// String的析构函数
	String::~String(void) 
	{
		delete [] m_data; // 或delete m_data;
	}
	//拷贝构造函数
	String::String(const String &other) 　　　// 得分点：输入参数为const型
	{ 
		int length = strlen(other.m_data); 
		m_data = new char[length+1]; 　　　　//加分点：对m_data加NULL 判断
		strcpy(m_data, other.m_data); 
	}
	//赋值函数
	String & String::operate =(const String &other) // 得分点：输入参数为const型
	{ 
		if(this == &other) 　　//得分点：检查自赋值
		return *this; 
		delete [] m_data; 　　　　//得分点：释放原有的内存资源
		int length = strlen( other.m_data ); 
		m_data = new char[length+1]; 　//加分点：对m_data加NULL 判断
		strcpy( m_data, other.m_data ); 
		return *this; 　　　　　　　　//得分点：返回本对象的引用
	}

剖析：

能够准确无误地编写出String类的构造函数、拷贝构造函数、赋值函数和析构函数的面试者至少已经具备了C++基本功的60%以上！

在这个类中包括了指针类成员变量m_data，当类中包括指针类成员变量时，一定要重载其拷贝构造函数、赋值函数和析构函数，这既是对C++程序员的基本要求，也是《Effective　C++》中特别强调的条款。

仔细学习这个类，特别注意加注释的得分点和加分点的意义，这样就具备了60%以上的C++基本功！

### 请写一个C函数，若处理器是Big_endian的，则返回0；若是Little_endian的，则返回1。

### 结构和联合的区别

结构和联合有下列区别:

	1. 结构和联合都是由多个不同的数据类型成员组成, 但在任何同一时刻, 联合转只存放了一个被选中的成员, 而结构的所有成员都存在。
	2. 对于联合的不同成员赋值, 将会对其它成员重写, 原来成员的值就不存在了, 而对于结构的不同成员赋值是互不影响的。


### 有三个不同的信箱，今有4封不同的信欲投其中，共有多少种不同的投法？ 
答案：每封信有3种投法，于是3\*3\*3\*3。 

### 连续4次抛掷一枚硬币，求恰出现两次是正面的概率和最后两次出现是正面的概率。 
答案：两次正面为，0.5\*0.5\*0.5\*0.5；最后两次为正：0.5\*0.5 

### 一个口袋内装有除颜色外其他都相同的6个白球和4个红球，从中任意摸出2个，求：A、2个都是白球的概率；B、2个都是红球的概率；C、一个白球，一个红球的概率。 

答案：

	A：（6/10）×（5/9） 
	B：（4/10）×（3/9） 
	C：（6/10）×（4/9）＋（4/10）×（6/9） 

### 有30支篮球队，先分3组（每组10队）按单循环制进行比赛，然后将每组前三名集中，再按单循环制进行比赛，规定在小组赛已相遇的两队不再重赛，求先后比赛共有多少场？ 
答案：小组赛时候次数为 3×（9＋8＋。。。＋1） 

每组前三名比赛次数3×6＋3×3 

### 正方形边长为1，以各个顶点半径为1做弧，在正方形中间有一个公共区域，求面积。 

### 使用下列每组数字，排出加减乘除的公式，得出“24”。第一组“1、2、3、4”；第二组“5、6、7、8”；第三组“3、3、8、8”。 

答案：

	A：(1+2+3)*4=24 
	B：(5+7)*(8-6)=24 
	C：8/(3-8/3)=24 

### 10个人排队戴帽子，10个黄帽子，9个蓝帽子，戴好后，后面的人可以看见前面所有人的帽子，然后从后面问起，问自己头上的帽子是什么颜色，结果一直问了9个人都说不知道，而最前面的人却知道自己头上的帽子的颜色。问是什么颜色，为什么？ 


### 一个班上有50个学生。老师对同学们说：你们中有人脸上有泥巴，请自己举起手来。连续问了七遍，所有脸上有泥巴的学生都举起了手。每个人看不到自己脸上是否有泥巴，但能观察到其他人，假设每个学生都有很聪明。问：有多少个人脸上有泥巴？ 

### 引用与指针有什么区别？ 
	1) 引用必须被初始化，指针不必。 
	2) 引用初始化以后不能被改变，指针可以改变所指的对象。 
	3) 不存在指向空值的引用，但是存在指向空值的指针。 

### 描述实时系统的基本特性 

### 什么函数不能声明为虚函数？ 
constructor 

### 写出float x 与“零值”比较的if语句。 
if(x>0.000001&&x<-0.000001) 

### IP地址的编码分为哪俩部分？ 
IP地址由两部分组成，网络号和主机号。不过是要和“子网掩码”按位与上之后才能区分哪些是网络位哪些是主机位。

### 如何找出一个带环单链表中是什么地方出现环的？ 
一个递增一，一个递增二，他们指向同一个接点时就是环出现的地方 

### 输出和为一个给定整数的所有组合 
例如n=5 
	
	5=1+4；5=2+3（相加的数不能重复） 
	则输出 
	1，4；2，3。 

### 写一段程序，找出数组中第k大小的数，输出数所在的位置。例如{2，4，3，4，7}中，第一大的数是7，位置在4。第二大、第三大的数都是4，位置在1、3随便输出哪一个均可。函数接口为：int find_orderk(const int* narry,const int n,const int k) 要求算法复杂度不能是O(n^2） 

### 用递归算法判断数组a[N]是否为一个递增数组。 

递归的方法，记录当前最大的，并且判断当前的是否比这个还大，大则继续，否则返回false结束： 

	bool fun( int a[], int n ) 
	{ 
		if( n= =1 ) 
			return true; 
		if( n= =2 ) 
			return a[n-1] >= a[n-2]; 
		return fun( a,n-1) && ( a[n-1] >= a[n-2] ); 
	} 

### 编写算法，从10亿个浮点数当中，选出其中最大的10000个。 
用外部排序，在《数据结构》书上有 《计算方法导论》在找到第n大的数的算法上加工。

### 给两个数组和他们的大小，还有一动态开辟的内存，求交集，把交集放到动态内存dongtai，并且返回交集个数 
long jiaoji(long* a[],long b[],long* alength,long blength,long* dongtai[]) 

### 单连表的建立，把'a'--'z'26个字母插入到连表中，并且倒序，还要打印. 

### 可怕的题目终于来了:向搜索的输入信息是一个字符串，统计300万输入信息中的最热门的前十条，我们每次输入的一个字符串为不超过255byte,内存使用只有1G, 请描述思想，写出算发（c语言），空间和时间复杂度， 

### 国内的一些帖吧，如baidu,有几十万个主题，假设每一个主题都有上亿的跟帖子，怎么样设计这个系统速度最好，请描述思想，写出算发（c语言），空间和时间复杂度. 

### 简述一个Linux驱动程序的主要流程与功能。

### 求输出结果
	typedef struct 
	{ 
		int a:2; 
		int b:2; 
		int c:1; 
	}test; 
	test t; 
	t.a = 1; 
	t.b = 3; 
	t.c = 1; 
	printf("%d",t.a); 
	printf("%d",t.b); 
	printf("%d",t.c); 


### 求n个数（1....n）中k个数的组合.... 
如：combination(5,3) 要求输出：543，542，541，532，531，521，432，431，421，321

### 用指针的方法，将字符串“ABCD1234efgh”前后对调显示


### 有一个数组a[1000]存放0--1000;要求每隔二个数删掉一个数，到末尾时循环至开头继续进行，求最后一个被删掉的数的原始下标位置。 

### 有1,2,....一直到n的无序数组,求排序算法,并且要求时间复杂度为O(n),空间复杂度O(1),使用交换,而且一次只能交换两个数.（华为） 
	#include<iostream.h> 
	int main() 
	{ 
		int a[]  = {10,6,9,5,2,8,4,7,1,3}; 
		int len = sizeof(a) / sizeof(int); 
		int temp; 
		for(int i = 0; i < len; ) 
		{ 
			temp = a[a[i] - 1]; 
			a[a[i] - 1] = a[i]; 
			a[i] = temp; 
			if ( a[i] == i + 1) 
			i++; 
		} 
		for (int j = 0; j < len; j++) 
			cout<<a[j]<<","; 
		return 0; 
	} 

### 
[上一节](chp0-1.html)  |  [目录索引](../index.html)  |  [下一节](chp1-2.html)







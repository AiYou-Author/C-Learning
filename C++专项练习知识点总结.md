### 1.函数指针

```c++
int(*func)(intx,inty);
```

函数指针是指向函数的指针变量。因而"函数指针"本身首先应是[指针变量](https://baike.baidu.com/item/指针变量)，只不过该指针变量指向函数。这正如用指针变量可指向[整型变量](https://baike.baidu.com/item/整型变量)、字符型、[数组](https://baike.baidu.com/item/数组)一样，这里是指向函数。

```c++
#include<stdio.h>

int add(inta,intb)
{
	return a+b;
}

int sub(inta,intb)
{
	return a-b;
}

//函数指针
int(*func)(inta,intb);

intmain()
{
	func=&add;
	printf("add:%d\n",(*func)(10,5));
	func=&sub;
	printf("sub:%d\n",(*func)(10,5));
	return0;
}
```



### 2.指针函数

```c++
int*func(int a,int b);
```

普通函数就是int func(int a,int b);,返回值是int，而指针函数就是返回值是指针的函数，即返回值是int*。



### 3.#pragmapack(n)与对齐系数

每个特定平台上的[编译器](https://so.csdn.net/so/search?q=编译器&spm=1001.2101.3001.7020)都有自己的默认“对齐系数”(也叫对齐模数)。程序员可以通过预编译命令#pragmapack(n)，n=1,2,4,8,16来改变这一系数，其中的n就是你要指定的“对齐系数”。

```c++
#pragmapack(n)//n=4,2,1
struct node{undefined
int e;
char f;
short int a;
char b;
};
structnoden;
printf("%d\n",sizeof(n));
```

输出的结果分别为12,10,8



### 4.数组越界

数组溢出是不会报错的

![img](https://uploadfiles.nowcoder.com/images/20200714/622959792_1594729708688_59B2900AA03CB2182A51CDB520B535B6)





### 5.'\0'与"\0"

```c++
#include<stdio.h>
int main()
{
    if('\0'==0) putchar('X');
    if('\0'==0) putchar('Y');
    if('a'>'b') putchar('Z');
	printf("\n");
}
```

‘\0’是空字符，ASCII码值为0

'a' ASCII码值为97

'b' ASCII码值为98

"\0"表示的是字符串







### 6.转义字符

```c++
完整的转义字符及含义如下：
\a响铃(BEL)
\b退格(BS)
\f换页(FF)，将当前位置移到下页开头
\n换行(LF)，将当前位置移到下一行开头
\r回车(CR)，将当前位置移到本行开头
\t水平制表(HT)
\v垂直制表(VT)
\'单引号
\"双引号
\\反斜杠
```

'\72'代表了ASCII码为八进制数72的字符

以反斜杠\开头代表转义字符，默认为八进制





### 7.友元函数

1.友元只是破坏了类的**隐藏性**和**封装性**，不能被继，没有this指针。

2.可以直接调用，不需要通过对象或者指针。





### 8.字符串复制函数

**memcpy()函数**

```
从数组a复制k个元素到数组b中：memcpy(b,a,sizeof(int/double)*k)
数组a全部复制到数组b中：memcpy(b,a,sizeof(a))
```

**strcpy()函数**

```
char* strcpy(char*destin,char*source);
功能：将source指向的字符串拷到destin，会覆盖之前的，source包含'\0'
```

**strcmp()函数**

```
int strcmp(char*str1,char*str2);
功能:比较两个字符串str1,str2返回:str1<str2,返回负数;str1=str2,返回0;str1>str2,返回正数,,按位比较
```

**strstr()函数**

```
char* strstr(char*str1,char*str2);
功能:找出str2字符串在str1字符串中第一次出现的位置(不包括str2的串结束符)返回:返回该位置的指针,如找不到,返回空指针
charb[20]="abcdef";
printf("position:%s\n",strstr(b,"bc"));//position:bcdef
```

**sprintf()函数**

```
把信息输出到字符串，保证字符串足够大
char a[20];
memset(a,0,sizeof(a));
sprintf(a,"%d%d%d%d",4,5,6,7);
for(inti=0;i<sizeof(a);i++){printf("%d",a[i]);}//输出20位525354550000000000000000
```







### 9.虚函数



#### 9.1 虚函数为动态绑定，而缺省参数值为静态绑定

```c++
class A
{
public:
    virtual void func(int val = 1)
    { 
        std::cout<<"A->"<<val <<std::endl;
    }
    virtual void test()
    { func();}
};
class B : public A
{
public:
    void func(int val=0)
	{
        std::cout<<"B->"<<val <<std::endl;
    }
};
int main(int argc ,char* argv[])
{
    B*p = new B;
    p->test();
	return 0;
}
```

**virtual 函数是动态绑定，而缺省参数值却是静态绑定。** 意思是你可能会 **在“调用一个定义于派生类内的virtual函数”的同时，却使用基类为它所指定的缺省参数值。**

结论：**绝不重新定义继承而来的缺省参数值！**（可参考《Effective C++》**条款37**）

对于本例：

```
B*p = newB;
p->test();
```

**p->test()执行过程理解**：

​    (1) 由于B类中没有覆盖（重写）基类中的虚函数test()，因此会**调用基类A中的test()**；

​    (2) A中test()函数中继续调用虚函数 fun()，因为虚函数执行动态绑定，p此时的动态类型（即目前所指对象的类型）为B*，因此此时调用虚函数fun()时，**执行的是B类中的fun()**；所以先输出“**B->**”；

​    (3) **缺省参数值是静态绑定**，即此时**val的值**使用的是基类**A中的缺省参数值**，其值在编译阶段已经绑定，值为1，所以输出“**1**”；

​    最终输出“**B->1**”。所以大家还是记住上述结论：**绝不重新定义继承而来的缺省参数值**





#### 9.2 哪些函数不能被声明为虚函数

- 构造函数：虚函数是运行时绑定，需要对象，所以要先调用构造函数
- 静态成员函数：只有一份大家共享
- 内联函数：编译时就展开，而虚函数是运行时绑定
- 友元函数：友元函数不能被继承，所以不存在虚函数

- 虚函数可以是另一个类的友元函数，但不能是静态成员函数

```c++
public class A
{
   private:
        int d;
  public:
    friend B::Geta(A a);
}
public class B
{
  public:
    virtual int Geta(A &a)
   {
       return a->d;
   }
}
这里Geta是class B的一个虚拟成员函数
同时它也是class A的一个友元函数,所以他能够存取A的私有变量d
```





#### 9.3 析构函数为虚函数时，delete p时，会输出什么内容

```c++
class Base
{
     public:
         virtual ~Base(){
         	std::out<<"Base Destructor"<<std::endl;
       	}
}
class Derived: public Base
{
    public :
        ~Derived(){
        	std::out<<"Derived Destructor"<<std::endl;
        }
}
Base* p=new Derived();
delete p;
```

```
Derived Destructor
Base Destructor
```

如果基类的析构函数不是虚函数，那么，像这种定义一个基类的指针，指向一个派生类的对象，当你delete这个基类的指针时，它仅调用基类的析构函数，并不调用派生类的析构函数。

**如果基类的析构函数是虚函数，delete基类的指针时，不仅会调用基类的析构函数，还会调用派生类的析构函数。**

而调用的顺序是先调用派生类的析构函数、然后调用基类的析构函数





















### 10.类型所占字节

|           | 32位 | 64位           |
| --------- | ---- | -------------- |
| char      | 1    | 1              |
| int       | 4    | 大多数4，少数8 |
| long      | 4    | 8              |
| float     | 4    | 4              |
| double    | 8    | 8              |
| long long | 8    | 8              |
| 指针      | 4    | 8              |

无符号数的最小值为0











### 11.extern "C"

​	extern "C" 的作用是为了能够正确的实现 C++ 代码调用 C 语言代码。加上 extern "C" 后，会指示编译器这部分代码按照 C 语言（而不是 C++）的方式进行编译。由于 C++ 支持函数重载，因此编译器编译函数的过程中会将函数的参数类型也加到编译后的代码中，而不仅仅是函数名；而C语言并不支持函数重载，因此编译 C 语言代码的函数时不会带上函数的参数类型，一般只包括函数名。 这个功能十分有用处，因为在 C++ 出现以前，很多代码都是 C 语言写的，而且很底层的库也是 C 语言写的，为了更好的支持原来的 C 代码和已经写好的 C 语言库，需要在 C++ 中尽可能的支持 C，而 extern "C" 就是其中的一个策略。













### 12.智能指针



（shared_ptr）的引用计数本身是安全且无锁的，但对象的读写则不是，因为 shared_ptr 有两个数据成员，读写操作不能原子化。 shared_ptr 的线程安全级别和内建类型、标准库容器、std::string 一样，即：
• 一个 shared_ptr 对象实体可被多个线程同时读取；
• 两个 shared_ptr 对象实体可以被两个线程同时写入，“析构”算写操作；
• 如果要从多个线程读写同一个 shared_ptr 对象，那么需要加锁。
请注意，以上是 shared_ptr 对象本身的线程安全级别，不是它管理的对象的线程安全级别















### 13.地址分析

```c++
struct A
{
    bool b;
    int arr[2];
    int i;
    int j;
};
int main()
{
    A a;
    a.b = false;
    a.arr[0] = 1;
    a.arr[1] = 2;
    a.i = 20;
    a.j = 30;
    *(a.arr + 1) = 40;
    A *p = 0;
    unsigned int q = (unsigned int)(&p->i);
    (*(int *)((char *)&a + q)) = -50;
     return 0;
}
/*
A*p = 0;
unsigned int q = (unsigned int)(&p->i));
(*(int*)((char*)&a +q)) = -50;
考点1：结构体指针，结构体指针的访问方式为（p->i）
考点2：->优先级大于&,故而这里是取对象的成员相对地址
考点3：考虑字节4对齐，bool b后面有3个空字节，所以i的地址就是12. 即q=12
考点4：(char*)&a +q 先把a的地址转换成指向char型（即1个Byte）指针，然后指针往后移动q个Byte。
所以最后得出的结果是a.i的值为-50。*/
```













### [14.sizeof()和strlen()](https://blog.csdn.net/magic_world_wow/article/details/80500473)

sizeof()计算的是分配空间的实际字节数。

strlen()是计算的空间中字符的个数（不包括**‘\0’**）

sizeof是在编译的时候就将结果计算出来了是类型所占空间的字节数，所以以数组名做参数时计算的是整个数组的大小。

strlen是在运行的时候才开始计算结果，这是计算的结果不再是类型所占内存的大小，数组名就退化为指针了

```
char* s = "0123456789";
sizeof(s);     //结果 4    ＝＝＝》s是指向字符串常量的字符指针
sizeof(*s);    //结果 1    ＝＝＝》*s是第一个字符
strlen(s);     //结果 10   ＝＝＝》有10个字符，strlen是个函数内部实现是用一个循环计算到\0为止之前
strlen(*s);     //结果 10   ＝＝＝》错误


char s[] = "0123456789";
sizeof(s);     //结果 11   ＝＝＝》s是数组，计算到\0位置，因此是10＋1
strlen(s);     //结果 10   ＝＝＝》有10个字符，strlen是个函数内部实现是用一个循环计算到\0为止之前
sizeof(*s);    //结果 1    ＝＝＝》*s是第一个字符

char s[100] = "0123456789";
sizeof(s);     //结果是100 ＝＝＝》s表示在内存中的大小 100×1
strlen(s);     //结果是10  ＝＝＝》strlen是个函数内部实现是用一个循环计算到\0为止之前

int s[100] = "0123456789";
sizeof(s);     //结果 400  ＝＝＝》s表示再内存中的大小 100×4
strlen(s);     //错误      ＝＝＝》strlen的参数只能是char* 且必须是以‘\0‘结尾的

char q[]="abc";
char p[]="a\n";
sizeof(q),sizeof(p),strlen(q),strlen(p);\\结果是 4 3 3 2

char p[] = {'a','b','c','d','e','f','g','h'};
char q[] = {'a','b','c','d,'\0','e','f','g'};
sizeof(p);     //结果是8 ＝＝＝》p表示在内存中的大小 8×1
strlen(p);     //为一个随机值，结果与编译器有关，不同编译器结果一般不同
sizeof(q);     //结果是8 ＝＝＝》p表示在内存中的大小 8×1
strlen(q);     //结果为4 ＝＝＝》存在'\0',遇到'\0'计算停止。
```









### 15.数组指针与指针数组

```c++
int *p1[5]；
int (*p2)[5]；
```

首先，对于语句int* p1[5]，因为“[]”的优先级要比“* ”要高，所以 p1 先与“[]”结合，构成一个数组的定义，数组名为 p1，而“int*”修饰的是数组的内容，即数组的每个元素。也就是说，该数组包含 5 个指向 int 类型数据的指针，如图 1 所示，因此，它是一个指针数组。

![img](https://s2.loli.net/2022/06/04/MLN9lJYfv1ZKQF8.jpg)

其次，对于语句“int(* p2)[5]”，“()”的优先级比“[]”高，“*”号和 p2 构成一个指针的定义，指针变量名为 p2，而 int 修饰的是数组的内容，即数组的每个元素。也就是说，p2 是一个指针，它指向一个包含 5 个 int 类型数据的数组，如图 2 所示。很显然，它是一个数组指针，数组在这里并没有名字，是个匿名数组。

![img](https://s2.loli.net/2022/06/04/3zrp6cLPOMQqGF2.jpg)













### 16.C++ lambda函数



```c++
int main()
{
    int a = 1;
    int b = 2;
    // 定义一个lambda函数
    auto sum = [](int x, int y)->int{
        return x + y;
    };

    std::cout << sum(a, b) << std::endl;   // 3

    return 0;
}
```

```c++
[capture](parameters) mutable -> return-type{statement}
```

- [capture]，捕捉列表。捕捉列表总是在lambda函数的开始，[]是lambda函数的引出符。编译器根据该引出符确定接下来的代码是不是lambda函数。捕捉列表能够捕捉上下文中的变量以供lambda函数使用。下文会介绍捕捉的方法。
- (parameters)，参数列表。和普通函数的参数列表一致，如果不需要参数可以连()一起省略。
- mutable，一个修饰符。默认情况下，lambda函数总是一个const函数，mutable可以取消其常量性。在使用mutable时，参数列表不可省略，即使参数为空。
- ->return-type，返回类型。用追踪返回类型声明函数的返回值。不需要返回值时，可以连同符号->一起省略。另外，在返回类型明确的情况下，也可以省略，让编译器推导出返回类型。
- statement，函数体。与普通函数一样，但是可以使用捕捉列表中的变量。

```c++
int main()
{
    int a = 1;
    int b = 2;

    [] {};                             // 最简单
    [=] {return a + b; };              // 省略了参数列表和返回值类型
    auto func1 = [&](int c) {b = a + c; };    // 省略了返回值类型
    auto func2 = [=, &b](int c)->int { return b += a + c; };  // 完整的lambda函数

    return 0;
}
```



捕捉列表的几种形式：

- [var]表示以值传递的方式来捕捉变量var。
- [=]表示以值传递的方式捕捉所有父作用域的变量，包括this指针。
- [&var]表示引用传递捕捉变量var。
- [&]表示引用传递捕捉所有父作用域的变量，包括this指针。
- [this]表示值传递方式捕捉当前的this指针。
- 以上的方式可以组合使用，但是不允许对同一个变量以同一方式重复捕捉。
- 在块作用域(可以理解为在{}以内的代码)以外的lambda函数捕捉列表必须为空，这种lambda和普通函数除了语法上不同以外，和普通函数差别不大。在块作用域内的lambda函数只能捕捉父作用域中的自动变量，不能捕捉非此作用域的变量或者非自动变量(如静态变量等)。











### 17.类成员的初始化列表



以下三种情况下需要使用**初始化成员列表**：

情况一、**需要初始化的数据成员是对象的情**况(这里包含了继承情况下，通过显示调用父类的构造函数对父类数据成员进行初始化)；

情况二、需要初始化**const修饰的类成员**；

情况三、需要初始化**引用成员数据**；



数组成员是不能在初始化列表里初始化的





### 18.迭代器

vector的插入操作会导致迭代器失效

vector是顺序存储的，尾部插入，在头部插入或者中间插入都会导致插入的部位以及其后的所有迭代器都失效；









### 19.抽象类

​	抽象类中可以不存在任何抽象方法

​	抽象类可以被抽象类所继承

​	如果一个非抽象类从抽象类中派生，不通过覆盖来实现继承的抽象成员，此时，派生类也会是抽象类，因为基类的抽象方法被继承下来，在派生类中，没有被重写，仍为抽象方法，那也就是说一样是抽象类了













### 20.const修饰指针的三种效果

左定值，右定向（const位于 *左侧值不变，const位于 *右侧指向地址不变）

```c++
const int*p=&a；
int const* p2=&a;
//可以初始化，也可以不初始化
//p的指向可以变，但是指向的变量，其内容不可变
```

```c++
int *const p2=&a;
//必须初始化
//p的指向地址不可变，但是指向的变量，其内容可变
```

```c++
const int*const p=&a；
//p中存放的内存单元的地址和内存单元中的内容都不可变
```



A. `const int * const p = &x;`中指针p及p指向的int类型数据都被const修饰，即`*p`与`p`都为const属性无法修改

- 编译器报错`error: assignment of read-only location ‘*(const int*)p’ *p = 1;`
- 故`* p =1;`语法错误

B. `const int &q=x;`是指向常量的引用，使用时必须初始化，而且初始化后，引用值不可以改变,引用的常量也不能改变

- 注意 只是修饰引用`q`,`x`不受影响
- 编译器报错`error: increment of read-only reference ‘q’ q++;`
- 故`q++;`语法错误

C. `int const *next=&x;`中`const`修饰整型数 int即`*next`

- 注意 同样只是修饰`*next`,`x`仍然是变量
- 指针变量`next`没有被const修饰因此可以被`next++`改变,语法正确

D. `const int *j=&x;`中`const int *`同`int const *`const修饰`*j`

- 编译器报错`error: increment of read-only location ‘* j’ (*j)++;`
- `(*j)`为const属性无法修改,故语法错误







### 21.继承

有三类成员函数不能被子类继承，分别是：**构造函数（包括拷贝构造）、析构函数、赋值运算符重载函数。**











### 22.类



#### 22.1 类的大小

1.类的大小为类的非静态成员数据的类型大小之和，也就是说**静态成员数据不作考虑**。

2.**普通成员函数与sizeof无关**。

3.**虚函数由于要维护在虚函数表**，所以要占据一个指针大小，也就是**4字节**。

4.类的总大小也遵守类似class字节对齐的，调整规则。



C++标准规定类的大小不为0，**空类的大小为1**，当类不包含虚函数和非静态数据成员时，其对象大小也为1。



**对象大小 = 虚函数指针 +  所有非静态数据成员大小  +  因对齐而多占的字节**







#### 22.2 构造和析构的调用顺序

```c++
class B:pubilc A

A *pa =new B();
delete pa;
```

先调用基类的构造函数，再调用继承类的构造函数

释放时，先调用继承类的析构函数，再调用基类的析构函数











### 23.类和结构体的关系

struct 能包含成员函数 能继承 能实现多态 和class的区别在于默认访问控制类型不同 struct是public的，class是private

struct也可以有无参构造

struct的成员变量不只有public









### 24.char*和char[]

​	若char\* p="Hello";实际上p是一个指针，指向的内容是字符串常量Hello，指向的内容是不可修改的！如果执行\*p+1='F'操作是错误的！因为p是指针，可以让p指向别的内容，如p="china" 是正确的。

​	char p[]="Hello";实际上是一个字符串数组初始化的方式，字符串数组的有两种初始化方式，一种是这样的初始化，另外一种是列表初始化；而p可以理解为是一个常量指针，p的值不可修改，如p++操作是错误的。

```c
char a[10]="china"；
char a[10],*p=a;p="china"；
char *a;a="china"；
char a[10],*p;p=a="china"；//错误，a为字符串数组对应的地址常量，不可以对其赋值。
```





```c
#include<iostream>
using namespace std;
int main(void)
{
    char str1[] = "hello world";   //存放在栈中的数组
    char str2[] = "hello world";   //存放在栈中的数组

    const char str3[] = "hello world";  //存放在栈中的字符串常量
    const char str4[] = "hello world";  //存放在栈中的字符串常量

    const char* pstring1 = "hello world";   //本身在栈中，指向常量的指针
    const char* pstring2 = "hello world";   //本身在栈中，指向常量的指针     //显然二者所指向的地址一致

    int x = (int)pstring1;
    int y = (int)pstring2;                  //为了方便打印出指针所指向的地址

    cout << boolalpha << ( str1==str2 ) << endl;               //比较字串首地址      flase
    cout << boolalpha << ( str3==str4 ) << endl;               //比较字串首地址      flase
    cout << boolalpha << ( pstring1==pstring2 ) <<endl;        //比较指针所指地址    true

    cout << "str1=" << &str1 << ",";
    cout << "str2=" << &str2 << endl;

    cout << "str3=" << &str3 << ",";
    cout << "str4=" << &str4 << endl;

    cout << "pstring1=" << &pstring1 << ",";
    cout << "pstring2=" << &pstring2 << endl;                   //输出指针本身地址

    cout<<hex;
    cout << "pstring1=" << x << ",";
    cout<<hex;
    cout << "pstring2=" << y << endl;      //16进制输出指针所指地址

    return 0;
}

```

![img](https://s2.loli.net/2022/06/21/Wu4xUIbY3Fi5ePE.png)





### 25. && || 逻辑

&& 和 || 为短路与 短路或

&&若前面的表达式为false,整个逻辑表达式为false,所以后面的表达式无论true和false都无法影响整个表达式的逻辑结果，所以为了提高代码执行速率，这里后面的表达式就不会执行。

同理，若||前面表达式为true,则后面的表达式无需计算。

& 和 | 为不短路与 不短路或



```c++
int i=0;
int j=0;
if((++i>0)||(++j>0)) {
//打印出i和j的值。
}
//i=1,j=0
```









### 26.八进制数与十进制数



C语言中以数字1-9开头表示十进制,以0开头表示八进制,以0X开头表示十六进制。

%d       十进制有符号整数 

%u      十进制无符号整数 

%f       浮点数 

%s       字符串 

%c       单个字符 

%p       指针的值

%e       指数形式的浮点数 

%x, %X     无符号以十六进制表示的整数 

%0       无符号以八进制表示的整数 

%g       自动选择合适的表示法









### 27.二维数组地址

数组定义`int a[3][4]`下面哪个不能表示`a[1][1]`？

```c
*(&a[0][0]+5);
*(*(a+1)+1);
*(&a[1]+1);//false
*(a[1]+1);

a[1]表示a[1][0]的地址，a[1]+1表示的是a[1][1]的地址
*(&a[1]+1)应该改为*(&a[1][0]+1)，因为a[1]表示的就是a[1][0]的地址
```













### 28.变量存储区域

（1）从静态存储区域分配：

内存在程序编译时就已经分配好，这块内存在程序的整个运行期间都存在。速度快、不容易出错，因为有系统会善后。例如全局变量，static变量等。

（2）在栈上分配：

在执行函数时，函数内局部变量的存储单元都在栈上创建，函数执行结束时这些存储单元自动被释放。栈内存分配运算内置于处理器的指令集中，效率很高，但是分配的内存容量有限。

（3）从堆上分配：

即动态内存分配。程序在运行的时候用malloc或new申请任意大小的内存，程序员自己负责在何时用free或delete释放内存。动态内存的生存期由程序员决定，使用非常灵活。如果在堆上分配了空间，就有责任回收它，否则运行的程序会出现内存泄漏，另外频繁地分配和释放不同大小的堆空间将会产生堆内碎块。

一个C、C++程序编译时内存分为5大存储区：堆区、栈区、全局区、文字常量区、程序代码区。

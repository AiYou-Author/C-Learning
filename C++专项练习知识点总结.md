#### 1.函数指针

```c++
int(*func)(intx,inty);
```

函数指针是指向函数的指针变量。因而"函数指针"本身首先应是[指针变量](https://baike.baidu.com/item/指针变量)，只不过该指针变量指向函数。这正如用指针变量可指向[整型变量](https://baike.baidu.com/item/整型变量)、字符型、[数组](https://baike.baidu.com/item/数组)一样，这里是指向函数。

```c++
#include<stdio.h>

intadd(inta,intb)
{
	return a+b;
}

intsub(inta,intb)
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



#### 2.指针函数

```c++
int*func(inta,intb);
```

普通函数就是intfunc(inta,intb);,返回值是int，而指针函数就是返回值是指针的函数，即返回值是int*。



#### 3.#pragmapack(n)与对齐系数

每个特定平台上的[编译器](https://so.csdn.net/so/search?q=编译器&spm=1001.2101.3001.7020)都有自己的默认“对齐系数”(也叫对齐模数)。程序员可以通过预编译命令#pragmapack(n)，n=1,2,4,8,16来改变这一系数，其中的n就是你要指定的“对齐系数”。

```c++
#pragmapack(n)//n=4,2,1
structnode{undefined
int e;
char f;
short int a;
char b;
};
structnoden;
printf("%d\n",sizeof(n));
```

输出的结果分别为12,10,8



#### 4.数组越界

数组溢出是不会报错的

![img](https://uploadfiles.nowcoder.com/images/20200714/622959792_1594729708688_59B2900AA03CB2182A51CDB520B535B6)





#### 5.'\0'与"\0"

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







#### 6.转义字符

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





#### 7.友元函数

1.友元只是破坏了类的**隐藏性**和**封装性**，不能被继，没有this指针。

2.可以直接调用，不需要通过对象或者指针。





#### 8.字符串复制函数

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







#### 9.虚函数

虚函数为动态绑定，而缺省参数值为静态绑定

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





##### 描述：

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













#### 10.类型所占字节

|        | 32位 | 64位           |
| ------ | ---- | -------------- |
| char   | 1    | 1              |
| int    | 4    | 大多数4，少数8 |
| long   | 4    | 8              |
| float  | 4    | 4              |
| double | 8    | 8              |
| 指针   | 4    | 8              |













#### 11.extern "C"

​	extern "C" 的作用是为了能够正确的实现 C++ 代码调用 C 语言代码。加上 extern "C" 后，会指示编译器这部分代码按照 C 语言（而不是 C++）的方式进行编译。由于 C++ 支持函数重载，因此编译器编译函数的过程中会将函数的参数类型也加到编译后的代码中，而不仅仅是函数名；而C语言并不支持函数重载，因此编译 C 语言代码的函数时不会带上函数的参数类型，一般只包括函数名。 这个功能十分有用处，因为在 C++ 出现以前，很多代码都是 C 语言写的，而且很底层的库也是 C 语言写的，为了更好的支持原来的 C 代码和已经写好的 C 语言库，需要在 C++ 中尽可能的支持 C，而 extern "C" 就是其中的一个策略。













#### 12.智能指针



（shared_ptr）的引用计数本身是安全且无锁的，但对象的读写则不是，因为 shared_ptr 有两个数据成员，读写操作不能原子化。 shared_ptr 的线程安全级别和内建类型、标准库容器、std::string 一样，即：
• 一个 shared_ptr 对象实体可被多个线程同时读取；
• 两个 shared_ptr 对象实体可以被两个线程同时写入，“析构”算写操作；
• 如果要从多个线程读写同一个 shared_ptr 对象，那么需要加锁。
请注意，以上是 shared_ptr 对象本身的线程安全级别，不是它管理的对象的线程安全级别















#### 13.地址分析

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


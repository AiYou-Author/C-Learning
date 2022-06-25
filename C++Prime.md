## 第二章 开始学习C++

### 2.1 进入C++

#### 2.1.1 main函数

编译器自动运行main函数



#### 2.1.2 C++注释



#### 2.1.3 C++预处理器和iostream文件



#### 2.1.4 头文件名



#### 2.1.5 名称空间

```c++
using std::cout 
```



#### 2.1.6 使用cout进行c++输出











### 2.2 C++语言

#### 2.2.1 声明语句和变量

```c++
int carrots;
```



#### 2.2.2 赋值语句

```C++
int carrots;
carrots=88;
```



#### 2.2.3 cout的新花样













### 2.3 其他C++语句

#### 2.3.1 使用Cin

```
cin >> carrots;
```



#### 2.3.2 使用cout进行拼接

```c++
cout << "Now you have"<< carrots << endl;
```



#### 2.3.3 类简介

类之于对象就像类型至于变量

类定义描述的数据格式及其用法，对象则是根据数据格式规范创建的实体

```c++
//创建一个int类型的变量carrots
int carrots;
```

```c++
//cout是ostream的一个类对象
//cin是istream的一个类对象
```











### 2.4 函数



#### 2.4.1 使用有返回值的函数

```c++
//函数调用
x=sqrt(6.25);
```

C++程序应当为程序中使用的每个函数提供原型

使用函数之前，C++编译器必须知道函数的参数类型和返回值类型



#### 2.4.2 函数变体

有返回值的函数被称为函数，没有返回值的函数被称为过程

```c++
answer=pow(5.0,8.0);
int rand(void);
```



#### 2.4.3 用户定义的函数

```C++
//函数头，花括号中的函数体
type functionname(aruementlist)
{
	statments
}
```

将计算机操作系统看做调用程序，main的返回值并不是返回给程序的其他部分，而是返回给操作系统、



#### 2.4.4用户定义的有返回值的函数





#### 2.4.5 再多函数程序中使用using编译指令

只让需要访问名称空间std的函数访问它是更好的选择









### 2.5 总结



- 程序从main()开始执行
- 函数由函数头和函数体组成
- 函数头指出函数的返回值的类型和函数期望通过参数 
- 函数体由一系列位于花括号({})中的C++语句组成











## 第三章 处理数据







### 3.1 简单变量



#### 3.1.1 变量名

```c++
//名称中只能使用字母字符、数字和下划线
//名称第一个字符不能是数字
//以两个下划线或下划线和大写字母打头的名称被保留给实现
```





#### 3.1.2 整型





#### 3.1.3 整型short,int,long和long long



- short至少16位
- int至少与short一样长(16位的int取值范围是-32768~+32767)
- long至少32位，且至少与int一样长
- long long至少64位，且至少与long一样长

```c++
//8位等于1字节
int is 4 bytes
short is 2 bytes;
long is 4 bytes;
long long is 8 bytes;
```



##### **siezof()和头文件climits(定义了符号常量)**

```C++
#Inlcude<climits>
INT_MAX = 2147483647=2^32;
SHRT_MAX = 32767=2^16;
LONG_MAX = 2147483647=2^32;
LLONG_MAX = 9223372036854775807= 2^64;
INT_MIN = -2147483647;
CHAR_BIT = 8;
```

```
cout << sizeof(int)<<"bytes"
```

预处理方式：

编译过程中，将源代码传给预处理器，编译指令告诉预处理器，在程序中找#include和#define，并将程序替换。





##### C++的初始化方法

```C++
int emus{7};
int rocs = {};
```





#### 3.1.4  无符号类型



short表示的范围-32768~32767，无符号版本的表示范围为0~65535

```C++
unsigned short change;
unsigned int rovert;
```





#### 3.1.5  选择整型类型



如果知道变量可能表示的值大于16位整数的最大可能值，使用long。即使系统上int为32位一直到16位也不会有大影响

short同理



#### 3.1.6 整型字面值



```c++
cout << 42;  			//42
cout << hex;
cout << 42 << endl;		//2a
cout << oct;
cout << 42 << endl;		//52
```





#### 3.1.7 C++如何确定常量的类型



| 字符类型           | 整数后缀        |
| ------------------ | --------------- |
| long               | l或L            |
| unsigned int       | u或U            |
| unsigned long      | LU或UL          |
| unsigned long long | ull,Ull,uLL,ULL |



#### 3.1.8 char类型：字符和小整数



- 存储字符集为ASCII字符集
- 定义格式：char ch='M';
- 成员函数 cout.put('M');
- 字符串中含有转义序列，如\b,\n,\t
- 通用字符名：Unicode和ISO 10646，通用字符名可以以\u和\U打头，\u后面是8个16进制位，\U后面是16个16进制位。 

```c++
int k\u00F6rper;     //k符号rper
cout << " Let them eat g\u00E2teau."  //g符号teau
//\u00F6代表的是Unicode中U-00F6的字符 
```

- wcha_t 可以表示扩展字符集，支持两字节，通过前缀L指示宽字符常量和字符串，wcout和wcin处理wchar_t流

```
wchar_t bob = L'p';
wcout << L"tall"<<endl;
```

- char16_t和char32_t，代表16位和32位的符号类型，使用u和U前缀分别表示

```
char16_t ch1 = u'q';
char32_t ch2 = U'\U0000222B';
```

- bool类型









### 3.2 const限定符





### 3.3 浮点数





#### 3.3.1 书写浮点数

​	3.45E6，指的是3.45与100000相乘。之所以成为浮点，因为小数点可以移动





#### 3.3.2 浮点类型

float，double和long double

float至少32位；double至少48位，且不少于float；long double至少和double一样多



#### 3.3.3 浮点常量

```
1.234f			//float
2.45E20F		//float
2.23246E28		//double
2.2L			//long double
```











### 3.4 C++算术运算符



#### 3.4.1 运算符优先级和结合性





#### 3.4.2 除法分支

若两个数都为整数，则进行整数除法

如果其中一个操作数是浮点值，则小数部分保留，结果为浮点数







#### 3.4.3 求模运算符





#### 3.4.4 类型转换



将较大的浮点类型转换为较小的浮点类型，精度降低

将浮点类型转换为整型，小数部分丢失

将较大整型转换为较小整型，long转换为short，超出范围，无法存储直接取最大值



**以{}方式初始化**为列表初始化，列表初始化不允许缩窄

```
const int code = 66;
int x=66;
char c1 {31325};    //narrowing,not allowed
char c2{code};		//allowed
char c3 = {x};		//not allowed,x is not constant
```



**表达式中的转换**

计算表达式时，C++将bool、char,unsigned char,signed char和short值转换为int，这些转换被称为整型提升。通常将int类型选择为计算机最自然的类型



**强制类型转换**

(typeName) value;

typeName (value)

static_cast<typeName> (value)



**auto声明**

auto让编译器根据初始值的类型推断变量的类型

vector<double>::iterator pv = v.begin();

auto pv = scores.begin();











### 3.5 总结















## 第四章 复合类型





### 4.1 数组



```c++
short months[12];    //creates array of 12 short
typeName arrayName[arraysize]; //arraySize表示元素数目
```





#### 4.1.1 程序说明



```
int yamcosts[3]= {20,30,5};  //只需要提供都好分割的值列表
```





#### 4.1.2 数组的初始化规则



```C++
//只有在定义数组时才能使用初始化
int cards[4] = {3,6,8,10};	//okay
int hand[4];				//okay
hand[4] = {5,6,7,9};		//not allowed
hand = cards;				//not allowed

//只要显式的将第一个元素初始化为0，其他元素都会被初始化为0
long totals[500] = {0};

short things[] = {1,5,3,8}；
```





#### 4.1.3 C++11 数组初始化方法



```C++
//初始化可省略等号
double earning[4]{1.0,2.0,3.0,4.0};

//可以不在大括号里添加任何元素，从而置零
unsigned int counts[10] = {};

//禁止缩窄转换
long plifs[] = {25,92,3.0};
```





### 4.2 字符串



```C++
//通过字符常量定义字符,必须记住加上空字符
char dog[3] = {'a','b','c'};		//not a string 
char cat[3] = {'a','b','\0'};		//a string

//字符串常量,""隐式的包括结尾的空字符
char bird[11] = "Mr.Cheeps"			//the \0 is understood

//确定存储字符串所需要的最短数组时，应将空字符计算在内

//字符串常量与字符常量不能互换
char shirt_size = 'S'		//'S'仅是83的另一种写法
char shirt_size = "S"		//"S"表示的是字符S和\0的支付穿，实际是将表示字符串的地址赋给了shirt_size，这是不允许的	
```





#### 4.2.1 拼接字符串常量



#### 4.2.2 在数组中使用字符串



```C++
const int Size = 15;
char name1[Size] = "C++owboy";
cout << strlen(name1);			//指出整个数组的长度
name1[3]='\0';
cout << name1;					//C++
```



#### 4.2.3 字符串输入



cin使用空白（空格、制表符和换行符）来确定字符串结束的位置，这意味着cin在获取字符串输入时只读取一个单词。



#### 4.2.4  每次读取一行字符串输入



```C++
//getlline()和get(),都读取一行的输入，直到换行符
//getline()将丢弃换行符,get()将换行符保留在输入序列中

//读入到一个包含20个元素的name数组中
cin.getline(name,20);
//通过换行符确定行位，但不保存换行符。存储字符串时，将用空字符\0代替换行符

cin.getline(name,20);
cin.getline(dessert,20);//a problem
//第一次调用后并不会丢弃换行符，第二次调用时便自动认定为是换行符，第二个get便直接到达行尾，不读取任何内容

//使用get来读取换行符
cin.getline(name,20);	//read first line
cin.get();				//read \n
cin.getline(dessert,20);//read second line
//组合函数
cin.get(name,20).get();
cin.getline(name,20).getline();
```



#### 4.2.5 混合输入字符串和数字



```C++
cin >> year; 				//输入1996\n
cin.getline(address,80);	//fail，无法输入
```

造成上述问题的主要原因是，cin将回车生成的换行符留在了输入队列里，cin,getline()读到了换行符

```C++
//修改方法
cin >> year;
cin.get();

//法2
(cin>>year).get()
```











### 4.3 string类



#### 4.3.1 C++11 字符串初始化

```C++
char first_date[]={"Le chanpon"};
string second_data = {"The elegant Plate"};
```





#### 4.3.2 赋值、拼接和附加

```c++
string str3;
str3 = str1+str2;
str1 +=str2;
```





#### 4.3.3 string类的其他操作

```c++
str1 = str2;
strcpy(charr1,charr2);

str1 +="paste";
strcat(charr1,"juice");

int len1 = str1.size();
int len2 = strlen(charr1); 
```





#### 4.3.4 string类I/O

```c++
string str1;
getline(cin,str);
//这里的getline不是类方法，为string类的一个友元函数
cin >> str;
```





4.3.5 其他形式的字符串字面值

```C++
wchar_t title[] = L"Cheif";
char16_t name[] = u"Felonia";
char32_t car[] = U"Humber";
```







### 4.4 结构简介



```C++
eg:
//结构体声明
struct infaltable
{
	char name[20];
	float volume;
	double price;
};
```



#### 4.4.1 在程序中使用结构

```C++
//初始化结构
inflatable guest =
{
	"Glorious",
	1.88,
	29.99
};

//访问结构体成员
guest.price
```





#### 4.4.2 C++结构初始化

不允许缩窄转换



#### 4.4.3 结构可以将string类作为成员





#### 4.4.4 其他结构属性



```c++
//可以使用赋值运算符将结构赋值给另一个同类型的结构
inflatable guest =
{
	"Glorious",
	1.88,
	29.99
};

inflatable choice;
choice = guest;

//完成定义结构，可以将变量名放在结束括号的后面
struct perks
{
    int key_number;
    char car[12];
}mr_smith,ms_jones;
```



#### 4.4.5 结构数组



```c++
inflatable gifts[100];
cin >> gifts[0].volume;
cout << gifts[99].price <<endl;

//初始化结构数组(用逗号分隔每个成员的值，并将这些值用花括号括起来)
inflatable guests[2]=
{
    {"Bambi",0.5,21.99},
    {"Godzilla",2000,565.99}
};
```







### 4.5 共用体





```c++
//共用体同时只存储一种类型
union one4all
{
	int int_val;
	long long_val;
	double double_val;
};

one4all pail;
pail.int_val = 15;
pail.double_val = 1.38;

//pail有时可以是int变量，有时又可以是double变量，每次只能存储一个值

//匿名共用体，其成员将成为相同地址处的变量
struct widget
{
    cahr brand[20];
    int type;
    union
    {
        long id_num;
        char id_char[20];
    };
};

widget prize;
cin >> prize.id_num;
cin >> prize.id_char;
```





### 4.6 枚举



```c++
//spectrum被称为枚举
enum spectrum {red,orange,yellow,green};
```

red、orange、yellow等作为符号量，对应整数0~3.这些常量叫做枚举量

```c++
//可以使用枚举名来声明变量
spectrum band;
//只可以将定义枚举使用的枚举量赋给这个变量
band = red;		//valid
band = 1000; 	//invalid,1000 is not an enumerator
```



枚举量是整型，可以被提升为int类型，但是int类型不能自动转换为枚举类型

```c++
int color = blue;	//valid
band = 3;			//invalid
color = 3 + red;	//valid,red converted to int
```



枚举没有定义运算符+

```c++
band = orange + red;	//not valid

//强制类型转换
band = spectrum(3);		//valid
band = spectrum(4003);	//超范围
```





#### 4.6.1 设置枚举量的值



```c++
enum bits{one = 1,two = 2, four = 4, eight = 8};	//指定的值必须为整数
//first默认为0，后面没有被初始化的枚举量将比前面的枚举量大1
enum bigstep {first,second= 100,third};
//可以创建多个值相同的枚举量
enum {zero,null = 0,one,uno = 1};
```





#### 4.6.2 枚举的取值范围

bigstep的最大枚举值是101，比这个数大的最小2幂值为128，其上限为127

最小枚举量为-6，比他小的，最大的2的幂为-8，下限为-7

```c++
enum bits{one = 1,two = 2, four = 4, eight = 8};
bits myflag;

myflag = bits(6);	//valid,because 6 is in bits range;
```







### 4.7 指针和自由存储空间



指针是一个变量，其存储的是值的地址，而不是值本身。

manly表示的是一个地址，而*manly表示存储在该地址处的值。



#### 4.7.1 声明指针和初始化指针



```c++
int *p_updates;

int higgens = 5;
int *pt = &higgens;
```





#### 4.7.2 指针的危险



```c++
long *fellow;
*fellow = 223323;
```

**一定要在对指针应用解除引用运算符（*）之前，将指针初始化为一个确定的、适当的地址。**





#### 4.7.3 指针和数字



```c++
//pt是int值的地址，并不意味着pt本身的类型是int
int *pt;
pt = (int*) 0xB80000;
```



#### 4.7.4 使用new来分配内存



```c++
int * pn = new int;
typeName * pointer_name = new typeName;
```

new 分配的内存块通常与常规变量声明分配的内存块不同。

变量的值被存储在被称为栈（stack）的内存区域中，new中被称为堆（sheep）或自由存储区域分配内存



#### 4.7.5 使用delete释放内存



```c++
int *ps = new int;
delete ps;

//不能使用delete来释放声明变量所获得的内存
int jugs = 5;
int * ps =&jugs;
delete ps;		//not allowed
//只能使用delete释放new分配的内存
```





#### 4.7.6 使用new来创建动态数组



通过声明创建数组，编译时即分配内存空间，成为静态联编；

通过new创建数组，为动态联编；

```c++
int * psome = new int[10];
delete [] psome;		//释放整个数组
```

- 不要使用delete释放不是new分配的内存
- 不要使用delete释放同一块内存两次
- 如果使用new[]为数组分配内存，则应使用delete[]释放







### 4.8 指针、数组和指针算术





#### 4.8.1 程序说明



C++将数组名解释为数组第一个元素的地址

```c++
double * pw = wages;
wages = &wages[0];

//sizeof运算符得到的是数组的数组的长度，对指针应用得到的是指针的长度
sizeof(wages) =24;
sizeof(pw) = 4;
```





#### 4.8.2 指针小结



指针算术

```c++
//c++允许将指针和整数相加。加一的结果等于原地址值加上指向对象占用的总字节数
int tacos[10];
int *pt = tacos;
pt= pt+1;
```

动态联编和静态联编

```c++
//使用数组声明来创建数组，采用静态联编
int tacos[10];
//使用new[]运算符来创建数组时，将采用动态联编，应使用delete[]释放内存
int *pt =new int[10];
delete [] pt;
```

数组表示法和指针表示法

```c++
//使用方括号数组表示法等同于对指针接触引用
int *pt =new int[10];
*pt = 5;
pt[0] = 6;

int coats[10];
*(coats + 4)= 12;
```







#### 4.8.3 指针和字符串

```c++
//在多个c++表达式中，char数组名，char指针以及用引号括起的字符串常量都被解释为字符串第一个字符的地址
const char * bird = "wren";
//"wren"实际表示的是字符串的地址，因此是将"wren"的地址赋给了bird地址
//字符串字面值是常量，所以使用关键字const
```







#### 4.8.4 使用new创建动态结构







#### 4.8.5 自动存储、静态存储和动态存储



1.自动存储

自动变量通常存储在栈中，这意味着执行代码块的时候，其中的变量将依次加入栈中，而在离开代码块时，将按相反的顺序释放变量



2.静态存储

静态存储是整个程序执行期间都存在的存储方式。使变量成为静态的两种方式：在函数外声明他；使用关键字static。



3.动态存储

new和delete，将变量存储在自由存储空间或堆中



### 4.10 数组的替代品





#### 4.10.1 vector

vector<int> v(n);



#### 4.10.2 array

array<int,5> ai;



array对象和数组都存储在内存区域即栈中。而vector对象存储在堆中。

中括号表示法无法禁止非法索引，.at()可以。

























### 复习题

```c++
1. 
char actor[30];
short betsie[100];
float chuck[13];
long double dipesa[64];
2.
    array<char,30> actor;
3.
    int a[5]={1,3,5,7,9};
4.
    even = a[0]+a[5];
5.
    float ideas[5];
    cout << ideas[1];
6.
    char s[15]="cheeseburger";
7.
    string s="WaldorfSalad";
8.
    struct fish
    {
        string kinds;
        int counts;
        double length;
	}
9.
    fish s1={"石斑",10,10};
10.
    
```





















## 第五章 循环和关系表达式







### 5.1 for循环



```c++
for(int i= 0;i<n;i++)

for(int i=0;i<n;++i)
```

用户定义前缀函数，将值加1，然后返回结果

用户定义后缀函数，首先复制一个副本，将其加1，然后将复制的副本返回

因此对于类而言，前缀版本的效率比后缀版本高



#### 5.1.8 递增、递减运算符和指针

前缀递增、前缀递减和解除引用运算符的优先级相同，以从右到左的方式进行结合。

后缀递增和后缀递减优先级仙相同，但比前缀运算符的优先级高，从左到右结合。

```c++
double x = *++pt;	//	*被应用于递增后的pt
++*pt;				// 意味着先取得pt指向的值，然后再加1
x = *pt++;
```







### 5.2 while 循环



#### 类型别名



```c++
//预处理器
#define BYTE char 	//用BYTE替换所有的char

//使用关键字typedef
typedef typeName aliasName;
//将byte_pointer声明为char指针
typedef char * byte_pointer;
```









### 5.3 do-while 循环







### 5.4 基于范围的for循环（C++）



```c++
double prices[5] = {4.99,10.99,6.87,7.99,8.49};
for(double x : prices)
	cout <<x <<std::endl;
```

```c++
//修改数组元素
for(double &x:prices)
    x = x*0.8;

for(int x : {3,5,2,8,6})
    cout <<x<<"";
```





### 5.5 循环和文本输入



#### 5.5.1 使用原始的cin进行输入

cin在读取char值时，与读取其他类型一样，cin将忽略空格和换行符。

发送给cin的输入被缓冲，只有用户按下回车键后，它的输入才会发给程序。





#### 5.5.2 使用cin.get(char)进行补救

```c++
while(ch!='#')
{
	cout << ch;
	++count;
	cin.get(ch);
}
//将全部字符计算在内，其中包括空格。
```





#### 5.5.4 文件尾条件

检测文件尾(EOF)

如果检测到EOF，则cin.eof()将返回bool值true，否则返回false。

同样如果检测到eofbit或failbit，则fail()成员函数返回true，否则返回false

```
while(cin.fail()==false)
{
	cout << ch;
	++count;
	cin.
}
```







### 5.6 嵌套循环和二维数组



```c++
//将cities声明为一个char指针数组
const char* cities[5]=
{
    "ab","cd","ef","ff","gg"
};

//char数组的数组
char cities[5][25]=
{
     "ab","cd","ef","ff","gg"
};
```















## 第六章 分支语句和逻辑运算



### 6.1 if 语句





### 6.2 逻辑表达式

|| 运算符是个顺序点。也就是说，先修改左侧的值，再对右侧的值进行判定

C++逻辑or和逻辑AND运算符的优先级都低于关系运算符。

x  > 5 && x < 10 被解释为(x>5)&&(x<10)

!运算符的优先级高于所有的关系运算符和算术运算符。

逻辑AND运算符优先级高于逻辑or运算符

age > 30 && age <45 || weight > 300 被解释为 (age > 30 && age < 45) || weight > 300







### 6.6 break和continue语句

continue语句导致程序跳过循环体的剩余部分，但不会跳过循环的更新表达式。

**goto语句**

```c++
if(ch == 'p')
	goto pairs;
cout << ;

pairs: cout << endl;
```









### 6.7 读取数字的循环

```c++
while(!(cin>>golf[i]))
{
    cin.clear;
    while(cin.get()!='\n')
        continue;
    cout << "please enter a number"
}
```

用户输入88，cin>>golf[i]返回true，用户输入must i?，cin表达式为false，!(cin>>golf[!])为true，进入while循环，clear()重置输入，cin.get读取行尾之前的所有输入，从而删除这一行的错误输入。







### 6.8 简单文件输入\输出



使用cin进行输入时，输入一开始都是字符数据--文本数据



#### 6.8.2 写入到文本文件中

```c++
ofstream outFile;
outFile.open("fish.txt");
double wt=125.8;
outFile << wt;
outFile.close();
```



```c++
//接受字符串风格的参数
ofstream fout;
char filename[50];
cin >> filename;
fout.open(filename);
char line[81] = "Objects are closer than they apear";
fout << line <<endl;
fout.close();
```

默认情况下，open()将首先截断该文件，即将其长度截断为零，丢弃原有的内容，将新的输出加入到该文件中。



#### 6.8.3 读取文本文件

```c++
ifstream inFile;
inFile.open("bowling.txt");
//如果文件被成功打开，is_open()将会返回true
if(!inFile.is_open())
{
    exit(EXIT_FAILURE);
}
double wt;
inFile >> wt;
while(inFile.good())
{
    inFile>>value;
}
```



```c++
ifstream fin;
char filename[50];
cin >> filename;
fin.open(filename);
char line[81];
fin.getline(line,81);
```





## 第七章 函数--C++的编程模块



### 7.1 函数基本知识

- 函数定义
- 函数原型
- 调用函数



#### 7.1.1 定义函数



没有返回值的

```c++
void functionName(parameterList)
{
	statement(s);
	return;
}
```

有返回值的

```c++
typeName functionName(parameterList)
{
	statement(s);
	return;
}
```



#### 7.1.2 函数原型

函数原型不要求提高变量名，有类型列表就足够了

```
dobule cube(double x);
void cheers(int);
```





### 7.2 函数参数和按值传递



argument表示实参，parameter表示形参



### 7.3 函数和数组

为了使函数通用，不仅要传递数组还要传递数组长度

```c++
int sum_arr(int arr[],int n);
int sum_arr(int *arr,int n);
//int *arr和int arr[],当且仅当用于函数头或函数原型中，其含义才是相同的
```

```
arr[i] == *(arr+i);
```

将数组作为参数传递给函数，是将数组的位置，元素的种类以及元素数目提交给函数。

传递常规变量时，函数将使用变量的拷贝，但传递数组时，函数将使用原来的数组



**数组处理函数的常用编写方式**

```c++
void f_modify(double ar[],int n);
void f_no_change(const double ar[],int n);
```



**指针和const**

```c++
//常规变量的地址赋给指向const的指针
int age = 39;
const int *pt = &age;
```

可以通过age变量来修改age的值，但不能使用pt指针来修改它。

可以将const变量的地址赋给指向const的指针

不可以将const的地址赋给常规指针



```c++
//常规变量的地址赋给指向const的指针
int age = 39;
const int *pt = &age;
```

const能防止修改pt指向的值，但是不能防止修改pt的值，可以将新的地址赋给pt

```c++
int sloth = 3;
const int *ps =&sloth;
int *const finger = &sloth
```

finger只能指向sloth，但允许使用finger来修改sloth的值

finger和*****ps都是const，而*****finger和ps不是

```c++
double trouble = 2.0E30;
const double * const stick = &trouble;
```

stick只能指向trouble，而stick不能用来修改trouble



### 7.4 函数和二维数组



```c++
//由四个int组成的数组的指针
int sum(int (*arr)[4],int size);
//此指针
int *arr[4];
//另一种格式
int sum(int arr[][4],int size);
```

arr是指针不是数组

```c++
arr+r == arr[r];
arr[r][c] == *(*(arr+4)+c);
```





### 7.5 函数和C-风格字符串



#### 使用字符串作为参数传递给函数

使用字符串作为参数传递给函数，表示字符串的方式有三种：

```c++
//字符常量
char apple[10]={'a','c','\0'};
//字符串常量
char ghost[15]="happy";
//char指针
char *str = "happy";
```

字符串作为参数产地，实际传递的是字符串的第一个字符地址





#### 返回字符串的函数

函数无法返回一个字符串，但可以返回字符串的地址

```c++
char * buildstr()
{
    char *ptr;
    return ptr;
};
```



### 7.6 函数和结构

结构与数组名不同，结构只是结构的名称，想要获得结构的地址，必须使用地址运算符&

```c++
struct rect
{
	double x;
    double y;
}

void show_rect(const rect * pda) {}
//调用
rect rect1;
show_rect(&rect1);
```



```c++
struct rect
{
	double x;
    double y;
}

rect rplace;
while(cin>> rplace.x >> rplace.y)
{
    //cin被用于测试表达式是否输入成功，若输入了q，cin知道q不是数字，从而返回false
}
```



### 7.7 函数与string对象

```c++
void display(const string sa[],int n)
{
    for(int i=0;i<n;i++)
    {
        cout<<sa[i];
    }
}
```





### 7.8 函数与array对象

```c++
array<double,4> expenss;
void show(std::array<double,4> da);
void fill(std::array<double,4> * pa);
{
    //第i个
    cin>>(*pa)[i];
}
show(expenss);
fill(&expenss);
```



### 7.9 递归

```c++
void recurs(argumentlist)
{
    statements1;
    if(test)
    {
        recurs(arguments);
    }
    statements2;
}
//recurs()进行了5次递归调用，第一个statements1按函数顺序执行5次，statements2相反顺序执行5次
```





## 第八章 函数探幽



### 8.1 C++内联函数



函数调用指令：函数调用后立即存储该指令的内存地址，将函数参数复制到堆栈中，跳到标记函数起点的内存单元，执行函数代码

C++内联函数将使用相应的函数代码来替换函数调用，内联函数的速度比常规函数稍快，但代价是需要占用更多的内存

函数声明和定义前应加上关键字inline





### 8.2 引用变量



```c++
int rats =101;
int & rodents = rats;
int * prats = &rats;
//rodents和*prats可以和rats互换
//&rodents和prats可以和&rats互换
```

必须在引用声明时将其初始化

```c++
int rat;
int & rodent;
rodent = rat;//invalid
```



##### 将引用作为函数参数

```c++
void swapr(int &a,int &b);
void swapp(int *p,int*q);
swapr(wallet1,wallet2);
swapp(&wallet1,&wallet2);
```



##### 引用的特别之处

```c++
void swapr(int &a,int &b);
long a=3,b=4;
swapr(a,b);
```

由于类型不匹配，因此编译器会创建两个临时int临时变量，然后交换临时变量的内容，而保持a和b不变



基类对象的引用可以指向派生类对象，调用基类引用作为参数的函数时，调用该函数可以将基类对象作为参数也可以将派生类对象作为参数。

```c++
void file_it(ostream & os);
file_it(fout);
file_it(cout);
//参数os(ostream)
//cout(ostream)
//fout(ofstream)
```



##### 如何使用引用参数

使用引用的原因：

- 程序员能够修改调用函数中的数据对象。
- 通过传递引用而不是整个数据对象，可以提高程序的运行速度。



对于使用传递的值而不作修改的函数。

- 如果数据对象很小,如内置数据类型或小型结构,则按值传递。
- 如果数据对象是数组,则使用措针,因为这是唯一的选择,并将指针声明为指向 const的指针。
- 如果数据对象是较大的结构,则使用 const指针或 const引用,以提高程序的效率。这样可以节省复制结构所需的时间和空间。



对于修改调用函数中数据的函数

- 如果数据对象是内置数据类型,则使用指针。如果看到诸如fxit(&x)这样的代码(其中x是int),则很明显,该函数将修改x如果数据对象是数组,则只能使用指针。
- 如果数据对象是结构,则使用引用或指针。
- 如果数据对象是类对象,则使用引用。





### 8.3 默认参数





对于带参数列表的函数，必须从右往左添加默认值

```c++
char * left(const char* str,int n = 1); 		//valid
int choico(int n,int m=6,int j);				//invalid
```

只有原型指定了默认值，函数定义与没有默认参数时相同

```c++
char * ps = left(sample,4);
char * pn = left(sample);

char * left(const char* str,int n)
{

}
```









### 8.4 函数重载



函数重载的关键是函数的参数列表--称为函数特征标

```c++
void print(long l);
void print(int i);
```



```c++
double cube(double x);
double cube(double &x);
//虽然特征标看起来不同，但是从编译器的角度来看将把类型引用和类型本身视为同一特征标
```



const与非const变量

```c++
void dabble(char * bits);
void drivel(const char * bits);
//dabble只与非const参数的调用匹配
//drivel可以与带const或非const的参数匹配
```



特征标而非函数类型使得可以对函数进行重载

```c++
long gronk(int n,int m);
int gronk(int n,int m);
//无法重载，非法的，返回类型可以不同，但是特征标必须不同
```



#### 左值右值！！！！







### 8.5 函数模板



```c++
//函数声明
template<typename T>
void swap(T &a,T &b)

//函数定义
template <typename T>
void swap(T &a,T &b)
{
    T temp;
    temp = a;
    a = b;
    b = temp;
}
```



**重载模板**

```c++
template<typename T>
void swap(T &a,T &b)

template<typename T>
void swap(T *a,T *b,int n);
```



**显示具体化**

函数使用优先级：非模板函数，显式具体化模板函数，模板函数

```c++
//非模板函数
void swap(job &,job &);

//模板函数
void swap(T &,T &);

//显式具体化模板函数
template<> void swap<job>(job&,job&);
template<> void swap(job&,job&);
```



**实例化与具体化**

实例化：编译器使用模板为特定类型生成函数定义

```c++
void swap <int> (int,int)
```

具体化：模板无法处理所有函数，引入具体化

```c++
template<> void swap<job>(job&,job&);
template<> void swap(job&,job&);
```



### 8.7 复习题



8)

```c++
template<> box Volume<box>(box& b1,box&b2)
{
    return b1.volume>b2.volume?b1:b2;
}
```



### 8.8 编程练习











## 第九章 内存模型和名称空间



### 9.1 单独编译



C++编译器既编译程序，又管理链接器。若只修改一个文件，则可以只重新编译该文件，然后将它与其他文件编译版本链接起来。



在包含头文件时，如果文件名包含在尖括号中<apple.h>，则C++编译器将在存储标准头文件的主机系统的文件系统中查找。如果文件名包含在双引号中，则编译器将首先查找工作目录或源代码目录。故在包含自己的头文件时，应使用引号而不是尖括号。



**头文件管理**

为了避免多次包含一个头文件，基于预处理器编译指令#ifndef

使用方法：

```c++
#ifndef COORDIN_H_
#define COORDIN_H_
//place include file
#endif
```





### 9.2 存储持续性、作用域和链接性

C++11使用4种不同的方案来存储数据

- 自动存储持续性：在函数定义中声明变量的存储持续性为自动的
- 静态存储持续性：在函数定义外定义的变量和使用关键字static定义的变量的存储持续性都为静态的
- 线程存储持续性：如果使用关键字thread_local声明，则生命周期与线程一样长
- 动态存储持续性：用new分配的内存将一直存在，直至使用delete释放，成为自由存储或堆



#### 作用域和链接

链接性描述了名称如何在不同单元间共享。链接性为外部的名称可在文件间共享，链接性为内部的名称只能在一个文件的函数共享。



#### 自动存储持续性

在函数声明的函数参数和变量的存储持续性为自动，作用域为局部，没有链接性。



#### 静态持续变量

C++为静态持续性变量提供了3种链接性：外部链接性，内部链接性和无链接性

外部链接性：必须在代码块外面声明它

内部链接性：在代码块外面声明并使用static限定符

没有链接性：在代码块内声明它，并使用static限定符

```c++
int global = 1000;				//external linkage
static int one_file = 50;		//internal linkage
int main()
{
    
}
void funct1(int n)
{
    int llama = 0;
    static int count = 0;		//no linkage
}
//在funct1()中声明的变量count作用域为局部的，没有链接性，但是与llama不同，即使没有被执行，count也留在内存中。
//由于one_file的链接性为内部的，因此只能在包含上述代码的文件中使用它
//由于global的链接性为外部，因此可以在程序的其他文件中使用它。
```





#### 静态持续性、外部链接性



##### 单定义规则

变量只能有一次定义。有两种声明：**定义声明**和**引用声明**

引用声明使用关键则extern，且不进行初始化

单变量定义规则并不意味着不能有多个变量名称相同

```c++
//file01.cpp
extern int cats = 20;
int dogs = 22;

//file02.cpp
extern int cats;
extern int dogs;
```





#### 静态持续性、内部链接性

如果文件定义了一个静态外部变量，其中与另一个文件中声明的常规外部变量相同，则该文件中静态变量将隐藏常规外部变量

```c++
//file1
int errors = 20;

//file2
static int errors =5;
cout << errors;//uses errors defined in file2
```





#### 静态存储持续性、无链接性

在代码块中使用static时，将导致局部变量的存储持续性为静态的。如果初始化了静态局部变量，则程序只在启动时进行一次初始化，以后再调用函数时，将不会像自动变量那样再次被初始化了。



#### 函数和链接性

使用关键字static将函数的链接性设置为内部的

```c++
static int private(double x)
static int private(double x)
{
    
}
```

函数只在这个文件中可见，可以在其他文件中定义同名的函数。

内敛函数不受这项规则的约束，这允许程序员能够将内敛函数的定义放在头文件中。



#### 存储方案和动态分配

编译器使用三块独立的内存：一块用于静态变量，一块用于自动变量，另外一块用于动态存储

```c++
float *p_fess = new float[20];//20个float变量，80字节
//另一个文件中使用声明
extern float * p_fess;
```



使用new运算符进行初始化

```c++
//内置标量类型,使用括号
int *pi = new int(6);	//*Pi set to 6
double *pd = new double(99.99);	//*pd set to 99.99

//单值变量也可以使用大括号列表初始化
int *pi = new int{6};	//*Pi set to 6
double *pd = new double{99.99};	//*pd set to 99.99

//初始化常规结构和数组，使用大括号的列表初始化
struct where {double x;double y; double z;};
where * one = new where{1.1,2.2,3.3};
int *ar = new int[4]{2,4,6,8};


```





## 第十章  对象与类





### 10.2 抽象和类



类规范由两个部分组成：

1）类声明：以数据成员的方式描述数据部分

2）类方法定义：描述如何实现类成员函数

C++将接口（类定义）放在头文件中，并将实现（类方法的代码）放在源代码文件中

```C++
#ifndef __STOCK00__H__
#define __STOCK00__H__

#include<string>
using namespace std;

class Stock
{
  private:
    string company;
    long shares;
    double share_val;
    double total_val;
    void set_tot() {total_val = shares * share_val};
    
  public:
    
    void acquire(const string &co,long n,double pr);
    void buy(long num,double price);
    void sell(long num,double price);
    void update(double price);
    void show();
};

#endif
```





**访问控制**

可以直接访问公有部分；

访问私有部分，只能通过公有成员函数来访问对象的私有成员；

数据项通常放在私有部分，组成类接口的成员函数放在公有部分；

类对象的默认访问控制为私有的，隐式private



#### 实现类的成员函数

- 定义成员函数时，使用作用域::来标识函数所属的类
- 类方法可以访问私有组件

```c++
void Stock::update(double price);
```

stock类的其他成员函数不必使用作用域解析运算符，就可以使用update()方法



```c++
//Stock00.cpp
#include<iostream>
#include "stock.h"

void Stack::acquire(const string &co,long n,double pr)
{
    company = co;
    if(n<0)
    {
        cout << "Number of shares can't be nagative"
            << company << "shares set to 0.\n";
    }
    else
        shares = n;
    share_val = pr;
    set_tot();    
}
```



**内联方法**

- 其定义位于类声明中的函数都将自动成为内联函数，stock::set_tot()是一个内联函数
- 类声明之外定义成员函数，并使其成为内联函数

```c++
class Stock
{
	private:
		void set();
};
inline void Stock::set();
{
    total_val = shares* share_val;
}
```





### 10.3 类的构造函数和析构函数



#### 声明和定义构造函数

```c++
class Stock
{
	//声明构造函数
	Stock();
};

//定义构造函数
Stock::Stock()
{

}
```





#### 使用构造函数

显式使用

```c++
Stock food  = Stock("World");
```

隐式调用构造函数

```c++
Stock garment("Furry");
```

使用new动态分配内存

```c++
Stock *pstock = new Stock("happy");
```



#### 默认构造函数

**默认构造是在未提供显式初始值时，用来创造对象的构造函数**

如果没有提供任何构造函数，编译器将会提供默认构造函数。然而如果提供了非默认构造函数（Stock(const char*co)）,但没有提供默认构造函数，则Stock stock1的声明将会出错。

**定义默认构造的方式有两种：**

- **给已有构造函数的所有参数提供默认值**

```c++
Stock(const string & co = "Error" , int n = 0, double pr = 0.0);
```

- **通过函数重载来定义构造没有参数的构造函数**

```
Stock();
```

**由于只有一个默认构造函数，因此不要同时采用两种方式**

```c++
//使用默认构造，声明对象变量
Stock first;
Stock first = Stock();
Stock *p = new Stock;
//未使用默认构造
Stock first("happy");
//声明一个返回值为类的函数
Stock second();
```





#### 析构函数

```c++
Stock::~Stock()
{
    
}
```

静态存储对象，则析构函数将在程序结束时自动被调用

自动存储对象，析构函数将在程序执行完成代码块时自动被调用

如果是通过new创建的，将贮存在栈内存或自由存储区中，使用delete来释放内存



```c++
Stock stock2 = Stock("happy");
stock1 = Stock("Node");
```

第一条语句是初始化，他创建有指定值的对象，可能会创建临时对象，也可能不会

第二条语句是赋值语句，赋值语句使用构造函数总会导致在赋值前创建一个临时对象。



**C++11列表初始化**

```c++
Stock hot_tip = {"happy"};
Stock jock{"happy"};
Stock temp{};
```



**const成员函数**

```c++
const Stock land = Stock("happy");
land.show(); 	//failed
```

**show()的代码无法确保调用对象不被修改**

解决方法：将const关键字放在函数的括号后面

```c++
//函数声明
void show() const;
//函数定义
void stock::show() const;
```

只要类方法不修改调用对象，就应将其声明为const



### 10.4 this指针

```c++
const Stock & topval(const Stock & s)const
```

函数隐式的访问一个对象，显式的访问另一个对象

```c++
const Stock & Stock::topval(const Stock & s) const
{
    if(s.total>this->total)
        return s;
    else
        return *this;
}
```





### 10.5 对象数组



当程序创建未被显式初始化的对象时，使用默认构造

```c++
stock mystuff[4];
```

可以使用构造函数来初始化数组元素。使用标准格式对数组进行初始化，用括号括起，用逗号分离

```c++
const int STKS = 4;
Stock stock[STKS] =
{
    Stock("happy"),
    Stock("birthday"),
    Stock("end"),
    Stock("ok")
};
```

可以对不同元素使用不同的构造函数

```c++
//由于只声明了四个元素，因此余下6个元素为默认构造进行初始化
const int STKS = 10;
Stock stock[STKS] =
{
    Stock("happy"),
    Stock("birthday",25),
    Stock(),
    Stock("ok")
};
```



### 10.6 类作用域



使用类成员名时，必须根据上下文使用**直接成员运算符(.)**、**间接成员运算符(->)**或**作用域解析运算符(::)**



#### **作用域为类的常量**

```c++
class Bakery
{
private:
    const int Months = 12;  	//declare a constant? FAIL
    dobule consts[Months];
    ...
}
```

声明类只是描述了对象的形式。在创建对象前，将没有用于存储值的空间。

改进方法如下：

- 声明一个枚举。**在类声明中的枚举作用域为整个类**

```c++
class Bakery
{
private:
    enum { Months = 12};  	
    dobule consts[Months];
    ...
}
```

- **使用关键字static,**将该常量与其他静态变量存储在一起，一个Months常量被所有Bakery对象共享

```c++
class Bakery
{
private:
    static const int Months =12;
    dobule consts[Months];
    ...
}
```



#### **作用域内枚举(C++ 11)**

```c++
enum egg {small,medium,large,jumbo};
enum t_shrit {samll,medium,large,Xlarge};
```

egg small和t_shirt small位于相同的作用域内，他们将发生冲突

```c++
enum class egg {small,medium,large,jumbo};
enum class t_shrit {samll,medium,large,Xlarge};
egg choice = egg::large;
t_shirt Floyd = t_shirt::large;
```





### 10.7 抽象数据类型



```c++
//stack.h
#ifndef __STACK_H__
#define __STACK_H__

typedef unsigned long Item;

class Stack
{
private:
    enum {MAX = 10};
    Item items[MAX];
    int top;
public:
    Stack();
    bool isempty() const;
    bool isfull() const;
    bool push(Item &item);
    bool pop(Item &item);
};
#endif
```

```c++
//stack.cpp
#include "stack.h"
Stack::Stack()
{
}

bool Stack::isempty() const
{
    return top==0;
}
    
bool Stack::isfull() const
{
 	return top==MAX;      
}
          
bool Stack::push(Item &item)
{
    if(top<MAX)
    {
        items[top++] = item;
        return true;
    }else
        return false;
}
    
bool Stack::pop(Item &item)
{
    if(top>0)
    {
        item = items[--top];
        return true;
    }else
        return false;
}

```



```c++
//stacker.cpp
#include<iostream>
#include<cctype>
#include"stack.h"

using namespace std;
int main()
{
    Stack st;
    unsigned long po;
    char ch;
    cout <<"Please enter A or a to add a purchase order\n"
        <<"P to process a PO\n"
        <<"or Q to quit\n";
    while( cin>>ch && toupper(ch)!='Q')
    {
        while(cin.get()!='\n')
            continue;
        switch(ch)
        {
            case A:
            case a:	cout << "Enter a PO number to add:";
                	cin >> po;
                	if(st.isfull())
                    {
                        cout << "Stack is FUll"<<endl;
                    }else
                    {
                        st.push(po);
                    }
                	break;
            case P:
            case p:	if(st.isempty())
            		{
                		cout <<"stack is empty"<<endl;
            		}else{
						st.pop(po);
                		cout<<"po#"<<po<<"poped\n";
            		}  
        }
        cout <<"Please enter A or a to add a purchase order\n"
        <<"P to process a PO\n"
        <<"or Q to quit\n";
    }
    cout <<"Bye"<<endl;
    return 0;
}
```







## 第十一章 使用类









### 11.1 运算符重载



C++允许将运算符重载扩展到用户定义的类型

```c++
operator op(argument list)
```

operator +()重载+运算符

operator *()；opertor []();

```c++
op3 = op1 + op2;
//等价于
op3 = op1.operator+(op2)
```





### 11.2  计算时间：一个运算符重载示例



**警告**：不要返回指向局部变量或临时对象的引用。函数执行完毕后，局部变量和临时对象将消失，引用将指向不存在的数据。

```c++
Time Sum(const Time & t) const;
//+运算符重载
Time operator+(const Time & t)const;
//函数定义
Time Time::operator+(const Time & t) const
{
    
}
```

```c++
//使用方法
total = coding.operator+(fixing);
total = coding+fixing;
```

```c++
//将两个以上对象相加
t4=t1+t2+t3;
t4=t1.operator+(t2+t3);
t4=t1.operator+(t2.operator+(t3));
```



#### 重载限制

重载后的运算符必须至少有一个操作数是用户定义的类型

使用运算符时不能违反运算符原来的句法规则

同样不能修改运算符的优先级

不能创建新运算符

不能重载的运算符：

- sizeof:sizeof运算符.
- :成员运算符。
- .*:成员指针运算符。
- :作用域解析运算符。
- ?:条件运算符。
- typeid:一个RTTI运算符。
- const cast:强制类型转换运算符。
- dynamic_cast:强制类型转换运算符.
- reinterpret_cast:强制类型转换运算符。
- static_cast:强制类型转换运算符。

**某些运算符只能通过成员函数进行重载： =  （） [ ]  ->**





### 11.3 友元



C++提供了另外一种形式的访问权限：友元

友元函数；友元类；友元成员函数

通过让函数成为类的友元，可以赋予该函数与类的成员函数相同的访问权限



```c++
//*重载
A = B * 2.75;
A = B.operator*(2.75);
//方法一：使用非成员函数
A = 2.75 * B;
A = operator*(2.75,B);
//该函数原型
Time operator*(double m,const Time&t);
```

非成员函数不能直接访问类的私有数据



#### 创建友元



第一步将原型放在类声明中，并在原型声明前加上关键字friend:

```c++
friend Time operator*(double m,const Time&t);
```

虽然其在类声明中声明，但是他不是成员函数，但是它拥有和成员函数一样的访问权限

不需要使用Time::限定符，不要在定义中使用关键字friend。其定义如下：

```c++
Time operator*(double m,const Time&t)
{
	return t*m;
}
```



#### 常用的友元：重载<<运算符



**法1：**

使自定义类使用cout，必须使用友元函数

```c++
Time trip;
cout << tirp;
```

```c++
//通过友元函数重载运算符
//cout实质是ostream的一个对象
ostream & operator << (ostream & os,const Time &t)
{
	os<<t.hours<<"hours"<<t.minutes<<"minutes";
    return os;
}
```



**法2：**

```c++
cout << "Trip time:"<<Trip<<"Tuesday";
```

ostream类将operator<<()函数实现返回一个指向ostream对象的引用

```c++
ostream & operator << (ostream & os,const Time &t)
{
	os<<t.hours<<"hours"<<t.minutes<<"minutes";
    ret
}
```



### 11.4 重载运算符：采用成员函数或非成员函数

```c++
//成员函数
Time operator+(const Time& t1) const;
//非成员函数
friend Time operator+(const Time&t1,const Time&t2) ;
```





### 11.6 类的自动转换和强制类型转换



**内置类型转换**

```c++
long count = 8;		//int converted to long
double time = 11;	//int converted to double
int side = 3.33; 	//double converted to int
```

enum {Lbs_Per_Ston = 14};等价static const int Lbs_Per_Stone = 14;



**自定义类转换**（内定类型转换为自定类型）

构造函数只能从某种类型到类类型的转换

将double类型的值转换为Stonewt类型

```c++
Stonewt myCat;
myCat = 19.6;
//利用构造函数
Stonewt(double lbs);
```

只有接受一个参数的构造函数才能作为转换函数。构造函数有两个参数，因此不能用来转换类型

```c++
Stonewt(int stn,double lbs);
```

如果第二个参数提供默认值，它便可用于转换int

```c++
Stonewt(int stn,double lbs=0);
```

可以使用关键字explicit，关闭自动类型转换

```c++
explicit Stonewt(double lbs);
```

```c++
//关闭了隐式转换，仍然允许显式转换
Stonewt myCat;
myCat = 19.6;	//	fail
myCat = Stonewt(19.6);
myCat = (Stonewt)19.6;
```

```c++
//int转换为double，然后使用Stonewt(double)
Stonewt Jumbo(7000);
Jumbo = 7300;
//若Stonewt存在Stonewt(double)和Stonewt(long)，则int可被转换为long和double，存在二义性
```



#### 转换函数

转换函数是将自定类转换为标准类型

```c++
Stonewt wolfe(285.7);
double host = double(wolfe);
double thinker = (double) wolfe;
```

转换函数：operator typeName();

- 转换函数必须是类方法
- 转换函数不能指定返回类型
- 转换函数不能有参数

```c++
//声明
operator double() const;
operator int() const;
//定义
Stonewt::operator double() const
{
    return pounds;
}
Stonewt::operator int() const
{
	return int (pounds+0.5);
}
```

可以将转换运算符声明为显式的

```c++
explicit operator int() const;
explicit operator double() const;
```





### 11.7 总结

- 利用友元函数访问私有类成员，需要在类中声明，并在声明前加friend

- 运算符重载，operator op(argument-list)

- 定义<<运算符，要让ostream对象成为第一个操作数，需要将运算符函数定义为友元，并且返回ostream&

  ```c++
  ostream & operator << (ostream & os,const c_name & obj)
  {
  	os << ...;
  	return os;
  }
  ```

- 类和基本类型之间进行转换。例如string类，它包含一个char*值作为其唯一参数的构造函数，则可以使用下面的语句

```c++
string bean;
bean = "points";
```

- 在构造函数前加关键字explicit，只能用于显示转化

```c++
bean = Sting("points");
```

- 要将类对象转换为其他类型，必须定义转换函数

```c++
operator typeName();
vector::operator typeName()
{
	return typeName_val;
}
```







## 第十二章 类和动态内存分配



### 12.1 动态内存和类

```c++
//stringbad.h
#include <iostream>
#ifdef STRENGBAD_H__
#define STRENGBAD_H__

class StringBad
{
private:
    char * str;
    int len;
    static int num_strings;
public:
    StringBad(const char*s);
    StringBad();
    ~StringBad();
    friend std:ostream & operator<<(std::ostream &os,const StringBad& st);
}

#endif
```

**使用char指针表示姓名，意味着没有为字符串本身分配存储空间，需在构造函数总使用new来为字符串分配空间。**

num_strings成员为静态存储类。无论创建多少个对象，**只创建一个静态类变量副本**。**所有对象共用一个静态成员。**

```c++
//stringbad.cpp
#include"stringbad.h"

int StringBad::num_string=0;

StringBad::StringBad(const char*s)
{
 	len = std::strlen(s);
    str = new char[len+1];
    std::strcpy(str,s);
    num_strings++;
}

StringBad::StringBad()
{
    len = 4;
    str = new char[4];
    std::strcpy(str,"C++");
    num_strings++;
}

StringBad::~StringBad()
{
    --num_strings;
    delete[]str;
}

std::ostream & operator<<(std::ostream &os,StringBad & st)
{
    os<<st.str;
    return os;
}
```

- **静态成员**num_strings的值初始化为0.**一般是需要在类声明之外使用单独的语句来进行初始化。初始化是在方法文件中，而不是在类声明中进行的。**
- 某些例外（静态成员是整型或枚举型const），则可以在类声明中初始化

```c++
StringBad sports"headline";
StringBad sailor = sports;
//等效于下面的语句
StringBad sailor = StringBad(sports);
```

对应的构造函数原型如下：

```c++
StringBad(const StringBad&);
```

当使用一个对象来初始化另一个对象时，编译器自动生成拷贝构造函数

#### 特殊成员函数：C++自动提供成员函数

**默认构造函数**

```c++
Klunk::Klunk(){}
Klunk::Klunk(int n=0){}
```

**默认析构函数**

```c++
Klunk::~Klunk(){}
```

**拷贝构造函数**

```c++
Class_Name(const Class_Name &)
StringBad(const StringBad &);
```

```c++
//何时调用
StringBad ditto(motto);
StringBad metoo = motoo;
StringBad also = StringBad(motoo);
StringBad *pStringBad = new StringBad(motoo);
```

当函数按值传递对象或函数返回对象是，都将使用拷贝构造函数

- **默认的拷贝构造函数逐个复制非静态成员（**成员复制也称为浅复制），**对于某些使用new初始化的指针成员，仅能复制指向字符串的指针。**
- **深度赋值（显示拷贝构造）**：拷贝构造函数应当复制字符串并将副本的地址赋给str成员，而不仅仅是复制字符串的地址。

```c++
StringBad::StringBad(const StringBad&st)
{
	num_string++;
	len = st.len;
	str = new char[len+1];
	std::strcpy(str,st.str);
}
```

**赋值运算符**

C++默认允许对象赋值，通过重载赋值运算符实现的

```c++
StringBad & operator=(StringBad& str);
StringBad & StringBad::operator=(StringBad & st)
{
	if(this==&st)
		return *this;
    delete [] str;
    len =st.len;
    st = new char[len+1];
    std::strcpy(str,st.str);
    return *
}
```

**地址运算符**













### 12.2 改进后的新string类



```c++
class String
{
private:
    char * str;
    int len;
    static int num_strings;
    static const int CINLIM = 80;
public:
    //默认构造和其他构造函数
    String(const char*s);
    String();
    String(const String &s);
    ~String();
    int length() const {return len;}
    
    //重载运算符
    String & operator=(const String&s1);
    String & operator=(const char*s1);
    char & operator[](int i);
    const char & operator[](int i) const;
    
    //友元重载运算符
    friend bool operator<(const String &s1,const String &s2);
    friend bool operator>(const String &s1,const String &s2);
    friend bool operator==(const String &s1,const String &s2);
    friend std:ostream & operator<<(std::ostream &os,const StringBad& st);
    friend std:istream & operator>>(std::istream &is,const StringBad& st);
    
    //静态成员函数
    static int HowMany();
}
```



```c++
//新的默认构造函数
String::String()
{
    len = 0;
    str = new char[1];
    str[0]='\0';
}
String::~String()
{
    delete [] str;
}
```

使用 str = new char[1];而不是 str = new char;在于析构函数的兼容。

delete[]与new[]初始化的指针和空指针都兼容



**C++11空指针**

```c++
str = nullptr;
```



#### 使用中括号来表示访问字符

```c++
//函数定义
char & String::operator[](int i)
{
    return str[i];
}

String city("happy");
city[0] = 'r';
city.operator[0] = 'r';
```

常量对象。无法使用`operator[]()`访问对象，不能确保不修改数据

```c++
const String answer("futile");
cout << answer[0];  //编译错误

//常量对象的operator[]()
const char & String::operator[](int i) const
{
    return str[i];
}
```



#### 静态成员函数

- 函数声明必须包含关键字

  ```c++
  static int HowMany() {return num_strings}
  ```

- 不能通过对象调用静态成员函数

- 若在公有部分声明，则可以使用类名和作用域解析运算符来调用

  ```c++
  int count = String::HowMany();
  ```

- **静态成员函数只能使用静态数据成员**









### 12.3 在构造函数中使用new时应注意的事项



- new和delete必须兼容，new对应于delete，new[]对应与delete[]
- **如果有多个构造函数，则必须以相同的方式使用new**
- **复制构造函数，深度复制**，不仅仅是数据的地址
- **赋值运算符，深度复制**







### 12.4 有关返回对象的说明

返回指向对象的引用；指向对象的const引用；const对象



#### 返回指向const对象的引用

函数返回传递给他的对象，通过返回引用来提高效率

```c++
const Vector & Max(const Vector &v1,const Vector &v2)
{
	...
        return v1;
    ...
        return v2;
}
```

**由于v1，v2都被声明为const引用，因此返回类型必须为const**



#### 返回指向非const对象的引用

重载赋值运算符以及重载与cout一起使用的<<运算符

```c++
String s2,s3;
s3 = s2 = s1;
```

s2.operator=()的返回值赋给s3，返回类型不是const，因为返回值可以对其进行修改



#### 返回对象

如果返回对象是被调用的局部变量，就不应该使用引用方式返回





### 12.5 使用指向对象的指针



```c++
//使用复制构造函数
String * favorite = new String(sayings[choice]);
```

使用对象saying[choice]来初始化新的string对象，使用了复制构造函数

```c++
class_name * pclass = new Class_name(value);
//使用构造函数
Class_name(Type_name);
```

```c++
//将指针初始化为指向已有的对象
String * first = &saying[0];
```



#### 定位new运算符

```c++
const int BUF = 512;
char *buffer = new char[BUF];

JustTesting *pc1,*pc2;
pc1 = new (buffer) JustTesting;
pc2 = new JustTesting("heap",20);

JustTesting *pc3,*pc4;
pc3 = new (buffer) JustTesting;

delete pc2;
delete [] buffer;
```

**使用new运算符创建512字节的内存缓冲区，使用定位new运算符在缓冲区中创建两个JustTesting对象**



程序员需要提供两个位于缓冲区的不同地址，确保两个内存单元不重叠

```c++
pc1 = new(buffer) JustTesting;
pc3 = new(buffer+sizeof(JustTesting)) JustTesting("Better",6);
```

**delete可以与常规new运算符配合使用，但不能与定位new运算符配合使用**

**delete[]buffer释放了整个内存块**，**但是没有为定位new运算符在该内存块创建的对象调用析构函数。**

**需要显式的定位new运算符创建的对象调用析构函数**

```c++
pc3->~JustTesting();
pc1->JustTesting();
delete []buffer;
```



### 12.7 队列模拟





```c++
Class Queue
{
private:
    struct Node
    {
        Item item;
        struct Node* next;
        enum{Q_SIZE=10};
        Node *front;
        Node *rear;
        int items;
        const int qsize;
	}
}
```

#### 嵌套结构和类

**类声明中声明的结构，类，或枚举被称为嵌套在类中，其作用域为整个类。**

如果为私有部分只能在类中使用。

公有部分，可以通过作用域解析运算符使用。Queue::Node



#### 成员初始化列表

**qsize为常量，可以对其进行初始化**，但是不能给它赋值

```c++
Queue::Queue(int qs):qsize(qs),front(nullptr),rear(nullptr),items(0)
{
}
```

- 对于**const类成员**，必须使用初始化列表。
- 对于**声明为引用的类成员**，必须使用初始化列表。
- 仅适用于构造函数

```c++
class Agent
{
	private:
		String & belong;
}
Agent::Agent(String & a):belong(a)
{
}
```



#### 类内初始化

```c++
class Classy
{
    int mem1 = 10;
	const int mem2= 20;
}
```

```c++
Classy::Classy(int n):mem1(n)
{
}
//mem1=n,mem2=20
```







### 12.10 编程练习

![image-20220313164617871](https://s2.loli.net/2022/05/06/sZgWurLbJaKeYp9.png)

```c++
//a.
String operator+(const String& s1,const String& s2)
{
    String str;
    delete []str.s;
    str.s = new char[s1.length+s2.length+1];
    strcpy(s,s1);
    strcat(s,s2);
    return str;
}

//b.
void String::Stringlow()
{
    while(*s!='\0')
    {
        if(*s >= 'A' && *s <= 'Z')
        {
            *s += 'a'-'A';
            *s++;
        }
    }
}
//d.
int String::has(char ch)
{
    int count=0;
    do{
      if(*s==ch)
      {
          count++;
      }
    }while(*s!='\0');
    return count;
}
```



















## 第十三章 类继承











### 13.1 一个简单的基类



```c++
class TableTennisPlayer
{
    private:
    
    public:
    	TableTenniPlayer(const string & fn="none",const string & ln = "none", bool ht = false);
};
```

```c++
//公有派生
class RatedPlayer : public TableTennisPlayer
{
	private:
    public:
    	RatedPlayer(unsigned int r=0; const string & fn="none",const string & ln = "none", bool ht = false);
    	RatedPlayer(unsigned int r,const TableTennisPlayer & tp);
}
```

公有派生，基类的公有成员将成为派生类的公有成员；基类的私有也将成为其派生类的一部分

- 派生类对象存储基类的数据成员
- 派生类对象可以使用基类的方法







#### 访问权限

派生类不能直接访问基类的私有成员。

派生类构造函数必须使用基类构造函数。

```c++
RatedPlayer::RatedPlayer(unsigned int r; const string & fn,const string & ln , bool ht ):TabelTennisPlayer(fn,ln,ht)
{
    rating = r;
}
```

将参数作为实参传给TableTennisPlayer构造函数，创建一个嵌套对象

```c++
RatedPlayer::RatedPlayer(unsigned int r; const string & fn,const string & ln , bool ht )//： TableTennisPlayer()
{
    rating = r;
}
```

如果不调用基类构造函数，程序将使用默认的基类构造函数

```c++
RatedPlayer::RatedPlayer(unsigned int r,const TableTennisPlayer & tp):TableTennisPlayer(tp)
{
    rating = r;
}
```

将调用基类的拷贝构造函数

ATT：**创建派生类对象，首先调用基类构造函数，然后再调用派生类构造函数**。

**可以使用初始化列表使用基类构造函数，否则将使用默认的基类构造函数。**









#### 派生类与基类

派生类可以使用基类的方法

- 基类指针可以在不进行显示转化的情况下指向派生类对象。基类引用也可以。

```c++
RatedPlayer rplayer1;
TableTennisPlayer & rt = rplayer;
TableTennisPlayer * pt = rplayer;
```

基类指针和引用只能使用基类方法，不能使用派生类方法

- 不可以将基类对象和地址赋给派生类引用和指针

- **可以将基类对象初始化为派生类对象**

  ```c++
  RatedPlayer olaf1;
  TableTennisPlayer olf2(olaf1);
  //存在隐式拷贝构造函数
  TableTennisPlayer (const TableTennisPlayer&);
  ```

- 可以将派生类对象赋给基类对象

  ```c++
  RatedPlayer olaf1;
  TableTennisPlayer olf2;
  olaf2=olaf1;
  //使用隐式赋值运算符
  ```











### 13.3 多态公有继承



希望同一个方法在派生类和基类中的行为是不同的，此为多态

```c++
class Brass
{
private:
public:
    Brass();
    virtual void Withdraw(double amt);
    double balance() const;
    virtual void VieAcct() const;
    virtula ~Brass();
}

class BrassPlus:public Brass
{
private:
public:
    BrassPlus();
    virtual void Withdraw(double amt);
    virtual void VieAcct() const;
}
```

- 如果方法是通过引用或指针调用。

**没有使用关键字virtual，程序将根据引用类型或指针类型方法；**

**使用了virtual，程序将根据引用或指针指向的对象类型来选择方法**；

```c++
//使用了关键字virtual
Brass dom;
BrassPlus dot;
Brass & b1 = dom;
Brass & b2 = dot;
b1.VieAcct();	//use Brass::VieAcct()
b2.VieAcct();	//use BrassPlus::VieAcct()
```

- 基类声明了虚析构函数，为了确保释放派生类对象时，按正确的顺序调用析构函数

派生类不能直接访问基类的私有数据，必须通过基类的公有方法访问

```c++
void BrassPlus::VieAcct() const
{
	Brass::VieAcct();
    ...
}
```

派生类方法调用基类方法显示基类数据成员，使用作用域解析运算符。



- 使用一个数组来保存Brass和BrassPlus对象

可以创建指向Brass的指针数组。

```c++
Brass *p_clients[5];
p_clients[1] = new Brass();
p_clients[2] = new BrassPlus();
```

**如果析构函数不是虚的，则将只调用对应于指针类型的析构函数**，对于此程序来说只有Brass的析构函数被调用。因此虚析构函数，可以确保正确的析构函数序列被调用。





### 13.4 静态联编和动态联编

将源代码中的函数调用解释为执行特定的函数代码被称为函数名联编

**静态联编，在编译过程中进行联编**

**动态联编，编译器必须生成能够在程序运行时选择正确的虚方法的代码**



**编译器对非虚方法使用静态联编**。由于静态联编的效率更高，因此被设置为C++的默认选择

使用**虚函数**需要在内存和执行速度方面有一定成本：

- 每个对象都将增大，增大量为存储地址的空间
- 对于每个类，**编译器都创建一个虚函数地址表**
- 对于每个函数调用，都需要执行一项额外的操作，即到表中查找地址



#### 虚函数的注意事项

- 在基类方法的声明中使用关键字virtual可使该方法在基类以及所有的派生类(包括从派生类派生出来的类)中是虚的。

- **如果使用指向对象的引用或指针来调用虚方法,程序将使用为对象类型定义的方法,而不使用为引用或指针类型定义的方法。**这称为动态联编或晚期联编。这种行为非常重要,因为这样基类指针或引用可以指向派生类对象。

- 如果定义的类将被用作基类,则应将那些要在派生类中重新定义的类方法声明为虚的。

- **构造函数不能是虚的**

- **析构函数应当是虚的**

- **友元不能是虚函数**，因为友元不是类成员，只有成员才能使虚函数

- **如果派生类没有重新定义函数，将使用该函数的基类版本**

- 重新定义将隐藏方法

  ```c++
  Base:
  	virtual void showperks(int a) const;
  Derived:
  	virtual void showperks() const;
  
  Derived trump;
  trump.showperks();	//valid
  trump.showperks(5)	//invalid
  ```

  **重新定义继承的方法并不是重载，而是隐藏同名的基类方法**

  **如果重新定义继承的方法，应确保与原来的原型完全相同。**

  但如果返回的类型是基类引用或指针，则可以修改指向派生类的引用和指针。此特性称为**返回类型协变**
  
  ```c++
  Base:
  	virtual Base& showperks(int a) const;
  Derived:
  	virtual Derived& showperks(int a) const;
  ```

  如果基类声明被重载了，则应在派生类中重新定义所有的基类版本
  
  ```c++
  Base:
  	virtual void showperks() const;
  	virtual void showperks(int a) const;
  	virtual void showperks(double a) const;
  Derived:
  	virtual void showperks() const;
  	virtual void showperks(int a) const;
  	virtual void showperks(double a) const;
  ```
  
  如果只重新定义一个版本，则其他两个版本将被隐藏

















### 13.5 访问控制：protected

关键字protected与private相似，在类外只能用公有类成员函数来访问protected部分中的类成员。**区别在于派生类成员可以直接访问基类的保护成员，但不能访问基类的私有成员。**



一般来说，对类数据成员采用私有访问控制，不要使用保护访问控制。

对于成员函数来说，保护访问控制很有用，能让派生类访问公众不能使用的内部函数













### 13.6 抽象基类



抽象基类(abstract base class,A)

以椭圆和圆为例，从椭圆和圆中抽象出他们的共性，将特性放到ABC中。然后从ABC中派生出Ellipse类和Circle类。

```c++
class BaseEllipse
{
private:
	double x;
	double y;
public:
    BaseEllipse(double x0=0,double y0=0):x(x0),y(y0){}
    virtual ~BaseEllipse(){}
    void Move(int nx,ny){x=nx,y=ny;}
    virtual double Area() const =0
}
```

C++使用纯虚函数提供未实现的函数。**纯虚函数声明的结尾处=0；**

当类声明中包含纯虚函数时，则不能创建该类的对象，包含纯虚函数的类只能用作基类。

```c++
//声明为虚的
void Move(int nx,ny)=0;
//将使基类成为抽象的，仍可以在实现文件中提供方法的定义
void BaseEllipse::Move(int nx,ny){x= nx;y=ny;}
```

从BaseEllipse类中派生出Ellips类和Circle类。因此可以使用BaseEllipse指针数组同时管理Ellips类和Circle类。













### 13.7 继承和动态内存分配



#### 基类使用动态内存，派生类不使用new

```c++
class baseDMA
{
private:
    char * label;
	int rating;    
public:
    baseDMA();
    virtual ~baseDMA();
    baseDMA& operator=(const baseDMA & rs);
}
```

从baseDMA派生出lackDMA类，而后者不使用new，不需要为lackDMA类定义显示析构函数，复制构造函数和赋值运算符。

**派生类的默认复制构造函数将使用基类的复制构造函数来复制基类对象的label成员。**





#### 基类使用动态内存，派生类也使用new

必须为派生类定义显示析构函数、复制构造函数和赋值运算符

```c++
class hasDMA:public baseDMA
{
private:
    char *style;
public:
}
```

hasDMA析构函数必须释放style管理内存

```c++
baseDMA::~baseDMA()
{
}

hasDMA::~hasDMA()
{
}
```

复制构造函数

```c++
hasDMA::hasDMA(const hasDMA & hs):baseDMA(hs)
{
    stryle =new char(strlen(hs.style)+1);
    std::strcpy(style,hs.style);
}
```

显式赋值运算符

```c++
hasDMA & hasDMA::operator=(const hasDMA & hs)
{
	...;
    baseDMA::operator=(hs);
    ... 
}
```

通过使用作用域解析运算符显式地调用基类的赋值运算符





#### 使用动态内存分配和友元的继承示例

```c++
class baseDMA
{
public:
	friend std::ostream & operator<<(ostream & os,const baseDMA& rs);
}
```

```c++
friend std::ostream & operator<<(ostream & os,const baseDMA& rs)
{
}

friend std::ostream & operator<<(ostream & os,const lackDMA& ls)
{
    os << (const baseDMA &)ls;
    ...
}

friend std::ostream & operator<<(ostream & os,const lackDMA& hs)
{
    os << (const baseDMA &)hs;
    ...
}
```











### 13.8 类设计回顾



#### 编译器生成的成员函数

##### 1.默认构造函数

如果定义了某种构造函数，编译器将不会定义默认沟站函数。

##### 2.复制构造函数

使用new初始化的成员指针需要执行深复制

##### 3.赋值运算符





#### 其他的类办法

##### 转换

```
class star
{
public:
	explicit Star(const char*);
}

north = "abc";			//not allowed
north = star("abc");	//allowed
```

##### 按值传递和传递引用



##### 返回对象和返回引用



##### 使用const

```c++
//确保不修改参数
Star::Star(const char *s);
//const确保方法不修改调用它的对象
void Star::show() const{}	//const表示const Star*this
//返回的对象也是const
const Stock & Stock::topval(const Stoc&s)const{}
```















## 第十四章 C++中的代码重用



has-a关系可以用包含、组合或层次化。零一种方法是使用私有或保护继承（多重继承）。



### 14.1 包含对象成员的类

valarray类支持数组元素相加，以及求数组中最大和最小的值。

```c++
valarray<int> q_values;
valarray<double> weights;
```



#### C++和约束

C++包含让程序员能够限制程序结构的特性--使用explicit防止单参数构造函数的隐式转换，使用const限制方法修改数据

```c++
class Student
{
private:
    string name;
    valarray<int> scores;
public:
    explicit Student(const std::string & s):name(s),scores(){}
    explicit Student(int n):name("Nully"),scores(n){}
    friend istream& getline(istream& is,Student& stu);
}
```



#### 初始化顺序

当初始化列表包含多个项目时，这些项目被初始化的顺序为他们被声明的顺序，而不是在初始化列表中的顺序。



```c++
istream & getline(istream & is,Student & stu)
{
	getline(is,stu);
    return is;
}
```











### 14.2 私有继承

使用私有继承，基类的公有成员和保护成员都将成为派生类的私有成员，基类方法将不会成为派生类对象公有接口的一部分，但可以在派生类的成员函数中使用他们。

```c++
class Student:private string,private valarray<double>
{
private:
    typedef std::valarray<double>ArrayDb;
public:
    Student():std::string("Null"),ArrayDb(){}
    Student(const char *str,const double *pd,int n)
        :std::string(str),ArrayDb(pd,n){}
    double Average() const;
    const string & Name() const;
}
```

使用多个基类继承的被称为多重继承。

- 包含版本提供两个被显式命名的对象成员，而私有继承提供两个无名称的子对象成员。

- 成员列表初始化使用的是std::string(str),而不是name(str)

##### 访问基类方法

```c++
double Student::Average() const
{
	if(ArrayDb::size()>0)
        return ArrayDb::sum()/ArrayDb::size();
    else
        return 0;
}
```

##### 访问基类对象

Student类的代码如何访问内部的string对象。

使用强制类型转换。通过强制类型转换将student对象转换为string对象

```c++
const string & Student::Name() const
{
	return (const string&) *this;
}
```

##### 访问基类的友元函数

通过显式转换为基类调用正确的函数,显式将Student转化为string,进而调用基类的友元。

```c++
ostream & operator<<(ostream & os,const Student & stu)
{
	os<<(const string&)stu;
}
```

引用stu不会自动转换为string引用。在私有继承中，在不进行显式类型转换的情况下，不能将指向派生类的引用或指针赋给基类指针或引用。

```c++
istream & getline(istream & is,Student & stu)
{
	getline(is,(string &)stu);
    return is;
}
```















### 14.3 多重继承



继承关系必须使用关键字public来限定每一个基类。因为除了特别指出，编译器都将认为是私有派生。

```
class SingingWaiter :public Waiter,Singer
{};
```





waiter和singer公有继承于worker

因此SingingWaiter将包含两个worker组件。

```c++
SingingWaiter ed;
Worker * pw =&ed;//ambiguous
```

这种赋值通常把基类指针设置为派生对象中基类对象的地址。但ed中有两个worker对象，有两个地址可以供选择，应使用类型转换来指定对象

```c++
Worker * pw1=(Waiter*) &ed;
Worker * pw1=(Singer*) &ed;
```





#### 虚基类

虚基类是的从多个类（他们的基类相同）派生出的对象只继承一个基类对象。

在类声明中使用关键字virtual，可以使worker被用作Singer和Waiter的虚基类(次序无关)

```c++
class Singer:virtual public Worker{};
class Waiter:public virtual Worker{};
class SingingWaiter:public singer,public Waiter{}
//singerWaiter只包含一个worker子对象
```

- 对于非虚基类，唯一可以出现在初始化列表的构造函数时即时基类构造函数。

```
class A{};
class B: public A{};
class C: public B{};
```

C的构造函数只调用B的构造函数，B的构造函数只调用A的构造函数。

- 对于虚基类来说，自动传递将不起作用

```c++
SingingWaiter(const Worker &wk,int p=0,int v=Singer::other):Waiter(wk,p),Singer(wk,v){}
//C++基类是虚的，禁止信息从中间类传递给基类。
//在上述情况下，编译器将使用worker的默认构造函数
```

```c++
SingingWaiter(const Worker &wk,int p=0,int v=Singer::other):Worker(wk),Waiter(wk,p),Singer(wk,v){}
//显示调用构造函数worker(const Worker&)
```

上述做法对用虚基类是合法的，但是对于非虚基类是非法的。



#### 多重继承，使用父类哪个方法

若singingWaiter没有重新定义show()

```c++
SingingWaiter happy;
happy.show();//ambiguous
//不知道使用waiter还是singer的show()
```

可以使用作用域解析符来澄清编程者的意图：

```c++
SingingWaiter happy;
happy.Singer::show();
```



#### 小结

- 如果一个类从两个不同的类继承两个同名的成员，则需要使用类限定符来区分
- 当派生类使用关键字virtual来指示派生，基类就是虚基类
- 从虚基类的一个或多个实例派生而来的类只继承一个基类对象
  有间接虚基类的派生类包含直接调用间接基类构造函数的构造函数













### 14.4 类模板

```c++
template <class Type>
//关键字template告诉编译器，要定义一个模板。
```

```c++
template <class Type>
class Stack
{
private:
    enum {SIZE=10};
    int stacksize;
    Type *items;
    int top;
pubilc:
    explicit Stack(int ss=SIZE);
    Stack(const Stack& st);
    ~Stack(){delete [] items;}
    bool isempty();
    bool isfull();
    bool push(const Type & item);
    bool pop(Type & item);
    Stack & operator=(const Stack &st);
}

template<class Type>
stack<Type>::stack(int ss=SIZE):stacksize(ss),top(0)
{
    items = new Type[stacksize];  
}    

template<class Type>
stack<Type>::Stack(const Stack& st)
{
    stacksize=st.stacksize;
    top=st.top;
    items=new Type[stacksize];
    for(int i=0;i<stacksize;i++)
    {
        items[i]=st.items[i];
    }
}

template<class Type>
bool Stack<Type>::isempty()
{
    return  top==0;
}

template<class Type>
bool Stack<Type>::isfull()
{
    return top==MAX;
}

template<class Type>
bool Stack<Type>::push(const Type & item)
{
    if(top!=MAX)
    {
        items[top++]=item;
        return true;
    }else
    {
        return fasle;
    }   
}

template<class Type>
bool Stack<Type>::pop(Type & item)
{
    if(top>0)
    {
        item=items[--top];
        return true;
    }else
    {
        return fasle;
    }   
}

template<class Type>
Stack<Type>& Stack<Type>::operator=(const Stack<Type>&st)
{
    if(this==&st)
    {
        return this*
    }else
    {
        delete []items;
        stacksize=st.stacksize;
    	top=st.top;
    	items=new Type[stacksize];
    	for(int i=0;i<top;i++)
    	{
        	items[i]=st.items[i];
    	}
        return *this
    }
}
```



使用模板类，必须请求实例化

```c++
Stack<int> kernels;
Stack<string> colonels;
```

Stack类假设可以将一个项目赋给另一个项目，这种假设对于基本类型、结构和类是成立的



```c++
//函数声明
Stack& Stack::operator=(const Stack&st);
//函数定义
template<class Type>
Stack<Type>& Stack<type>::operator=(const Stack<Type>&st)
{}
```

将赋值运算函数的返回类型声明为stack引用，实际为stack<Type>的缩写。可以在模板声明或模板函数定义内使用stack，但在类外，即指定返回类型或使用作用域解析运算符时，必须使用完整的stack<Type>。





#### 数组模板示例

```c++
template<class T,int n>
class ArrayTP
{
private:
    T ar[n];
public:
    ArrayTP(){};
    explicit ArrayTP(const T&v);
    virtual T & operator[](int i);
    virtual T operator[](int i)const;
}
```

这种参数称为**表达式参数**。

指定数组大小的数组模板。一种方法是使用**动态数组和构造函数参数**来设定。

另一种方法是使用**表达式参数**来提供常规数组大小。

构造函数更通用，数组大小作为类成员存储在定义中，可以将一种尺寸的数组赋给另一个尺寸的数组。







#### 模板多功能性

##### 递归使用模板

```c++
ArrayTP<ArrayTP<int,5>,10> towdee;
twodee[i][j];
```

##### 使用多个类型参数

pair模板

```c++
Pair<string,int>ratings[4];
int joints=sizeof(ratings)/sizeof(Pair<string,int>);
```

##### 默认类型参数模板

```c++
template <class T1,class T2=int> 
class Topo{};
Topo<double,double>m1;
Topo<double>m2
```









#### 模板的具体化

模板可以有隐式实例化、显式实例化和显式具体化

***隐式实例化\***：使用模板之前，编译器不生成模板的声明和定义示例，后面有程序用了，编译器才会根据模板生成一个实例函数，
***显式实例化\***：是无论是否有程序用，编译器都会生成一个实例函数
***显示具体化\***：因为对于某些特殊类型，可能不适合模板实现，需要重新定义实现，此时就是使用显示具体化的场景



##### 隐式实例化

即声明一个或多个对象，指出所需的类型

```c++
ArrayTP<int,100> stuff;
```

编译器在需要对象之前，不会生成类的隐式实例化：

```c++
ArrayTP<double,30>*pt;//只是生成指针，不需要对象
pt = new ArrayTP<double,30>;//现在需要一个对象
```



##### 显式实例化

使用关键字template指出所需类型来声明类，编译器将生成类声明的显示实例化

声明必须位于模板所在的名称空间中

```c++
template class ArrayTP<string,100>;
```



##### 显式具体化

需要在为特殊类型实例化时，对模板进行修改，使其行为不同。

具体化模板

```c++
template<>class ClassName<specialized-type-name>{};
template<>class SortedArray<const char*>{};
```



##### 部分具体化

```c++
//通用模板
template<class T1,class T2> 
    class Pair{};
//部分具体化,T2具体化为int
template<class T1> 
    class Pair<T1,int> {};
//显式具体化
template<> 
	class Pair<int,int>{};
```

```c++
Pair<double,double>pl; //通用模板
Pair<double,int>p2; //部分具体化,T2具体化为int
Pair<int,int>p3;//显式具体化
```

也可以通过为指针提供特殊版本来部分具体化

```c++
template<class T> 
class Feeb{}
template<class T*> 
class Feeb{}
```

```
Feeb<char> fb1;
Feeb<char*> fb2;
```







#### 成员模板

模板类可以将另一个模板类和模板函数作为其成员

```c++
template <typename T>
class beta
{
private:
    template<typename V>
    class hold
    {
    };
    
    hold<T> q;
    hold<int> n;
public:
    beta(T t,int i):q(t),n(i){}
    template<typename U>
    U blab(U u,T t){return ..};
}


int main()
{
    beta<double> guy(3.5,3);//T set double
    cout << guy.blab(10,2.3);//U set int
    cout << guy.blab(10.0,2.3);// U set double
}
```





#### 将模板用作参数

```c++
template<template <typename T> class Thing>
class Crab
{
private:
    Thing<int> s1;
    Thing<double> s2;
};
```

其中template <typename T> class是类型，Thing是参数

```c++
//实例化
Crab<King> legs;
//kings 是一个模板类 template<typename T> class King{};
```

```c++
Crab<Stack> nebula;
//Stack<int>s1;
//Stack<double>s2;
```

混合使用模板参数和常规参数

```c++
template<template <typename T> class Thing,typename U,typename V>
class Crab
{
private:
    Thing<U> s1;
    Thing<V> s2;    
}

Crab<Stack,int,double>nebula;
```





#### 模板类和友元

模板类声明也可以有友元。模板的友元分3类:

- 非模板友元:
- 约束(bound)模板友元,即友元的类型取决于类被实例化时的类型;
- 非约束(unbound)模板友元,即友元的所有具体化都是类的每一个具体化的友元。



##### 模板类的非模板友元函数

```c++
template<class T>
class HasFriend
{
private:
    static int ct;
public:
	friend void counts();
    friend void report(HasFriend<T> &);
}

template<class T>
int HasFriend<T>::ct=0;
void counts(){
    cout << HasFriend<int>::ct;
    cout << HasFriend<double>::ct;
}
friend void report(HasFriend<int> &);
friend void report(HasFriend<double> &);
```

couts()函数成为所有模板实例化的友元



要提供模板类参数必须指明具体化

```c++
tamplate<class T>
//声明
friend void report(HasFriend<T> &);
//显式具体化定义
friend void report(HasFriend<int> &);
friend void report(HasFriend<double> &);
```

report()本身并不是模板函数，而只是使用一个模板作为参数，这意味着必须使用显式具体化

HasFriend模板的静态成员ct，每个类的特定具体化都将有自己的静态成员

```c++
int main()
{
    HasFriend<int> hfi1(10);
    HasFriend<int> hfi2(20);
    HasFriend<double> hfdb(10.5);
    counts();
    reports(hfi1);
    reports(hfi2);
    reports(hfdb);
}
```





##### 模板类的约束模板友元函数

在类定义前面声明每个模板函数

```c++
template <typename T> void counts();
template <typename T> void report(T &);
```

在函数中再次将模板声明为友元，根据模板参数声明具体化

```c++
template <typename TT>
class HasFriendT
{
    
	friend void counts<TT>();
    friend void report<>(HasFriend<TT>&);
}
```

```c++
int main()
{
	counts<int>();
    HasFriend<int> hfi1(10);
    HasFriend<int> hfi2(20);
    HasFriend<double> hfdb(10.5);
    reports(hfi1);
    reports(hfi2);
    reports(hfdb);
    counts<double>();
}
```

count<double>和count<int>报告的模板大小不同。每种T类型都有自己的友元函数count()





##### 模板类的非约束模板友元函数

通过在类内部声明模板，可以创建非约束友元函数，即每个函数具体化都是每个类具体化的友元

```c++
template <typename T>
class ManyFriend
{
	template<typname C,typename D> friend void show2(C&,D&);
}
```

```c++
int main()
{
    ManyFriend<int> hfi1(10);
    ManyFriend<int> hfi2(20);
    ManyFriend<double> hfdb(10.5);
    show2(hfi1,hfi2);//void show2<ManyFriend<int>,ManyFriend<int>>(ManyFriend<int>,ManyFriend<int>);
    show2(hfi1,hfdb);//void show2<ManyFriend<int>,ManyFriend<double>>(ManyFriend<int>,ManyFriend<double>);
}
```





#### 模板别名

使用typedef为模板具体化

```c++
typedef std::array<double,12> arrd;
typedef std::array<int,12> arrd;
typedef std::array<std::string,12> arrd;
```

```c++
template<typename T>
	using arrtype = std::array<T,12>;

arrtype<double> gallons;
arrtype<int> days;
```

C++11允许将using=用于非模板，等价于typedef

















## 第十五章 友元、异常和其他





### 15.1 友元

可以将类作为友元。友元类的所有方法可以访问原始类的私有成员和保护成员

也可以将特定的成员函数指定为另一个类的友元。



#### 友元类

遥控器可以控制电视机的状态，应将Remote类作为Tv类的一个友元

```c++
friend class Remote;
```

友元声明可以位于公有、私有或保护部分，其位置无关紧要。

```c++
class Tv
{
public:
    friend class Remote;
    enum{TV,DVD};
    enum{Off,On};
    
    Tv(int s=Off,int mc=125);
    void onoff(){state = (state==On)?Off:on;}
    bool volup();
    bool voldown();
    ...
}

class Remote
{
public:
    Remote(int m= Tv::TV):mode(m){};
    void onoff(Tv &t){t.onoff();}
    bool volup(Tv &t){return t.volup()};
    bool voldown(Tv &t){return t.voldown()};
    void setchan(Tv &t,int c){t.channel=c;}
}
```

```c++
//使用异或运算符来简化两个状态的转换
void onoff(){state = (state==On)?Off:on;}
void onoff(){state^=1;}
```

```c++
int main()
{
	Tv s42;
    s42.volup();
    s42.voldown();
    
    Remote grey;
    grey.volup(s42);
    grey.setchan(s42,10);
    
    Tv s43;
    s43.volup();
    s43.voldown();
    grey.setchan(s43,10);
    
}
```





#### 友元成员函数

唯一直接访问Tv成员的Remote方法是Remote::setchan(),所以唯一需要的是这个成员函数

1. 让Remote::setchan(),成为Tv类的友元，需在Tv类声明中将其声明为友元

   ```c++
   class Tv
   {
       friend void Remote::setChan(Tv & t,int c);
   }
   ```

2. Tv类处理友元语句必须知道Remote的定义，Remote定义需要放在Tv前

3. Remote的方法提到了Tv对象，需要Tv的定义在Remote之前

   ```c++
   class Tv;
   class Remote{...};
   class Tv{...};
   
   inline void Remote::volup(Tv &t){return t.volup();}
   
   ```
   

Remote中使用到的Tv类对象需要在最后内联定义。

让整个Remote类成为友元并不需要前向声明，因为友元语句本身已经指出了Remote是一个类





#### 共同友元

函数需要访问两个类的私有数据。

- 一个类的成员，另一个类的友元
- 两个类的友元

```c++
class Analyzer;
class Probe
{
    friend void sync(Analyzer & a,const Probe &p);
    friend void sync(Probe&p,const Analyzer & a);
}

class Analyzer
{
    friend void sync(Analyzer & a,const Probe &p);
    friend void sync(Probe&p,const Analyzer & a);
}

inline void sync(Analyzer & a,const Probe &p)
{
    
}

inline void void sync(Probe&p,const Analyzer & a)
{
    
}
```









### 15.2 嵌套类

在另一个类中声明的类成为嵌套类。

仅当声明位于公有部分时，才能在包含类的外面使用嵌套类，而且必须使用作用域解析运算符

包含意味着将类对象作为另一个类的成员，而对类进行嵌套不创建类成员，而是定义了一种类型，该类型在包含嵌套类的声明中有效

```c++
class Queue
{
	class Node
    {
     public:
        Item item;
        Node *next;
        Node(const Item& i):item(i),next(0){}
    };
}

bool Queue:enqueue(const Item&item)
{
    if(isfull())
        return false;
    Node *add = new Node(item);
}
```

要想在方法文件中定义构造函数，定义需要指出Node类是在Queue类中定义的

```c++
Queue::Node::Node(const Item&i):item(i),next(0){}
```





#### 嵌套类和访问权限

嵌套类的作用域私有，保护，公有声明，与普通成员一样。

```c++
class Team
{
public:
	class Coach{};
}
```

要在Team类外创建Coach对象

```c++
Team::Coach forhire;
```

嵌套结构与枚举的作用域与此相同。因此许多程序员使用公有枚举来提供客户程序员使用的类常数。







### 15.5 类型转换运算符

- dynamic_cast

- const_cast

- static_cast

- reinterpret_cast

  

dynamic_cast能够在类层次结构中进行向上转换

```
dynamic_cast<type-name>(expression);
```

```c++
High* ph;
Low* pl;
pl=dynamic_cast<Low*>ph;//仅当Low是High可访问的基类，才能赋值，否则将空指针付给pl
```



const_cast运算符用于执行const或volatile转换,也就是将const改为非const

```c++
const_cast<type-name>(expression);
```

type-name和expression的类型相同

```c++
High bar;
cosnt High *pbar=&bar;
High *pb=const_cast<High*>(pbar);//valid
const Low*pl=const_cast<const Low*>(pbar);//invalid;
```

第一个类型转换使得*pb成为一个可用于修改bar对象值的指针，删除了const标签



static_cast可以进行向上转换或者向下转换

```c++
High bar;
Low blow;
High *pb=static_cast<High*>(&blow);
Low *pl=static_cast<Low*>(&bar);
```

从派生类到基类是可以正常进行。从基类到派生类，在不进行显示类型转换的情况下，无法进行。













## 第十六章 string类和标准模板库



### 16.1 string 类

string有7个构造函数

string::npos定义为字符串的最大长度，通常为unsigned int的最大值

```c++
string one("Lotter Winner");
string two(20,'$');
stirng three(one);
string four;
char alls[]="All's well that ends well";
string five(alls,20);
string six(alls+6,alls+10);
string seven(four,7,16);

one+="Oops";			//+=
two="Sorry!";			//=
cout<<four<<endl;		//<<
cout<<five[4];			//[]
```

```
char alls[]="All's well that ends well";
string five(alls,20);
```

只使用前20个字符来初始化five对象。如果用40代替20，将导致15个无用字符复制到five的结尾处，即内存中后面的内容作为字符。

```c++
template<class Iter> string(Iter begin,Iter end);//[begin,end)
```



```c++
string seven(four,7,16);
```

four的第八个字符开始，将16个字符复制到seven中



#### C++11新增的构造函数

string(string && str) noexcept 这是C++11新增的,它将一个string对象初始化为string对象str,并可能修改str(移动构造函数)

string<initializer_list<char> il>这是C++11新增的,它将一个string对象初始化为初始化列表il中的字符

```c++
string piano_man={'L','i','s','z','t'};
```



#### string类输入

char输入

```c++
char info[100];
cin>>info;
cin.getline(info,100);//discard \n
cin.get(info,100);//leave \n
```

string输入

```c++
string stuff;
cin>>stuff;			//read a word
getline(cin,stuff);	//read a line,discard\n
```

```c++
cin,getline(info,100,':');	//read up to :,discard :
getline(stuff,':');			//read up to :,discard :
```

指定分界字符后，换行符就被视为常规字符





#### 使用字符串

length()和size()都返回字符串中的字符数

find()有个四个重载版本

```c++
string str("happy");
string str1("ap");
char s[]="ap";
char ch='h'
int pos = str.find(str1,0);	//位置0开始搜索str1
int pos = str.find(s,1);	//位置1开始搜索s
int pos = str.find(s,1,1);	//位置1开始搜索s的前1个字符组成的字符串
int pos = str.find(ch,0);	//位置0开始搜索ch
```

```c++
rfind();//右侧开始搜索
find_first_of();//查找参数中任何一个字符首次出现的位置
find_last_of();//查找参数中任何一个字符最后一次出现的位置
find_first_not_of();//在字符串中查找第一个不包含在参数中的字符
find_last_not_of();//在字符串中查找最后一个不包含在参数中的字符
int where = snake1.find_first_of("hark");
```

```c++
if(badchars.find(letter)!=string::npos||attempt.find(letter)!=string::npos)
```

npos是string类的静态变量，它的值是string对象能存储的最大字符数。从而表示没有查找到字符或字符串







### 16.2 智能指针模板

```c++
std::string* ps=new std::string(str);
```

该语句分配堆中的内存，需要使用delete来收回，若不收回则会导致内存泄漏

```c++
std::string* ps=new std::string(str);
...;
if(weird_thing())
    throw excetion();
delete ps;
```

当出现异常时，delete将不被执行，因此将导致内存泄漏



#### 智能指针

auto_ptr,unique_ptr,shared_ptr

智能指针对象必须要包含头文件memory

智能指针过期时，其析构函数将使用delete来释放内存

```c++
template<class X> 
class auto_ptr
{
public:
    explicit auto_ptr(X* p=0) throw();
};
```

throw()意味着构造函数不会引发异常。

```c++
auto_ptr<double> pd(new double);
auto_ptr<string> ps(new string);
```

new double是new 返回的指针，指向新分配的内存块。

```c++
unique_ptr<double> pdu(new double);
shared_ptr<string> pss(new string);
```





所有智能指针类都有一个explicit构造函数，该构造函数将指针作为参数。因此不能将指针自动转换为智能指针对象

```c++
shared_ptr<double> pd;
double *p_reg=new double;
pd = p_reg;//not allowed(implicit conversion);
pd = shared_ptr<double>(p_reg);
shared_ptr<double>pshared = p_reg;//not allowed;
shared_ptr<double>pshared(p_reg);
```

智能指针对象很多方面类似于常规指针。*ps接触引用操作，将其赋给相同类型的常规指针，赋给同一类型的智能指针对象。

```c++
string vaction("I wanted!");
shared_ptr<string> pvac(&vacation);//no
```

delete运算符用于非堆内存这是错误的



```c++
auto_ptr<string> ps(new string("i wanted"));
auto_ptr<string> vocation;
vocation=ps;
```

auto_ptr和unique_ptr在出现赋值语句时，会转让所有权

赋值操作转让所有权的unique_ptr指针

shared_ptr跟踪引用特定对象的智能指针数，引用计数。赋值时计数加一，指针过期时，计数减一。仅当最后一个指针过期时调用delete



```c++
auto_ptr<string>films[5]= 
{	
    auto_ptr<string>(new string("Powl Barls")),
 	auto_ptr<string>(new string("Duck Warks")), 
    auto ptr<string>(new string("Chicken Runs")), 
    auto_ptr<string>(new string("Turkey Errors")),
    auto_ptr<string>(new string("Goose Eggs"))
};
auto_ptr<string> pwin;
pwin=films[2];	//films[2] loses ownership;
```

films[2]不再引用该字符串。程序会在运行时报错。

若使用shared_ptr代替auto_ptr则程序正常运行。

```c++
shared_ptr<string> pwin;
pwin=films[2];
```

若使用unique_ptr则会在编译代码是报错。



#### unique_ptr与auto_ptr

unique_ptr比auto_ptr更安全，编译阶段就会报错

对于一个函数返回一个临时的unique_ptr，然后赋给一个新的unique_ptr，则返回的unique_ptr会被销毁。

试图将一个unique_ptr赋给另一个时，如果源unique_ptr是个临时右值，则编译器允许这样做。如果源unique_ptr将存在一段时间，编译器禁止这样做。

```c++
unique_ptr<string> pu1(new string "Hi bo!");
unique_ptr<string> pu2;
pu2 = pu1;	//not allowed;
unique_ptr<string> pu3;
pu3 = unique_ptr<string>(new string"YO!");//allowed
```

C++有一个标准库函数std::move()，可以将unique_ptr赋给另一个。

```c++
unique_ptr<string> pu1(new string "Hi bo!");
unique_ptr<string> pu2;
pu2 = move(pu1);	//allowed;
```

相比auto_ptr，unique_ptr可用于数组的变体

auto_ptr使用delete而不是delete[]，只能与new一起使用。而unique_ptr有使用new[]和delete[]版本

```c++
unique_ptr<double[]> pda(new double(5));
```





选择智能指针

如果程序要使用多个指向同一对象的指针，应选择shared_ptr;

如果不需要多个指向同一对象的指针，则可以使用unique_ptr;

shared_ptr包含一个显式构造函数，可用于将右值unique_ptr转换为shared_ptr;







### 16.3 标准模板库



#### 模板类vector

```c++
vector<int> ratings(5);
```

- size()返回元素数目
- swap()交换两个容器内容
- begin()返回容器的第一个元素的迭代器，end()返回一个超过容器尾部的迭代器
- iterator是一个广义指针，每个模板都定义了迭代器，一个名为iterator的typedef

```c++
vector<double>::iterator pd = scores.begin();
auto pd = scores.begin();
```

- erase()删除给定区间的元素

  ```c++
  scores.erase(scores.begin(),scores.begin()+2);
  ```

- insert()，第一个参数指定新元素插入的位置，第二个和第三定义了被插入区间

  ```c++
  old_v.insert(old_v.begin,new_v.begin()+1,new_v.end());
  ```

  

#### STL函数

for_each(),random_shuffle()和sort()

for_each()函数可用于很多容器，接收3个参数。前两个容器区间的迭代器，最后一个是指向函数的指针（最后一个参数是一个函数对象）

```c++
for(auto pr=books.begin();pr!=books.end();pr++)
{
	ShowReview(*pr)
}

for_each(books.begin(),books.end(),ShowReview);
```

randmo_shuffle()随机排列books矢量中的所有元素

```c++
randmo_shuffle(books.begin(),books.end());
```

sort()如果容器元素是用户定义的对象，需要定义能够处理该对象的operator<()函数



#### 基于范围的for循环(C++11)

```c++
double prices[5]={4.5, 10, 11, 15.2, 13};
for(auto x:prices)
{
	cout << x<<endl;
}
```

基于范围的for循环可以修改容器的内容

```c++
for_each(books.begin(),books.end(),ShowReview);
for(auto & x:books) InflateReview(x);
```







### 16.4 泛型编程

泛型编程是编写独立于数据类型的代码。STL是一种泛型编程

泛型编程意在使用同一个find函数来处理数组、链表或任何其他容器类型。





#### 16.4.1 为何使用迭代器

- 每个容器类定义了相应的迭代器类型，迭代器可能是指针，可能是对象
- 迭代器提供所需要的操作，若*和++
- 每个容器类都有一个超尾标记
- 每个容器都有begin()和end()方法
- 每个容器类都使用++操作，让迭代器从第一个元素逐步指向超尾位置

```c++
//对于类
Struct Node
{
    double item;
    Node* p_next;
}

class iterator
{
    Node *pt;
public:
    iterator():pt(0){}
    ...;
    double operator*(){return pt->item;}
    iterator operator++()	//for ++it
    {
        pt=pt->next;
        return *this;
    }
    
    iterator operator++(int)	//for it++
    {
        return *this;
        pt=pt->next;
    }
        
}
```

operator++作为前缀版本，operator++(int)作为后缀版本

```c++
//对于类
iterator find_ll(iterator head,const double&val)
{
    iterator start;
    for(start=head;start!=0;++start)
    {
        if(*start==val)
            return start;
        return 0;
    }
}
//对于指针
vector<double>::iterator pr;
for(pr=scores.begin();pr!=scores.end();pr++)
{
    cout << *pr<<endl;
}
```

尽可能直接使用stl函数如（for-each())



#### 16.4.2 迭代器类型

STL定义了5种迭代器

输入迭代器，输出迭代器，正向迭代器，双向迭代器和随机访问迭代器

##### 1.输入迭代器

输入从程序角度来说，来自容器的信息被视为输入，输入迭代器被程序用来读取容器中的信息。

输入迭代器是单项迭代器，可以递增不能倒退



##### 2.输出迭代器

输出指用于将信息从程序传输给容器的迭代器。可以修改容器的值，但是不能读取

单通行



##### 3.正向迭代器

正向迭代器只使用++来遍历容器

它总是按相同的顺序遍历容器，可以多次通行

可以读取和修改数据，也可以只能读取数据

```c++
int *ptr;
const int*ptr1;
```



##### 4.双向迭代器

能双向遍历容器

双向迭代器具有正向迭代器所有特性，同时支持前后缀的递减运算



##### 5.随机访问迭代器

要求能够直接跳到容器中的任何一个元素，叫做随机访问

随机访问迭代器具有双向迭代器的所有特性，同时支持随机访问

![image-20220418160423318](https://s2.loli.net/2022/05/06/zAYIFgMx75EJkZu.png)





#### 16.4.3 迭代器层次特性

![image-20220418160523855](https://s2.loli.net/2022/05/06/i84VOC7BY16EwoA.png)



每个容器类都定义了个类级迭代器。例如vector<int>类的迭代器vector<int>::iterator

矢量迭代器是随机访问迭代器。

list<int>的迭代器是双向链表，他使用双向迭代器不支持随机访问





#### 16.4.4 概念、改进和模型



##### 1.将指针用作迭代器

迭代器是广义指针



**sort()函数**

sort()函数接受指向第一个元素的迭代器和超尾的迭代器作为参数

```c++
const int SIZE=100;
double Rec[SIZE];
sort(Rec,Rec+SIZE);
```

C++支持将超尾概念用于数组



**copy()函数**

```c++
int casts[10]={6,7,2,3,5,1,8,5,5,1};
vector<int> dice[10];
copy(casts,casts+10,dice.begin());
```

copy()的前两个选代器参数表示要复制的范围,最后一个迭代器参数表示要将第一个元素复制到什么位置。前两个参数必须是(或最好是)输入选代器,最后一个参数必须是(或最好是)输出选代器。Copy()函数将覆盖目标容器中已有的数据,同时目标容器必须足够大,以便能够容纳被复制的元素。因此,不能,使用copy()将数据放到空矢量中。

```c++
#include <iterator>
ostream_iterator<int,char>out_iter(cout," ");
```

第一个模板参数指出被发送给输出流的数据类型，第二个模板参数指出了输出流使用的字符类型构造函数第一个参数cout指出了使用的输出流，第二个参数是发送给输出流每个数据项后的分隔符

```c++
*out_iter++ = 15;//works like cout << 15 <<" ";
```

```c++
copy(dice.begin(),dice.end().out_iter);//将dice容器中的这点那个区间复制到输出流
```

```c++
copy(istream_iterator<int,char>(cin),istream_iterator<int,char>(),dice.begin());
```

istream_iterator模板参数与ostream_iterator相同，构造函数参数使用cin管理的输入流，省略构造函数参数表示输入失败



##### 2.其他有用的迭代器

reverse_iterator,back_insert_iterator,front_insert_iterator和insert_iterator

vector有一个名为rbegin()，rend()的成员函数，对迭代器执行递增操作，将导致其递减

```c++
copy(dice.rbegin(),dice.rend(),out_iter);
```

rbeign()和end()返回相同的超尾值，但类型不同(reserve_iterator和iterator)

反向指针通过先递减，再解除引用。

rp指向位置6，则*rp将是位置5的值

```c++
vector<int>::reserve_iterator ri;
for(ri=dice.regin();ri!=dice.rend();++ri)
{
    cout << *ri<<' ';
}
```



back_insert_iterator将元素插入到容器尾部

front_insert_iterator将容器插入到容器的前端

insert_iterator将元素插入到insert_iterator构造函数的参数指定的位置前面

这些迭代器将容器类型作为模板参数，将实际的容器标识符作为构造函数参数

```c++
back_insert_iterator<vector<int>> back_iter(dice);
```

back_insert_iterator的构造函数将假设传递给它的类型有一个push_back()方法

```c++
back_insert_iterator<vector<int>> back_iter(dice,dice.begin());
```

```c++
string s1[4]={"fine","fish","fashion","fate"};
vector<string> words(4);
copy(s1,s1+4,words.begin());
for_each(words.begin(),words.end(),ostream_iterator<int,char>(cout,' '));
copy(s2,s2+4,back_insert_iterator<vector<string>>(words));
for_each(words.begin(),words.end(),ostream_iterator<int,char>(cout,' '));
copy(s3,s3+4,insert_iterator<vector<string>>(words,words.begin()));
for_each(words.begin(),words.end(),ostream_iterator<int,char>(cout,' '));
```



#### 16.4.5 容器种类

概念是具有名称(容器、序列容器、关联容器等)的通用类别

deque	list	queue	priority_queue	stack	vector	map	multimap	set	multiset	

容器是存储其他对象的对象。被存储的对象必须是一种类型的

类型必须是可复制构造的和可赋值的对象才可以存储在容器中![image-20220418202140118](https://s2.loli.net/2022/05/06/I2ULEFwpBGr4z6W.png)![image-20220418202247874](https://s2.loli.net/2022/05/06/qcD8uf5BGdxmNXs.png)



##### 序列

7中stl容器类型deque	forward_list	list	queue	priority_queue	stack	vector都是序列

队列可以在队尾添加元素，队首删除元素。deque表示双端队列允许在两端添加和删除元素

![image-20220418203735184](https://s2.loli.net/2022/05/06/WJ3jZgdLnRUGAyO.png)

![image-20220418203127195](https://s2.loli.net/2022/05/06/XfGaKVA1Nz5CQYv.png)

如果n落在容器的有效区间外，则a.at(n)将执行边界检查，引发out_of_range异常



###### vector



###### deque

deque表示双端队列，在开始位置插入和删除元素时间是固定的，而不是vector那样线性的。

支持随机访问



###### list

list表示双向链表

list和vector在链表中任意位置进行插入和删除的时间都是固定的。

vector可以进行随机访问而list强调元素的快速插入和删除

![image-20220418203604483](C:\Users\AiYou_\AppData\Roaming\Typora\typora-user-images\image-20220418203604483.png)

```c++
list<int> one(5,2);
int stuff[5]={1,2,4,5,6};
list<int> two;
two.insert(two.begin(),stuff,stuff+5);
list<int> three(two);

three.remove(2);//删除2
three.splice(three.begin(),one);//将one中的内容都剪切到three.begin()的前面
three.unique();//将连续相同的元素压缩为单一元素
three.sort();//排序
two.sort();
three.merge(two);//将两个排序后的链表合并
```

**非成员函数sort**需要随机访问迭代器，所以list不能用非成员函数sort



###### forward_list

它实现了单链表，只需要正向迭代器



###### queue

不支持随机访问队列元素，不允许遍历队列，可以将元素插入队尾，从队首删除元素，查看队首和队尾的值，检查元素数目和测试队列是否为空

![image-20220418211633848](C:\Users\AiYou_\AppData\Roaming\Typora\typora-user-images\image-20220418211633848.png)

###### priority_queue

priority_queue中，最大元素被移动到队首

```c++
priority_queue<int> pq1;
priority_queue<int> pq2(greater<int>);
```

- top 访问队头元素
- empty 队列是否为空
- size 返回队列内元素个数
- push 插入元素到队尾 (并排序)
- emplace 原地构造一个元素并插入队列
- pop 弹出队头元素
- swap 交换内容

```c++
priority_queue<Type, Container, Functional>;
//升序队列
priority_queue <int,vector<int>,greater<int> > q;
//降序队列
priority_queue <int,vector<int>,less<int> >q;
```





###### stack

###### stack![image-20220418212100767](https://s2.loli.net/2022/05/06/f8rsuhzOYjvqtm1.png)

它非STL容器，其长度是固定的。不能使用push_back和insert



##### 关联容器

关联容器将值与键关联在一起

对于容器X，X::key_type表示键的类型，X::value_type表示值的类型

关联容器提供对元素的快速访问，允许插入新元素，但是不允许指定元素的位置

关联容器本质是由某种树实现

四种关联容器：set	multiset	map	multimap

set值和键是相同，键是惟一的

multiset可以有多个值的键相同

map中，值和键的类型不同，键是唯一的



###### set

```c++
set<string> A;
```

默认情况下使用less<>

```c++
set<string,less<string>> A;
```



**set_union()函数**

set_union()是求两个集合的并集,最后一个参数为输出迭代器

```c++
set_union(A.begin(),A.end(),B.beign(),B.end(),ostream_iterator<string,char>out(cout," "));
```

其类似于copy()，覆盖容器中已有数据但是并不会插入。使用insert_iterator

```
set_union(A.begin(),A.end(),B.beign(),B.end(),insert_iterator<set<string>>(C,C.begin()));
```

**set_intersection()**和**set_difference()**分别为查找交集和差集，其接口与set_union()相同

**lower_bound()**将键作为参数返回迭代器，指向集合中第一个不小于键参数的成员

**upper_bound()**将键作为参数返回迭代器，指向集合中第一个不大于键参数的成员

```
copy(C.lower_bound("ghost"),C.upper_bound("spook"),out)
```





###### multimap

键和值的类型不同，且一个键可与多个值相关联

```c++
multimap<int,string>codes;
```

将使用模板less<>

STL使用模板类pair<class T,class U>将两种值存储到一个对象

```c++
pair<const int ,string>item(213,"Los Angeles");
codes.insert(item);
```

```
codes.insert(pair<const int ,string>item(213,"Los Angeles");)
```

```c++
pair<const int ,string>item(213,"Los Angeles");
cout << (*it).first<' '<<(*it).second<<endl;
```

成员函数count()接收键作为参数，并返回具有该键的元素数目

equal_range()用键作为参数，且返回两个迭代器，他们表示的区间与该键匹配

```c++
pair<multimap<KeyType,string>::iterator,multimap<KeyType,string>::iterator> range = codes.equal_range(718);
multimap<KeyTyep,string>::iterator it;
for(it = range.first;it!=range.second;++it)
    cout << (*it).second<< endl;
```

```c++
auto range=codes.equal_range(718);
```





### 16.5 函数对象

函数对象也叫函数符。函数符是可以函数方式与()结合使用的任意对象

这包括函数名、指向函数的指针和重载()运算符的类对象

```c++
template<class InputIterator,class Function>
Function for_each(InputIterator first, InputIterator last, Function f);
```

```c++
for_each(books.begin(),books.end(),ShowReview);
```

void ShowReview(const Review &);

ShowReview的类型将为函数指针void(*)(const Review&);

for_each代码具有一个使用f()的表达式，对于ShowReview来说，f是指向函数的指针。如果为对象，则会调用其重载的()运算符的对象



#### 16.5.1函数符概念

生成器(generator)是不用参数就可以调用的函数符。

一元函数.(unary function)是用一个参数可以调用的函数符。

二元函数(binary function).是用两个参数可以调用的函数符。

返回bool值的一元函数是谓词

返回bool值的二元函数是二元谓词



sort()函数具有使用二元谓词版本

```c++
bool WorseThan(const Review &r1,const Review &r2);
sort(books.begin(),books.end(),WorseThan);
```



list模板具有remove_if()成员

```c++
bool tooBig(int n){return n>100};
list<int>scores;
scores.remove_if(tooBig)
```

假设要删除链表中大于20的值，可以使用类函数符

```c++
Template<class T>
class TooBig
{
private:
    T cutoff;
public:
    TooBig(const T& t):cutoff(t){}
    bool operator()(const T& v){return v>cutoff;}
};


TooBig<int> f(100);
scores.remove_if(f);//删除大于100的值
scores.remove_if(TooBig<int>(200));//删除大于200的值
```



可以使用初始化列表来简化初始化

```c++
int vals[10]={50,100,90,180,...};
list<int> yada(vals,vals+10);
//可简化
list<int> yada{50,100,90,180,...};
list<int> yada={50,100,90,180,...};
```





#### 16.5.2 预定义的函数符

###### transform()

```c++
//函数符是单个参数的函数符
template<class InputIterator,class OutputIterator,class Function>
void transform(InputIterator first,InputIterator end,OutputIterator ite);
void transform(InputIterator first,InputIterator end,OutputIterator ite,Fucntion f);

//函数符是两个参数的函数符
template<class InputIterator1,class InputIterator2,class OutputIterator,class Function>
void transform(InputIterator1 first,InputIterator1 end,InputIterator2 ite0, OutputIterator ite,Fucntion f);
```

```c++
//单参数函数符
vector<double> gre{35,32,52,16};
ostream_iterator<double,char>out(cout,' ');
transform(gre.begin(),gre.end(),out);

//双参数函数符求和两个区间
double add(double x,double y){return x+y};
transfrom(gre.begin(),gre.end(),gre1.begin(),out,add);
```



###### plus<>双参数加法函数符

```c++
plus<double> add;
transfrom(gre.begin(),gre.end(),gre1.begin(),out,add);
transfrom(gre.begin(),gre.end(),gre1.begin(),out,plus<doubel>());
```



###### 运算符和相应函数符

![image-20220419160606798](https://s2.loli.net/2022/05/06/8yFNA5LpDcO4SnZ.png)





#### 16.5.3 自适应函数符和函数适配器



自适应生成器

自适应一元函数

自适应二元函数

自适应谓词

自适应二元谓词



STL提供binder1st和binder2nd类完成将自适应二元函数转换为自适应一元函数

```c++
//自适应二元函数对象f2(),创建binder1st对象，将f2和用于f2的第一个参数val用于其构造函数参数
binder1st(f2,val) f1;
```



```c++
template<class T>
class multiplies2_5
{
private:
    T val;
public:
    multiplies2_5(const T& t):val(t){}
    const T operator()(const T& v){reutrn plus<T>(val,v)} 
};

//使用类对象
transfrom(gre.begin(),gre.end(),out,multipies2_5<double>(2.5));
//使用自适应函数符
binderlist(multipies<double>(),5) multiplies2_5;
transfrom(gre.begin(),gre.end(),out,multiplies2_5);
```





### 16.6 算法

​	统一的容器设计使得不同类型的容器之间具有明显关系。例如,可以使用copy()将常规数组中的值复制到vector对象中,将vector对象中的值复制到list对象中,将list对象中的值复制到set对象中。可以用==来比较不同类型的容器,如deque和vector。之所以能够这样做,是因为容器重载的==运算符使用选代器来比较内容,因此如果deque对象和vector对象的内容相同,并且排列顺序也相同,则它们是相等的。



#### 16.6.1算法组

- 非修改式序列操作：for_each()
- 修改式序列操作: transform(),random_shuffle() copy()
- 排序和相关操作: sort()
- 通用数字运算



#### 16.6.2算法的通用特征



copy()函数原型

```c++
template<class InputIterator,class OutputIterator>
OutputIterator copy(InputIterator first,InputIterator last,OutputIterator result);
```

算法按照结果放置位置分为就地版本和复制版本

```c++
//就地版本
template<class ForwardIterator,class T>
void replace(ForwardIterator first,ForwardIterator last,const T& old_val, const T& new_value);

//复制版本,返回一个迭代器，该迭代器指向复制的最后一个值后面的一个位置
template<class InputIterator,class OutputIterator,class T>
OutputIterator replace_copy(InputIterator first,InputIterator last,OutputIterator result,const T& old_val, const T& new_value);
```





#### 16.6.4 函数和容器方法

删除链表中某个特定的值可以使用成员函数或者STL方法

成员函数，可以删除元素，链表长度自动调整。

STL算法将未被删除的元素放在链表开始位置，并返回一个指向新的超位置迭代器

```c++
list<int> la,lb;
la.remove(4);

list<int>::iterator last;
last=remove(lb.begin(),lb.end(),4);
lb.erase(last,lb.end);
```



编写程序，让用户输入单词。得到按输入顺序的单词列表。字母排序顺序的单词列表。并记录每个单词被输入的次数。

```c++
#include <iostream>
#include <set>
#include <vector>
#include <map>
#include <string>
#include <algorithm>
#include <iterator>
using namespace std;

void out(const string &str)
{
	cout << str << " ";
}
string &ToLower(string &str)
{
	transform(str.begin(), str.end(), str.begin(), tolower);
	return str;
}

int main()
{
	cout << "请输入单词 " << endl;
	string input;
	vector <string> words;
	set<string> words_set;
	map<string, int> words_map;

	while (cin>>input && input!="quit")
	{
		words.push_back(input);
	}
	cout << "输入顺序的单词列表" << endl;
	for_each(words.begin(), words.end(), out);
	cout << endl;

	
	transform(words.begin(), words.end(), insert_iterator<set<string>>(words_set, words_set.begin()),ToLower);
	cout << "排序的单词列表" << endl;
	for_each(words.begin(), words.end(), out);
	cout << endl;

	for (auto si = words_set.begin(); si != words_set.end(); ++si)
	{
		//cout << *si << endl;
		words_map[*si] = count(words.begin(), words.end(), *si);
	}
	
	for (auto si = words_set.begin(); si != words_set.end(); ++si)
	{
		cout << *si << ":" << words_map[*si] << endl;
	}
	
	return 0;
}

```







### 16.7 其他库



#### 16.7.1 vector, valarray和array

- vector
- valarray面向数值计算。没有push_back()和insert()
- array表示长度固定的数组。没有push_back()和insert()。提高STL方法，begin(),end(),rbegin()和rend()

```c++
vector<double> ved(10),ved1(10),ved2(10);;
array<double,10> vod,vod1,vod2;
valarray<double> vad(10),vad1(10),vad2(10);
```

```c++
transform(ved.begin(),ved.end(),ved1.begin(),ved1.end(),ved2.begin(),plus<double>());

//array可以使用stl
transform(vod.begin(),vod.end(),vod1.begin(),vod1.end(),vod2.begin(),plus<double>());

//valarray重载了所有的算术运算符
vad2=vad+vad1;
vad2=vad*vad1;

//数组每个元素扩大2.5倍
transform(ved.begin(),ved.end(),ved2.begin(),bind1st(multiplies<double>(),2.5));

vad2=vad2*2.5;
vad3=log(vad1);//重载了数学函数
vad3=vad1.apply(log);//适用于非重载函数
```

valarray提供了sum(),size(),max(),min()

```c++
//创建bool数组
valarray<double> numbers(10);
valarray<bool>=numbers>9;
```

slice类指定下标

slice对象被初始化为三个整数值：起始索引，索引数和跨距

slice(1,4,3)索引的分别为1,4,7,10

```
valarray<double> varint(11);
varint[slice(1,4,3)]=10;
```

valarray定义了和单个int元素定义了运算符+





#### 16.7.2 模板initializer_list

容器类将initializer_list<T>作为参数的构造函数

```c++
vector<double> payments{15.99,12.55,13.66,42.55};
```

问题：

```c++
vector<double> v{10};	//?
vector<double> v(10);	//10个元素
vector<double> v({10});	//1个为10的元素
```

如果类接收initializer_list为参数，则该语法对应第二种

**所有initializer_list元素的类型必须相同，不能进行窄化转换**

```c++
vector<int> payments{10,8,5.5};//narrowing
```

```c++
Position A={20,-3}; //将调用Position(int,int,int);
```





#### 16.7.3 使用initializer_list

```c++
#include<initializer_list>
double average(const std:initializer_list<double> & ril);

std:initializer_list<double> dl={1.1,2.2,3.3,4.4};
cout << average(dl);
dl={2.2, 3.5, 4.4};
```

initializer_list的迭代器类型为const，不能修改initializer_list的值























## 第十七章 输入、输出和文件







### 17.1 C++输入和输出概述



缓冲区是用作中介的内存块，将信息从设备传输到程序或从程序传输给设备的临时存储工具。

缓冲方法则从磁盘读取大量信息，将这些信息存储在缓存区中，然后每次从缓冲区中读取一个字节。从内存中读取单个字节要比从硬盘上快得多

C++程序通常在用户发送换行符时刷新输入输出缓存区



#### 17.1.2 流、缓冲区和iostream文件

- streambuf类为缓冲器提供了内存，并提供了用于填充缓冲区，访问缓冲区内容，刷新缓冲区和管理缓冲区内存的类方法
- ios_base表示流的一般特征，如是否可读取，是二进制流等
- ios类基于ios_base，其中包括了一个指向streambuf对象的指针成员
- ostream类继承ios
- istream类继承ios
- iostream类继承istream和ostream类



C++11标准提供了I/O的char 和wchar_t具体化。istream和ostream都是char具体化



iostream文件将自动创建8个流对象：

cin对象对应于标准输入流，wcin对应宽字符

cout对象对应于标准输出流，wcout对应于宽字符

cerr对象与标准错误流对应。这个流不会被缓冲。wcerr对应宽字符

clog对象对应着标准错误六，这个流被缓冲。wclog





#### 17.1.3 重定向



通过输入重定向(<)和输出重定向(>)，可以使用使用一个名为counter.exe来计算oklahma中字符数，并将结果放到cow_cnt文件中

```
cow_cnt file;
C>counter <oklahoma>cow_cnt
```







### 17.2 使用cout进行输出

ostream类最重要的任务之一是将数值类型(int和float)转换为以文本形式表示的字符流

ostream类将数据内部表示转换为由字符字节组成的输出流



#### 17.2.1 重载的<<运算符

```c++
cout << value;
ostream & operator<<(int);
```

C++输出流可以输出所有基本类型



##### 输出指针类型

- const signed char*
- const unsigned char*
- const char*
- void*

```c++
char name[20]="happy";
char *pr="sad";
cout << "hello";
cout << pr;
cout << name;
```

对于其他类型的指针，C++将其应用与void*，并打印地址的数值表示，如果想要获得字符串的地址，必须将其强制转换为其他类型

```c++
int eggs=12;
char * amount ="dozen";
cout << &eggs;		//address
cout << amount;		//string
cout << (void*) amount;	//address
```



#### 17.2.2 其他ostream方法

ostream类还提供了put()方法和write()方法。前者用于显示字符，后者用于显示字符串。

put()方法

```c++
ostream &put(char);

cout.put('W');
cout.put('I').put('t');
//函数原型自动将参数转换为char
cout.put(65);	//display A charactor
cout.put(66.3);	//display B charactor
```

write()方法

```c++
basic_ostream<charT,traits>&write(const char_type*s,streamsize n);
//第一个参数提供显示的字符串地址，第二个参数指出要显示多少字符
```

```c++
const char* state1="florida";
const char* state2="kkkasbs";
cout.write(state2,1);
cout.write(state2,3);
```

write()方法用于数值数据，将数字地址强制转换为char*

```c++
long val=560031841;
cout.write((char*)&val,sizeof(long));
//560031841作为4个独立的字节被传输
```







#### 17.2.3 刷新输出缓冲区

cout对象将输出存储到缓冲区中，直到缓冲区填满。然后程序将刷新（flush）缓冲区，把内容发送出去，并清空缓冲区。

```c++
cout <<"Hello" << flush;
cout <<"wait" << endl;
```

控制符flush刷新缓冲区，而控制符endl刷新缓冲区并插入一个换行符

控制符也是函数，可以直接调用flush()刷新cout缓冲区

```c++
flush(cout);
cout <<flush;
```



#### 17.2.4 用cout进行格式化

浮点类型被显示为6位，末尾的0不显示

数字当指数大于等于6或小于等于-5时，将使用科学计数法表示



通过成员函数可以控制字段宽度和小数位数

##### 1.修改计数系统

控制符dec, hex 和oct控制符可以将格式设置为不同进制

```c++
hex(cout);
cout<<hex;
```

控制符位于名称空间std中



##### 2.调整字段宽度

```c++
int width();
int width(int i);
```

第一个返回字段宽度

第二个设置字段宽度并返回以前的字段宽度值

width()方法只影响将显示的下一个项目，然后将恢复默认值

```c++
cout << '#';
cout.width(12);
cout<<12<<"#"<<24<<endl;
//#			12#24#
```

右对齐，如果试图在宽度为2的字段中打印一个7位置，C++将增宽字段，以容纳改数据



##### 3.填充字符

fill()函数改变填充字符，

```
cout.fill('*');
```

与字符宽度不同，新的填充字符一直有效，直到更改他为止



##### 4.设置浮点数的显示精度

在定点模式和科学模式下，精度指的是小数点后的位数。C++的默认精度为6位。

```c++
cout.precision(2);
```

新的精度设置一直有效；



##### 5.打印末尾的0和小数点

ios_base提供一个setf()函数

```c++
cout.setf(ios_base::showpoint);
```

此时2.00不显示2，将显示为2.00000



##### 6.再谈setf()

```c++
fmtflags setf(fmtflags);
```

![image-20220425221433086](https://s2.loli.net/2022/05/06/mMzgDtf8sByWlA2.png)

```c++
//63
cout.setf(ios_base::showpos);	//+63
cout<<hex;	//3f
cout.setf(ios_base::uppercase);	
cout.setf(ios_base::showbase);	//0X3F
cout.setf(ios_base::boolalpha);	//ture
```

双参数版本

```c++
fmtflags setf(fmtflags fmtflags);
```

![image-20220425222038338](https://s2.loli.net/2022/05/06/ESWvALktCh6q4Fn.png)

![image-20220425222048306](https://s2.loli.net/2022/05/06/YyKPCE2znmgoID4.png)

```c++
//恢复旧的设置
ios_base::fmtflags old=cout.setf(ios::left,ios::adjustfield);
cout.setf(old,ios::adjustefield);
```

精度3让默认的浮点显示总共显示3位，而定点模式和科学模式只显示3位小数

setf()的效果可以通过unsetf()消除

![image-20220425222519169](https://s2.loli.net/2022/05/06/1HVoG6xDc3vYAue.png)



##### 7.标准控制符

C++提供控制符可以调用setf()

```
cout << left << endl;
```

![image-20220425223001481](https://s2.loli.net/2022/05/06/ZorygPju1ch7tVf.png)![image-20220425223031243](https://s2.loli.net/2022/05/06/5d8RZEqrCxoMiym.png)





##### 8.头文件iomanip

setprecision()，setfill()和setw()分别设置精度，填充字段和字段宽度

```
cout<<setw(6)<<setfill('.')<<n<<setfill(' ')
	<<setw(12)<<setprecision(3)<<root
	<<setw(14)<<setprecision(4)<<sqrt(root)<<endl;
```













### 17.3 使用cin输入

```c++
cin>>value_holder;
```

value_holder可以是变量，引用，被解除引用的指针，可以是类，可以是结构成员

运算符函数被称为格式化输入函数，将输入数据转换为目标指定格式

```c++
istream & operator>>(int &);
```





#### 17.3.1 cin>>检查输入

抽取运算符跳过空白（空格，换行符和制表符）直到遇到非空白字符

抽取运算符将读取指定类型的数据，直到与目标类型不匹配

```C++
int elevation;
cin>>elevation;
//输入123Z
//elevation=123,Z将留在输入流中，下个cin从Z开始读取

//输入Zcar，将不会修改elevation的值
```



```c++
void main()
{
	int input;
	while (cin >> input)
	{	
		cout << input << endl;
	}
	cout << "last value=" << input << endl;
}
//由于键入不符合浮点格式，将导致cin>>input返回false
```





#### 17.3.2 流状态

流状态由3个ios_base元素组成：eofbit, badbit和failbit

cin到达文件尾设置eofbit

cin未能读取到预期字符，或者I/O失败也会设置failbit

无法诊断的失败破坏流，badbit元素被设置

当三个元素全部被置为0，说明一切顺利

![image-20220426093342931](https://s2.loli.net/2022/05/06/irPCHLJ1Zzp9GKV.png)

clear()和setstate()，都重置状态。

```c++
clear();
//将清除3个状态位（eofbit,badbit,failbit)
```

```c++
setstate(eofbit);
//将设置eofbit
```



##### 2.I/O和异常

可以使用exceptions()方法控制异常处理

excepitons()方法返回一个位字段，分别对应eofbit，failbit和badbit

excepitons()默认设置为goodbit，可以重载exceptions(iostate)使得能够控制其行为。ios_base::failure异常类从std::exception类派生而来，包含一个what()方法。

```c++
cin.exceptions(badbit);
```

```c++
int main()
{
	cin.exceptions(ios_base::failbit);
	int input,sum=0;
	try{
		while(cin>>input)
		{
			sum+=input;
		}
	}catch(ios_base::failure &bf)
	{
		cout << bf.what()<<endl;
	}
	return 0;
}
```





##### 3.流状态的影响

```c++
while(cin>>input)
{
    sum+=input;
}
if(cin.eof())
    cout<<"EOF"<<endl;
cout << sum<<endl;
cin>>input;	//won't work;
```

设置流状态将对后面的输入或输出关闭，直到位被清除

如果希望程序在流状态被设置后能够读取后面的输入，就必须将流状态重置

```c++
while(cin>>input)
{
    sum+=input;
}
if(cin.eof())
    cout<<"EOF"<<endl;
cout << sum<<endl;
cin.clear();	//reset stream state
while(!isspace(cin.get()))
    continue;
cin>>input;
```

isspace()函数在参数为空白符时返回true

```c++
//类似
while(cin.get()!='\n')
    continue;
```



假设循环由于到达文件尾或由于硬件故障而终止，可以使用fail()方法检测假设是否正确。fail()在failbit或eofbit被设置时返回true

```c++
while(cin>>input)
{
    sum+=input;
}
if(cin.fail()&& !cin.eof())
{
	cin.clear();
	while(!isspace(cin.get()))
    continue;
}else
{
	cout<<"i can't go on!";
	exit(1);
}
cin>>input;
```







#### 17.3.3 其他istream方法

非格式化输入函数，只是读取字符输入，不会跳过空白，不进行数据转换

get(char&)和get(void)提供不跳过空白的单字符输入

get(char*,int,char)和getline(char*,int,cahr)默认情况读取整行



##### 1.单字符输入

get(char&)将输入字符赋给参数和get(void)将输入字符转换为整型



(1)成员函数get(char&)

```c++
while(ch!='\n')
{
	cout<<ch;
    ct++;
	cin.get(ch);
}
//输入 i c++ clearly<Enter>
//输出 i c++ clearly
```

遇到回车终止循环

```c++
while(ch!='\n')
{
	cout<<ch;
    ct++;
	cin>>ch;
}
//输入 i c++ clearly<Enter>
//输出 ic++clearly
//并且不会停止循环
```





（2）成员函数get(void)

依旧读取空白，将返回值输入传递给程序,返回值为int类型，或者更大的整型

```c++
ch=cin.get();
```

![image-20220428215918881](https://s2.loli.net/2022/05/06/mUbgvuF9LYePlSp.png)





##### 2.选择哪种单字符输入形式

```c++
>>	get(char&)	get(void)
```

希望跳过空白，选择抽取运算符>>





##### 3.字符串输入:getline()，get()和ignore()

get()和getline()的主要区别在于get()将换行符留在输入流中，getline()抽取并丢弃输入流中的换行符

```c++
istream & get(char*,int, char);
istream & get(char*,int);
istream & getline(char*,int,char);
istream & getline(char*,int);
```

第一个参数用于放置输入字符串的内存单元的地址

第二参数必要读取的最大字符数大1

第三个参数指定用作分解符的字符

```c++
char line[50];
cin.get(line,50);
```

ignore()成员函数，接收两个参数。一个为要读取的最大字符数，另一个是字符，用作输入分界符

```c++
cin.ignore(255,'\n');
```

读取并丢弃接下来的255个字符或直到到达第一个换行符,并丢弃换行符

```c++
//函数原型
istream & ignore(int =1,int =EOF);
```

```
const int Limit=255;
char input[Limit];
cin.getline(input,Limit,'#');

char ch;
cin.get(ch);

if(ch!='\n')
	cin.ignore(Limit,'\n');
```





##### 4.意外字符串输入

get(char*,int)和getline()的某些输入形式将影响流状态。其也会设置eofbit和badbit

对于get(char*,int)来说，输入空行会导致无法抽取字符

```c++
char temp[80];
while(cin.get(temp,80))
{
    
}
```

对于getline()来说，空行不会导致其设置为failbit，因为getline()仍将抽取换行符

若希望其遇到空行终止循环，则可以

```c++
char temp[80];
while (cin.getline(temp,80)&&temp[0]!='\0')
{

}
```





cin.getline(temp,30)

- 遇到文件尾设置eofbit
- 读取29个字符，并且下个字符不是换行符，则设置failbit

cin.get(char*,int)

- 如果没有读取任何字符则设置faibit





#### 17.3.4 其他istream方法

read()	peek()	gcount()

read()读取指定书目的字节，并存储在指定位置

```c++
char gross[144];
cin.read(gross,144);
```



peek()函数返回输入中的下个字符，但是不抽取输入流中的字符

```c++
ch=cin.peek()
```



gcount()方法返回最后一个非格式化抽取方法读取的字符数



putback()函数将一个字符插入到输入字符串中，被插入的字符将是下调输入语句读取的第一个字符



删除未读取完的余下内容	

```c++
inline void eatline()
{
	while(cin.get()!='\n')
		continue;
}
```













### 17.4 文件输入和输出

写入文件，创建ofstream对象， 使用<<插入运算符或writer()

读取文件，创建ifstream对象，使用>>抽取运算符或get()



#### 17.4.1 简单的文件I/O

```c++
ofstream fout;
fout.open("jar.txt");

//构造函数
ofstream fout("jar.txt");

//将字符串放入文件
fout<<"Dull data";
```

ofstream对象从程序逐字节收集输出，当缓冲区填满后，将缓冲区内容传给目标文件

以默认方式打开文件进行输出将自动把文件的长度截短为零，相当于删除已有内容



```c++
ifstream fin;
fin.open("jar.txt");

//构造函数
ifstream fin("jar.txt");

char ch;
fin>>ch;
char buf[80];
fin.getline(buf,80);
string line;
getline(fin,lin);
```

fin对象管理输入缓冲区

```c++
fout.close();
fin.close();
//关闭文件链接
```



将文件名读取到string对象，可以使用c-str()将其提供给ofstream和ifstream的构造函数

```c++
string filename;
ofstream fout(filename.c_str());
```







#### 17.4.2 流状态检查和is_open()

C++文件流类从ios_base继承了流状态程艳

试图打开一个不存在的文件进行输入时，将设置failbit位

```c++
fin.open(argv[file]);
if(fin.fail()){}
```

```c++
if(!fin.is_open()){}
```





#### 17.4.3 打开多个文件

打开一个流，可以将其依次关联到各个文件

```c++
ifstream fin;
fin.open("far.txt");
...
fin.close();
fin.clear();

fin.open("rat.txt");
...
fin.close();
```





#### 17.4.4 命令行处理技术

```c++
wc report1 report2 report3
```

C++可以在命令行环境中运行的机制

```c++
int main(int argc,char* argv[]);
```

argc为命令行的参数个数，包括命令本身

argv变量为指针

上例，argc为4，argv[0]为wc，argv[1]为report以此类推

```c++
for(int i=0;i<argc;i++)
{
	cout << argv[i]<<endl;
}
```





#### 17.4.5 文件模式

文件模式描述的是文件将被如何使用：读，写，追加等等

可以在初始化文件流对象，或者open()方法，提供文件模式的第二参数

```
ifstream fin("far.txt",mode1);
ofstream fout;
fout.open("rat.txt",mode2);
```

![image-20220429154722956](https://s2.loli.net/2022/04/29/zb489e7pLHnXkvw.png)

ifstream open()方法和构造函数使用ios_base::in(打开文件来读取)作为默认值

ofstream open()方法和构造函数使用ios_base::out|ios_base::trunc(打开文件，写入并截短文件)

fstream类不提供默认的模式值，必须显示提供模式

```c++
ofstream fout("bagels",ios_base::out|ios_base::app);
```



```c++
//c++
ifstream fin(filename,C++mode);
//C
fopen(filename,cmode);
```

C++mode是一个openmode值，ios_base::in

Cmode是相应的C模式字符串，如"r"

![image-20220429160953502](https://s2.loli.net/2022/04/29/lKEYVnwNmFij5x7.png)ios_base::ate和ios_base::app都将文件指针指向打开的文件尾。

ios_base::app将数据添加到文件尾，ios_base::ate将指针放到文件尾



##### 2.二进制文件

将数据存储在文件中，可以将其存储为文本格式或二进制格式

对于字符来说，二进制表示与文本表示一样，即ASCII码的二进制表示

对于数字来说，差别较大。

![image-20220429161853205](https://s2.loli.net/2022/04/29/GFONKkeIg4oW9As.png)

二进制格式对于数字来说更加精确，其不会有转换误差或舍入误差。

二进制保存数据的速度更快不需要转换，可以大块地存储数据，其通常占用空间较小



例：

```c++
const int LIM=20;
struct planet
{
	char name[LIM];
	double population;
	double g;
};
planet pl;
```

```c++
//文本格式
ofstream fout("planets.dat",ios_base::out|ios_base::app);
fout<<pl.name<<" "<<pl.population<<" "<<pl.g<<"\n";
```

```c++
//二进制格式
ofstream fout("planets.dat",ios_base::out|ios_base::binary);
fout.write((char*)&pl,sizeof(pl));
```

fout前往pl结构的地址，并将开始的36个字节复制到相关联的文件

```c++
ifstream fin("planets.dat",ios_base::in|ios_base::binary);
fin.read((char*)&pl,siozef(pl));
```

通过read()方法读取数据

同样的方法也适用于不使用虚函数的类。在由虚函数的情况下，只有数据成员被保存，方法不被保存

read()来恢复write()写入的数据

对于planet结构体，不可以使用string对象来替代其结构体的name成员。因为string对象本身并不包含字符串，只是包含指向字符串内存单元的指针，将指针复制到文件中，毫无意义。







#### 17.4.6 随机存取

如果文件由长度相同的记录组成，这种方法实现简单

同时使用in模式和out模式，可以同时读写

```c++
fstream finout;
finout.open(file,ios_base::in|ios_base::out|ios_base::binary);
```

fstream类继承了两个办法：seekg()和seekp()，前者将输入指针移动到指定文件位置，后者将输出指针移到指定的文件位置。

```c++
//char类型的模板具体化
istream & seekg(streamoff,ios_base::seekdir);
istream & seekg(streampos);
```

第一个原型定位到离第二个参数指定的文件位置特定距离的位置(单位为字节)

第二个原型定位到离文件开头特定距离的位置(单位为字节)

```c++
fin.seekg(30,ios_base::beg);
fin.seekg(-1,ios_base::cur);
fin.seekg(0,ios_base::end);
```

```c++
fin.seekg(112);
```

例子：

```c++
void main()
{
	fstream finout;
	finout.open("a.txt", ios_base::in | ios_base::out | ios_base::binary);

	int ct = 0;
	if (finout.is_open())
	{
		cout << "Here ar the current contents of the file:\n";
		while (finout.read((char*)&pl,sizeof(pl)))
		{
			cout << ct++ << ":"
				<< pl.name << " "
				<< pl.population << " "
				<< pl.g << endl;
			if (finout.eof())
				finout.clear();
			else
			{
				cerr << "Error!" << endl;
				exit(EXIT_FAILURE);
			}
		}
	}
	else
	{
		cerr << "could not be open";
		exit(EXIT_FAILURE);
	}
}

//定位到你输入的文件位置
int rec;
cin>>rec;
streampos place = res*sizeof(pl);
finout.seekg(place);
//读取当前位置文件
finout.read((char*)&pl,sizeof(pl));
```















### 17.5 内核格式化

读取string对象中的格式化信息或将格式化信息写入string对象中称为内核格式化

头文件sstream定义从ostream类派生出来的哦stringstream类

ostringstream有一个名为str()的成员函数，该函数返回一个被初始化为缓冲区内容的字符串对象

```c++
ostringstream outstr;
outstr<<fixed;
outstr<<"Play only CHF"<<double()<<endl;
string result=outstr.str();
cout << result;
```

构造函数

```c++
istringstream instr(facts);//facts为string对象
string word;
while(instr>>word)
    cout << word <<endl;
```









### 17.6 总结

​	

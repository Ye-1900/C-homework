
# C++第一次作业整理  
### 2.24
不行，无法确定指针是否有效或者符合语法  
### 2.23
因为lp的类型不是int，而void定义了一个空指针，可以接受任意类型的对象。  
### 2.25
a:int型指针，int型变量，引用  
b：int型变量，int型指针，0  
c：int型指针，int型变量  
### 2.35
第一个auto  j  类型为int  

第二个auto  &k 类型为const int &  

第三个auto *p类型为const int *  

第四个auto j2类型为const int  

第五个auto &k2 类型为const int&  
### 3.20
#include<iostream> #include<string> #include<vector>  
using namespace std;  
void main()  
{  
vector My_vector;  
int a[10];  
for (int i = 0;i<10;i++) { cin>>a[i];  
}  
for (int j = 0;j<10;j++)  
{  
My_vector.push_back(a[j]);  
}  
int sum[10];  
for (int k = 0;k<5;k++)  
{  
sum[k] = My_vector[k] + My_vector[9-k];  
cout<<sum[k]<<endl;  
}  
}  
  
### 3.23
#include <iostream>    
#include <string>  
#include <vector>  
using namespace std;  
void main()   
{	  
	vector<int> text(10,5);  
	for (auto it = text.begin(); it != text.end();it++) //注意判断其是否为空  
	{  
		*it = *it * 2;  
		cout<<*it<<endl;  	
	}  
}  
  
### 3.4
#include <iostream>  
#include <string>  
using namespace std;  
void main()  
{  	
	string string1 , string2;  
	cin>>string1>>string2;  
	if (string1.size() != string2.size())  
	{  
		cout<<(string1.size() >= string2.size() ? string1 : string2)<<endl;  
	}  
	else  
	{  
		cout<<"两个字符串长度相等"<<endl;  
	}	  
}   
  
 ### 6.10
include<bits/stdc++.h> using namespace std;  

int exchange(int &v1,int &v2){ int a; a=v1; v1=v2; v2=a; return 0 }  

int main(){ int v1,v2; cin>>v1>>v2; cout<<“v1,v2=”<<endl; exchange(v1,v2) cout<<v1<<v2<<endl; return 0; }  
### 6.19
(a)：函数只有一个参数，传入两个不合法  
(b)：合法  
(c)：合法  
(d)：合法  

### 7.16
对于某个访问说明符能出现多少次没有严格限定，一般来说，作为接口的一部分，构造函数和一部分成员函数应该定义在public说明符之后，而数据成员和作为实现部分的函数则应该跟在private后面。  
定义在public之后的成员在整个程序内可被访问，public成员定义类的接口  
定义在private之后的成员可以被类的成员函数访问，但是不能被使用该类的代码访问。  
### 7.27  
class Screen {  
public: typedef std::string::size_type pos; Screen() = default; Screen( const pos ht, const pos wt ) : height( ht ), width( wt ), contents( ht * wt, ’ ’ ) { } Screen( const pos ht, const pos wt, const char c ) : height( ht ), width( wt ), contents( ht * wt, c ) { } public: Screen& cursor_move( const pos r, const pos c ) { cursor = r * width + c; return *this; } Screen& set_ch( const pos r, const pos c, const char ch ) { contents[ r * width + c ] = ch; return *this; } Screen& set_ch( const char ch ) { contents[ cursor ] = ch; return *this; } Screen& display( void ) { std::cout << contents; return *this; }  

private:  
std::string contents;  
pos cursor = 0;  
pos height = 0;  
pos width = 0;  
}; 
### 7.49  
a：s隐式地调用Sales_data的构造函数，生成一个临时的Sales_data对象，然后传递给combine的形参。  
b:编译无法通过。因为combine成员函数的形参是非常量引用，但是s自动创建的Sales_data临时对象无法传递给combine所需的非常量引用。  
c:编译无法通过。因为我们把combine成员函数声明成了常量成员函数，所以该函数无法修改数据成员的值。  +
### 7.58  
除了静态常量成员之外，其他静态成员不能在类的内部初始化。    
所以rate和vec不能在类内初始化。  
所以rate和vec的类外定义必须给出其初始值。  

# C-p20-2-C-2-
C语言学习笔记 p20 C语言操作符详解(2)
#include<stdio.h>
//下标引用、函数调用、结构成员
int main()
{
    int a[10]={0};
    a[4]=10;//[]下标引用操作符，操作数：一个数组名+一个索引值
    return 0;
}

int get_max(int x,int y)
{
    return x>y?x:y);
}
int main()
{
    int a=10;
    int b=20;
    get_max(a,b);//调用函数的时候的()就是函数调用操作符,操作数接受一个或多个，第一个操作数是函数名，剩余的操作数就传递给函数的参数
    printf("max=%d\n",max);
    return 0;
}

//学生
//创建一个结构体类型-struct Stu
struct Stu
{
    //成员变量
    char name[20];
    int age;
    char id[20];
}
//访问一个结构的成员的操作符一个. 一个->
int main()
{
    int a=10;
    //使用struct Stu整个类型创建了一个学生对象s1，并初始化
    struct Stu s1={"张三",20,"2019010305“};
    printf("%s\n",s1.name);
    printf("%d\n",s1.age);
    printf("%s\n",s1.id);
    //结构体变量.成员名
    return 0;
}

int main()
{
    int a=10;
    //使用struct Stu整个类型创建了一个学生对象s1，并初始化
    struct Stu s1={"张三",20,"2019010305“};
    struct Stu* ps=&s1;
    printf("%s\n",(*ps).name);
    printf("%d\n",(*ps).age);//以上两行代码太啰嗦
    printf("%s\n",ps->name);
    printf("%d\n",ps->age);
    printf("%s\n",ps->id);
    //->的用法：左边是一个结构体指针，右边是一个成员名
    printf("%s\n",s1.id);
    //结构体变量.成员名
    return 0;
}

//表达式的求值
//隐式类型转换
int main()
{
    char a=3;
    char b=127;
    char c=a+b;
    printf("%d\n",c);
    return 0;
}//输出-126

//整形提升
int main()
{
    char a=0xb6;
    short b=0xb600;
    int c=0xb6000000;
    if (a==0xb6)
        printf("a");
    if(b==0xb600)
        printf("b");
    if(c==0xb6000000)
        printf("c");
    return 0;
}//输出只有c，因为char和short都被补成int类型的了
int main()
{
    char c=1;
    printf("%u\n",sizeof(c));
    printf("%u\n",sizeof(+c));
    printf("%u\n",sizeof(!c));
    return 0;
}//输出141，这里的+c也是涉及到整形提升

//算数转换
//如果某个操作符的各个操作数属于不同类型，必须将其中一个操作数转化为另一个操作数的类型，否则无法进行

//操作符的属性
//一共有三个因素
//1.操作符的优先级
//2.操作符的结合性
//3。是否控制求值顺序
int main()
{
    int a=10;
    int b=20;
    int c=b+a*3;
    return 0;
}


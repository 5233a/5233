# 实验 硬件编程–机器指令编程  学号  18342135  姓名  张震扬
## 实验目标
1. 理解冯·诺伊曼计算机的结构
2. 理解机器指令的构成
3. 理解机器指令执行周期
4. 用汇编编写简单程序
## 实验步骤与结果
### 任务1
![](http://imgsrc.baidu.com/forum/pic/item/6fde01025aafa40f0ae0fe88a664034f78f0196a.jpg)
#### 点step after step。观察并回答下面问题：
1. PC，IR 寄存器的作用。
程序计数器，是用来计数的，指示指令在存储器的存放位置，也就是个地址信息。
指令寄存器是用来存放指令的，存放当前正在执行的指令，包括指令的操作码，地址码，地址信息。
2. ACC 寄存器的全称与作用。
累加器A是一个具有特殊用途的二进制8位寄存器，专门用来存放操作数或运算结果。在CPU执行某种运算前，两个操作数中的一个通常应放在累加器A中，运算完成后累加器A
中便可得到运算结果。
3. 用“LOD #3”指令的执行过程，解释Fetch-Execute周期。
读取下条指令：储存3；解码指令；获取数据3；执行指令: 将3存放在寄存器中；程序计数器 +2；
4. 用“ADD W” 指令的执行过程，解释Fetch-Execute周期。
读取下条指令：将W与X相加；解码指令； 从地址W和寄存器中分别获取数据3和1；执行指令：将1和3相加得到4；
5. “LOD #3” 与 “ADD W” 指令的执行在Fetch-Execute周期级别，有什么不同。
LOD #3只需访问RAM一次,而ADD W需要两次访问RAM.
#### 点击“Binary”,观察回答下面问题
1. 写出指令 “LOD #7” 的二进制形式，按指令结构，解释每部分的含义。
00010100 00000111 
第四个数1是寻址模式，表示数值，然后四位是操作码,最后8位为操作数
2. 解释 RAM 的地址。
只用于暂时存放程序和数据，一旦关闭电源或发生断电，其中的程序和数据就会丢失 
3. 该机器CPU是几位的？（按累加器的位数）
8位
4. 写出该程序对应的 C语言表达。
int w = 3;
int x = 1;
int z = w + x;
### 任务2
![](http://imgsrc.baidu.com/forum/pic/item/f57eb62ac65c1038e1adff97bf119313b17e8946.jpg)
#### 输入程序Program 2，运行并回答问题：
无法找到所谓的program2，故第一题无法完成；
#### 修改该程序，用机器语言实现 10+9+8+..1 ，输出结果存放于内存 Y
1. 写出 c 语言的计算过程
##### #include<stdio.h>
##### int main(){
##### int sum = 0;
#####  for(int i = 10;i > 0;++i){
#####    sum += i;
#####  }
##### }
2. 写出机器语言的计算过程
00000000 00010100 00001010 
00000010 00000101 10000001 
00000100 00010001 00000001 
00000110 00000101 10000000 
00001000 00000000 10000001 
00001010 00000101 10000000 
00001100 00000100 10000000 
00001110 00001101 00010010 
00010000 00001100 00000100 
00010010 00000101 10000010 
00010100 00001111 00000000 
00010110 00001110 00000000 
3. 用自己的语言，简单总结高级语言与机器语言的区别与联系
##### 联系:高级语言经编译可变为机械语言,都可以实现顺序，选择和循环
##### 区别：高级语言更接近人类语言,可读性强 ; 机器语言是纯粹的二进制数据,适合于机器的读取
## 实验小结
有实验可以看出，机械语言是非常落后且难以理解的，所以我们应该更加努力地学习高级语言，创造出能造福社会的程序。

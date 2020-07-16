# 中兴

(4条未读通知) offer对比 顺便发一部面经_笔经面经_牛客网: https://www.nowcoder.com/discuss/311651?type=2&order=0&pos=7&page=1&channel=666&source_id=discuss_tag

## 堆和栈区别

## 手撕冒泡排序

```c++
void bubble_sort(int *a,int len){
    int max = len-1;
    int i,j;
    for(i=0;i<max;i++){
        for(j=0;j<max-i;j++){
            //由小到大排序，大的往后移动
            if(a[j]>a[j+1]){
                int t = a[i];
                a[j] = a[j+1];
                a[j+1] = t;
            }
        }
    }
}
```

优化版本

```c++
void bubble_sort(int *a,int len){
    int max = len-1;
    int i,j;
    for(i=0;i<max;i++){
        //每次遍历标志位都要先置为0，才能判断后面的元素是否发生了交换
		int flag = 0;
        
        for(j=0;j<max-i;j++){
            //由小到大排序，大的往后移动
            if(a[j]>a[j+1]){
                int t = a[i];
                a[j] = a[j+1];
                a[j+1] = t;
                flag = 1;
            }
        }
        
        //判断标志位是否为0，如果为0，说明后面的元素已经有序，就直接return
		if (flag == 0)
		{
			return;
		}
    }
}
```



## c和c++区别



[中兴提前批面经_笔经面经_牛客网](
https://www.nowcoder.com/discuss/447132?type=2&order=0&pos=6&page=1&channel=666&source_id=discuss_tag)



[中兴面试经验之谈(结合自己与网上的面经)_zhf的博客-CSDN博客_中兴终面面试经验](https://blog.csdn.net/weixin_43283397/article/details/106405607?ops_request_misc=%257B%2522request%255Fid%2522%253A%2522159428038019724839208620%2522%252C%2522scm%2522%253A%252220140713.130102334..%2522%257D&request_id=159428038019724839208620&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~blog~first_rank_v2~rank_blog_v1-4-106405607.pc_v2_rank_blog_v1&utm_term=%E4%B8%AD%E5%85%B4%E9%9D%A2%E8%AF%95)



[中兴优招软开岗一面、二面_笔经面经_牛客网](https://www.nowcoder.com/discuss/451104?type=post&order=time&pos=&page=0&channel=2000&source_id=search_post)

1. TCP/IP四层协议

   ```
   应用层（FTP E-mail）
   传输层（TCP UDP）
   网络层（IP）
   链路层（以太网协议）
   ```

   

2. 操作系统进程之间通讯

   ```
   管道（pipe）
   信号（signal）
   消息队列
   共享内存
   信号量
   套接字（socket)
   ```

   

3. 使用过Linux吗？说说常用命令

   ```
   cd ls mkdir rm fdisk man
   torch cat wget nohup grep cp mv
   vim watch ps kill
   ```

   

4. 消息队列技术的优点

   ```
   解耦(多个系统)
   异步
   削峰
   ```

   

5. 消息队列放到内存还是磁盘？

   ```
   RabbitMQ是先放内存，后异步刷到磁盘
   Kafka的消息是保存或缓存在磁盘上的
   ```

   

6. 如何保证http请求安全

   ```
   使用HTTPS
   ```

   

# 地平线

(4条未读通知) 秋招攒人品_笔经面经_牛客网
https://www.nowcoder.com/discuss/253529?type=2&order=0&pos=10&page=1&channel=666&source_id=discuss_tag

## c++11的特性，一些关键字的作用、智能指针

## STL容器类中vector、list的相关知识

## 虚函数、虚基类（问了不少相关的）

```
1.虚函数是用于多态中virtual修饰父类函数，确保父类指针调用子类对象时，运行子类函数的。
2.纯虚函数是用来定义接口的，也就是基类中定义一个纯虚函数，基类不用实现，让子类来实现使用了纯虚函数的类不能被实例化。
3.虚基类是用来在多继承中，如果父类继承自同一个父类，就只实例化一个父类

虚函数（多态） 虚基类（多继承）
```



## tcp和udp的区别

## udp如何实现可靠传输与速率控制

## 用两个栈来实现队列，这个牛客的剑指offer有

## 进程和线程，僵尸线程（进程？）

## 程序到可执行文件的过程

## 动态库、静态库的区别

```
静态库
静态函数库的扩展名一般为（.a或.lib），这类库在编译的时候会直接整合到目标程序中，利用静态函数库编译成的文件体积会比较大，代码装载效率高，移植比较方便

动态库
动态函数库的扩展名一般为（.so或.dll），动态函数库在程序运行的时候进行链接，库方便升级
```




(4条未读通知) 互联网挂经合集（本咸鱼已去事业单位，勿念）_笔经面经_牛客网: https://www.nowcoder.com/discuss/322691?type=2&order=0&pos=1&page=4&channel=666&source_id=discuss_tag

**地平线一面（电话面试）** **2019-09-05 10.10-10.40**  

1. 自我介绍

2. const关键字

3. 多态的实现，虚函数实现机制

4. STL了解吗？讲一下

5. vector迭代器的失效问题

   ```
   insert/erase会涉及到迭代器失效的问题
   ```

6. map和unorder_map的区别

   ```markdown
   map： map内部实现了一个红黑树，map内部的所有元素都是有序的，对于那些有顺序要求的问题，用map会更高效一些
   unordered_map: unordered_map内部实现了一个哈希表，因此其查找速度非常的快
   ```

7. 红黑树介绍一下

   ```
   红黑树是非严格平衡二叉搜索树，而AVL是严格平衡二叉搜索树，红黑树具有自动排序的功能
   ```

8. C++11特性

9. 移动拷贝、移动赋值讲讲

10. RPC方式（没打听清，我RPC只了解大体是咋回事，深了真不会）

11. 分布式介绍一下

12. CLOSE_WAIT状态介绍一下（和TIME_WAIT混了，让讲了讲挥手过程）

13. 单链表交点问题

    ```
    1.双指针
    设定两个指针分别指向两个链表头部，一起向前走直到其中一个到达末端，另一个与末端距离则是两链表的 长度差。再通过长链表指针先走的方式消除长度差，最终两链表即可同时走到相交点。
    ```

    

14. 栈实现队列

    ```
    队列是一种 先进先出（first in - first out， FIFO）的数据结构
    栈是一种 后进先出（last in - first out， LIFO）的数据结构
    
    需要使用第二个栈来将第一个栈中的数据逆序，第二个栈顶的数据就能满足队列的先进先出特点
    ```

    

15. 项目介绍

**地平线二面（电话面试）** **2019-09-05 11.05-12.10** 

1. 自我介绍   
2. 实习项目介绍
3. 手撕代码：人脸照片合并（并查集问题，并不会，用了最原始的办法解决了，时间复杂度O(mn2) = =…）
4. 聊在校的那个项目
5. 想做嵌入式方向还是软件开发方向
6. 问我了解地平线吗（我说做机器人的= =，尴尬，人家虽然叫地平线机器人，却并不是做机器人的）

**地平线三面（电话面试）** **2019-09-08 17.00-18.20**  

1. 自我介绍   

2. 一个class有一个指针数据成员，要把它封装成库，要考虑到那些问题。继承情况下呢

3. STL六大组件介绍一下

   ```
   容器(containers)，算法(algorithm)，迭代器(iterator)，
   仿函数(functors)，适配器(adapters)，配置器(allocators)
   ```

   

4. Linux用过哪些框架

5. TCP的拥塞控制，两种方式分别应用的场景

6. 两个数组，存的是长整型，现在交换数组元素，是一个数组的所有元素都大于另一个数组的元素，并且保证两个数组的原始长度不变，怎么设计，算法复杂度多少

7. 如果两个数组分布在两台机器上（分布式），应该如何操作

8. 分布式相关问题，缓存设计，分布式缓存一致性问题（讲了raft，总监提出了很多问题，最后觉得我没怎么理解，于是跳过了）

9. 想去什么样的公司，实习在哪里，以后工作想去哪

10. 反问1：总监是负责哪块的

11. 反问2：怎么看待AI的前景

# 字节跳动

(4条未读通知) 菜鸡本菜的字节客户端一面二面_笔经面经_牛客网: https://www.nowcoder.com/discuss/446035?type=2&channel=666&source_id=discuss_terminal_discuss_hot


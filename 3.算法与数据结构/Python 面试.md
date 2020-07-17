# 面试1

[中兴软件开发面试](https://blog.csdn.net/jerryz2017/article/details/100603157?ops_request_misc=%7B%22request%5Fid%22%3A%22159430027919724835802133%22%2C%22scm%22%3A%2220140713.130102334.pc%5Fall.%22%7D&request_id=159430027919724835802133&biz_id=0&utm_medium=distribute.pc_search_result.none-task-blog-2~all~first_rank_ecpm_v3~rank_ctr_v3-2-100603157.ecpm_v1_rank_ctr_v3&utm_term=中兴+软件开发)

## python常用库有哪些？

- os：提供不少于操作系统相关联的函数
- sys：通常用于命令行参数
- datetime：日期时间
- re：正则匹配
- math：数学运算

## 常用排序算法有哪些？

1. **冒泡排序（Bubble Sort）**
2. 选择排序（Selection Sort）
3. 插入排序（Insertion Sort）
4. 希尔排序（Shell Sort）
5. **归并排序（Merge Sort）**
6. **快速排序（Quick Sort）**
7. 堆排序（Heap Sort）
8. 计数排序（Counting Sort）
9. 桶排序（Bucket Sort）
10. 基数排序（Radix Sort）

## 上面的排序算法中那种最快，复杂度是多少？

最快 快速排序 O(nlogn)

冒泡排序 O(n^2)

## 类方法中__init__与__new__的区别?

new作用于init之前。前者可以决定是否调用后者，可以决定调用哪个类的init方法。

## 熟悉哪些数据结构？

列表 字典 集合 链表 队列 二叉树 堆栈

## 链表适用于哪些场合？

频繁做插入删除操作，数据大小没有固定

## 可变数据类型和不可变数据类型？

- 可变类型：会在原来的内存地址上修改元素 比如： **列表，字典**
- 不可变类型：不会在原来的内存地址上修改元素，而是指向了新的内存引用 比如：**整型，**
  **字符串，元组**

## 强制改变不可变数据类型会怎样？

Python会抛出TypeError异常



# 面试2

[中兴软件开发提前批面经_笔经面经_牛客网](https://www.nowcoder.com/discuss/450141?type=post&order=rank&pos=&page=1&channel=2000&source_id=search_post)

## Python读取Excel文件的方式

* xlrd
* panda

## 判断是否为空的表达方式

* if x is None

* if not x      

  not True为False，not False为True

  None、空列表[]、空字典{}、空元组()、0等一系列代表空和无的对象会被转换成False

* **if x is not None**      if not x is None

## 判断两个字符串是否相等

用"==" 符号比较两个字符串

‘==’ 是用来判断两个对象的值是否相等的

 is 用来判断是否是同一个对象，也就是说is是来判断两个变量的地址引用是否相同

## Python中列表，元组，字典，集合的区别

列表List，可重复，类型可不同

元组Tuple，元组是只读的，不能修改

字典dict，定义了键和值之间一对一的关系

集合set，一个无序不重复元素集

## sizeof与strlen的区别

strlen测量的是字符的实际长度，以'\0' 结束。而sizeof 测量的是字符的分配大小。

strlen是函数，结果要在运行的时候才能计算出来

sizeof 是运算符，其值在编译时即计算好了

# 面试3

[中兴优招一二面_笔经面经_牛客网](https://www.nowcoder.com/discuss/451227?type=post&order=create&pos=&page=1&channel=2000&source_id=search_post)

# 面试4

[中兴ZTE2020.7.15优招一面记录_笔经面经_牛客网](https://www.nowcoder.com/discuss/452446?type=post&order=create&pos=&page=1&channel=2000&source_id=search_post)

## LINUX系统下怎么设置文件权限

数字 4 、2 和 1，表示读、写、执行权限，即 r=4，w=2，x=1

rwx = 4 + 2 + 1 = 7

rw = 4 + 2 = 6

rx = 4 +1 = 5

拥有者 、群组 、其它组( u、 g 、o)，分别代表User、Group、及Other的权限

- 设置所有人可以读写及执行

  chmod 777 file  (等价于  chmod u=rwx,g=rwx,o=rwx file 或  chmod a=rwx file)

- 设置拥有者可读写，其他人不可读写执行

  chmod 600 file (等价于  chmod u=rw,g=---,o=--- file）

# 面试5

[中兴优招 base南京_笔经面经_牛客网](https://www.nowcoder.com/discuss/454029?channel=2000&source_id=home_feed)

## 判断短的字符串在长的字符串中出现的次数

* KMP算法 Knuth-Morris-Pratt 字符串查找算法
* 双指针
* 滑动窗口

```python
a = "abababc"
b = "ab"
# 方法 1
count_a = a.count(b)
print(count_a)

# 方法 2 
# 双指针
i = 0
j = 0
count_b = 0
while i<len(a):
    if a[i]==b[j]:
        i+=1
        j+=1
    else:
        i+=1
        j=0
    if j == len(b):
        count_b += 1
        j = 0

print(count_b)

        
# 方法 3
# 固定滑动窗口
j = len(b)
count_c = 0
for i in range(len(a)):
    if a[i:i+j] == b:
        count_c += 1
print(count_c)
```

```C++
int main() {
    char a[]="abababc";
    char b[]="ab";
    
    int i=0;
    int j=0;
    int count=0;
    while(a[i]!='\0'){
        if(a[i]==b[j]){
            i++;
            j++;
        }else{
            i++;
            j=0;
        }
        if(b[j]=='\0'){
            count++;
            j=0;
        }
    }
    
    std::cout << count;
}
```


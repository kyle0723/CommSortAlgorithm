# 冒泡排序
**冒泡排序**（Bubble Sort）也是一种简单直观的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢"浮"到数列的顶端。
## 原理
每次比较相邻的两个元素，将最大或者最小的元素交换到最右端，如图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/2019102612143187.gif)
## 代码实现
**Java实现：**
1.未优化版，count用来统计比较次数，每交换完一次，count+1。

```java
public static void bubbleSort(int sorArray[]){
        //count用来计数
        int count = 0;
        //第一次比较(外层循环控制冒泡趟数，趟数为数组长度-1)
        for(int i = 0; i < sorArray.length-1; i++){
            //第二次比较（内层循环两两比较，每次选出最大的数放到最后）
            for(int j = 0; j < sorArray.length-1-i; j++){
                if(sorArray[j] > sorArray[j+1]){
                    int temp = sorArray[j];
                    sorArray[j] = sorArray[j+1];
                    sorArray[j+1] = temp;
                }
                count++;
            }
        }
        System.out.println(Arrays.toString(sorArray));
        System.out.println("比较次数为= " + count);
    }
```
2.优化版，添加一个boolean变量，如果内存循环两两比较没有发生交换，说明排序完成，跳出循环。

```java
/*
    * 当排序过程中已将数组元素排序完成，但此时他仍然回去比较，做了无用功，通过加一个boolean变量来优化。
    **/
    //优化后
    /*
    * @auther delet
    * @Description 
    * @Date 14:56 2019/8/21
    * @Param [sorArray]
    * @return void
    **/
    public static void bubSort(int sorArray[]){
        //count用来计数
        int count = 0;
        //第一次比较(外层循环控制冒泡趟数，趟数为数组长度-1)
        for(int i = 0; i < sorArray.length-1; i++){
            boolean flag = true;
            //第二次比较（内层循环两两比较，每次选出最大的数放到最后）
            for(int j = 0; j < sorArray.length-1-i; j++){
                    if(sorArray[j] > sorArray[j+1]){
                    int temp = sorArray[j];
                    sorArray[j] = sorArray[j+1];
                    sorArray[j+1] = temp;
                    flag=false;
                }
                count++;
            }
            if(flag){
                break;
            }
        }
        System.out.println(Arrays.toString(sorArray));
        System.out.println("优化后比较次数为= " + count);
    }
```
## 总结：
1.内层循环中j的范围为数组长度-1-i，这里是因为每i次冒泡会选出i个最大的元素放到最后的位置，只需要比较前面的大小。
2.添加boolean变量可以省去最后一趟排好序的次数，减少了循环次数。
# 插入排序
**插入排序**（Insertion Sort）顾名思义就是讲未排序的元素插入到已排序的队列中以构成新的有序队列。插入排序是一种最简单直观的排序算法，它的工作原理是通过构建有序序列，对于未排序数据，在已排序序列中从后向前扫描，找到相应位置并插入。
## 原理
每次都将当前元素插入到左侧已经排序的数组中，使得插入之后左侧数组依然有序，如图：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191108114650196.gif)
## 代码实现
**Java实现：**

```java
public static void insSort(int arr[]){
        // 从下标为1的元素开始选择合适的位置插入，因为下标为0的只有一个元素，默认是有序的
        for(int i = 1; i < arr.length; i++){
            // 记录要插入的数据
            int temp = arr[i];
            int indx = 0;
            // 从已经排序的序列最右边的开始比较，找到比其小的数
            for(int j = i; j > 0; j--){
                if(arr[j] < arr[j-1]){
                    arr[j] = arr[j-1];
                    indx = j-1;
                }else{
                    break;
                }
                arr[indx] = temp;
            }
//            //定义要插入的元素
//            int insertValue = arr[i];
//            //找到要插入的元素的前一个下标
//            int insertIndex = i - 1;
//            while(insertIndex >= 0 && insertValue < arr[insertIndex]){
//                arr[insertIndex + 1] = arr[insertIndex];
//                insertIndex--;
//            }
//            arr[insertIndex + 1] = insertValue;
        }
        System.out.println(Arrays.toString(arr));
    }
```
## 总结：
![在这里插入图片描述](https://img-blog.csdnimg.cn/20191108115523404.png)![在这里插入图片描述](https://img-blog.csdnimg.cn/2019110811550657.png)
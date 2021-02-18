# 选择排序

**选择排序(Selection-sort)** 是一种简单直观的排序算法。它的工作原理：首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置，然后，再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。以此类推，直到所有元素均排序完毕。 

## 原理：

首先在未排序序列中找到最小（大）元素，存放到排序序列的起始位置。

再从剩余未排序元素中继续寻找最小（大）元素，然后放到已排序序列的末尾。

重复第二步，直到所有元素均排序完毕。

![selectionSort](C:\Users\Kyle\Desktop\selectionSort.gif)

## 代码：

```java
public static int[] selectionSort(int[] array) {
    if (array.length == 0) {
        return array;
    }
    // 总共要经过 N-1 轮比较
    for (int i = 0; i < array.length - 1; i++) {
        int min = i;
        // 每轮需要比较的次数 N-i
        for (int j = i; j < array.length; j++) {
            if (array[j] < array[min]) {
                // 记录目前能找到的最小值元素的下标
                min = j;
            }
        }
        if (min != i) {
            int tmp = array[i];
            array[i] = array[min];
            array[min] = tmp;
        }
    }
    return array;
}
```

## 总结：

![1613631816449](C:\Users\Kyle\AppData\Local\Temp\1613631816449.png)![1613631842281](C:\Users\Kyle\AppData\Local\Temp\1613631842281.png)
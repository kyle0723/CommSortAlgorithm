# ��������
**��������**��Insertion Sort������˼����ǽ�δ�����Ԫ�ز��뵽������Ķ������Թ����µ�������С�����������һ�����ֱ�۵������㷨�����Ĺ���ԭ����ͨ�������������У�����δ�������ݣ��������������дӺ���ǰɨ�裬�ҵ���Ӧλ�ò����롣
## ԭ��
ÿ�ζ�����ǰԪ�ز��뵽����Ѿ�����������У�ʹ�ò���֮�����������Ȼ������ͼ��
![���������ͼƬ����](https://img-blog.csdnimg.cn/20191108114650196.gif)
## ����ʵ��
**Javaʵ�֣�**

```java
public static void insSort(int arr[]){
        // ���±�Ϊ1��Ԫ�ؿ�ʼѡ����ʵ�λ�ò��룬��Ϊ�±�Ϊ0��ֻ��һ��Ԫ�أ�Ĭ���������
        for(int i = 1; i < arr.length; i++){
            // ��¼Ҫ���������
            int temp = arr[i];
            int indx = 0;
            // ���Ѿ�������������ұߵĿ�ʼ�Ƚϣ��ҵ�����С����
            for(int j = i; j > 0; j--){
                if(arr[j] < arr[j-1]){
                    arr[j] = arr[j-1];
                    indx = j-1;
                }else{
                    break;
                }
                arr[indx] = temp;
            }
//            //����Ҫ�����Ԫ��
//            int insertValue = arr[i];
//            //�ҵ�Ҫ�����Ԫ�ص�ǰһ���±�
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
## �ܽ᣺
![���������ͼƬ����](https://img-blog.csdnimg.cn/20191108115523404.png)![���������ͼƬ����](https://img-blog.csdnimg.cn/2019110811550657.png)
# 方法

## 1.何谓方法









## 2.方法的定义及调用

![20220511123646](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511123646.png)











## 3.方法重载



![20220511125900](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511125900.png)







## 4.命令行传参









## 5. 可变参数



![20220511130311](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511130311.png)







## 6.递归



![20220511130738](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511130738.png)



![20220511130759](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511130759.png)



# 数组

## 1.数组概述

![20220511131024](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511131024.png)





## 2. 数组声明创建



![20220511131802](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511131802.png)

```java
int[] a=new int [10] //声明了一个长度为10的整型数组
```



![20220511132208](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511132208.png)



![20220511132644](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511132644.png)



![20220511132725](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511132725.png)



![20220511132818](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511132818.png)



![20220511132856](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511132856.png)







## 3.数组使用

![20220511134036](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511134036.png)





![20220511134237](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511134237.png)



## 4. 多维数组

![20220511134440](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511134440.png)

1. 二维数组











## 5. Arrays 类

![20220511135702](C:\Users\黎明\Documents\Tencent Files\1563826569\Image\SharePic\20220511135702.png)



冒泡排序：

```java
int[] array={1,3,45,,45,6,1,3,4,5}
//冒泡排序
for(int i=0;i<array.lenth-1;i++){//表示比较的次数
    for(int j=0;j<array.lenth-i;j++){//从前往后依次比较
        if(array[j+1]>array[j]){//比较前后大小
            int temp=0;   //作为交换的中间值
            temp=array[j];
            array[j]=array[j+1];
            array[j+1]=temp;
        }
    
```







## 6，稀疏数组







1. 目的

稀疏数组：缩小数组的规模，只记录有效值，想用的时候可以随时进行还原











2. 应用
   1.把一个二维数组变为稀疏数组

```java
 int[][] array1=new int[5][6]; //原数组 有的空间中没有赋值，出现空间的浪费

        array1[2][4]=2;
        array1[3][4]=6;
        array1[4][2]=7;
        for(int[] ints:array1){//运用增强for循环输出原数组
            for(int anInt:ints){
                System.out.print(anInt+"\t");
            }
            System.out.println();
        }

        int sum=0;//用来记录有效值的个数

//        对原数组进行遍历计算有效值的个数
        for (int[] ints : array1) {
            for (int anInt : ints) {
                if (anInt!=0) {
                    sum++;
                }
            }
        }
//        记录有效值的个数
        int[][] array2=new int[sum+1][3];// 定义一个稀疏数组
        //        计算原数组的总行号
        array2[0][0]=array1.length;
//        记录原数组的总列号
        array2[0][1]=array1[0].length;
        array2[0][2]=sum;
        int count=1;//记录稀疏数组的行号 ，从第二行开始
       for (int i=0;i<array1.length;i++){
           for (int j=0;j<array1[i].length;j++){
               if (array1[i][j]!=0){
                   array2[count][0]=i; //记录有效值的行号
                   array2[count][1]=j;//记录有效值的列号
                   array2[count][2]=array1[i][j];//记录有效值
                   count++;//下一次再记录时要进行换行了
               }
           }
       }
//       循环遍历稀疏数组
        for (int[] ints : array2) {
            for (int anInt : ints) {
                System.out.print(anInt+"\t");
            }
            System.out.println();
        }

```



2. 步骤
   1. 先对计算原数组有效值的个数
   2. 根据有效值的个数写出稀疏数组的行数 列数是固定的为三列 
      1. 第一行 不记录有效值
   3. 定义一个变量记录稀疏数组的行号
   4. 然后遍历原数组把相应的数组记录在稀疏数组中









2. 把稀疏数组还原

```java
//        把稀疏数组转换为原数组
        int[][] array3=new int[array2[0][0]][array2[0][1]];
//        从有有效值的一行开始即从第二行开始
        for (int i=1;i<array2.length;i++){

            array3[array2[i][0]][array2[i][1]]=array2[i][2];

        }
        for (int[] ints : array3) {
            for (int anInt : ints) {
                System.out.print(anInt+"\t");
            }
            System.out.println();

        }
```



步骤：

1. 根据稀疏数组的第一行数据写出原数组的行号和列号
2. 遍历稀疏数组对将相应的值写入原数组 
   1. 注意是从稀疏数组的第二行开始遍历
   2. 第一行只是记录的个数没有记录有效值

# 注意：

1. 最好自己谢谢总结，变成自己的理解，一定要多思考
2. 截图的时候在图上写出自己的思考
3. 别耗时间，加快速度学
4. 遇到不会的记录下来



# 遇到的困难，问题

1. 运用增强for循坏时注意前面是后面数组里的元素
2. 转义字符在双引号里面  "\t"
3. 进行转换为原数组的时候注意从第二行开始遍历


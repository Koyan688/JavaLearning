## Array's Basic

### Array's Feature

>1. 长度确定，数组一旦被创建，它的大小就是不可变的；
>2. 其元素必须是相同类型，不允许出现混合类型；
>3. 数组类型可以是任何数据类型，包括基本数据类型和引用类型。

### Array's Initialize

>1. static-initialize;
>2. dynamic-initialize;
>3. default-initialize.     //int-->0; String-->null; boolean-->false;

### for-each

用于读取数组或集合中的所有元素，即遍历:    
        
    String[] s = {"aa","bb","cc"}
    for(String m:s){
        System.out.println(m);
    }


## ArrayCopy

用arraycopy方法实现增删字符串数组元素：

    public class TestArrayCopy {
        public static void main(String[] args) {
            //删除指定位置元素
            String[] s1 = {"10","20","3","0","0"};
            for(int i = 2; i > 0; i--){
                s1 = removeElment(2,s1);
            }
            s1 = extendRange(s1,10);
            System.out.println(Arrays.toString(s1));//---------------------Arrays.toString方法-----------------
            //插入数组
            String[] s2 = {"a","b","c","d","e","f","i","j"};
            String[] s3 = {"g","h"};
            String[] s4 = insertElment(s2,s3,6);
            System.out.println(Arrays.toString(s4));
        }
        //删除指定索引位置元素，并返回数组
        public static String[] removeElment(int index,String[] s){
            System.arraycopy(s,index+1,s,index,s.length-index-1);
            s[s.length-1] = null;
            for(int i = 0; i < s.length; i++){
                System.out.println(i+"---"+s[i]);
            }
            return s;
        }
        //数组扩容
        public static String[] extendRange(String[] s1,int n){
            String[] extend = new String[s1.length+n];//扩容n个元素
            System.arraycopy(s1,0,extend,0,s1.length);
            return extend;
        }
        //插入数组(index前一位插入)
        public static String[] insertElment(String[] s1,String[] insert,int index){
            String[] extend = extendRange(s1,2);
            System.arraycopy(insert,0,extend,index,insert.length);
            System.arraycopy(s1,index,extend,index+insert.length,s1.length-index);
            return extend;
        }
    }


## three-usual-method of Arrays

    `int a[]={100,30,26,50,70,200}`

>1. toString:`System.out.println(Arrays.toString(a));//描述数组内容`
>2. sort:`Arrays.sort(a);//排序`
>3. binarySearch:`System.out.println(Arrays.binarySearch(a,50));//查找元素位置,成功返回索引，失败返回-1`


## 2Dimension Array

>1. dynamic-initialize:
    int[][] a = new int[3][];
    a[0] = new int[]{10,20};
    a[1] = new int[]{20,30,50};
    a[2] = new int[]{30,60};

>2. static-initialize:
    int[][] b ={
        {10,20,30},
        {2,4},
        {30,50,60},
    };


## Table Saved in Array

    Object[] emp1 = {1001,"ZhangSan",18};//基本数据类型1001，本质不是Object对象，编译器自动将其"封装"成包装类对象；
    Object[] emp1 = {1002,"LiSi",19};
    Object[] emp1 = {1003,"WangWu",20};
    Object[][] tableData = new Object[3][];
    tableData[1] = emp1;
    tableData[2] = emp2;
    tableData[3] = emp3;
    for(Object[] temp:tableData){
        System.out.println(Arrays.toString(temp));
    }

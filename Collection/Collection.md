# Generic 泛型

**泛型就是数据类型的参数化，用于建立安全的集合。**

1. 声明：`class MyClass<E> {}`*^^E为形参*
2. 调用：`MyClass<String> mc = new MyClass<>();`	*^^String为实参，也可为其他基本数据类型的包装类<Integer>、<Character>……*

***

# Common Methods of Collection 容器接口的常用方法

## 容器内操作

`Collection<String> c = new ArrayList<>();`	*^^ArrayList继承List继承Collection*

1. size()
2. isEmpty()
3. add(E)
4. contains(E)
5. toArray()
6. remove(E)
7. clear()

```java
System.out.println(c.size());	//Returns the number of elements in this collection.
System.out.println(c.isEmpty());	//Returns the number of elements in this collection.
c.add("Yang");	c.add("Tang"); c.add("None");
System.out.println(c.contains("Yang"));	//Returns true if this collection contains the specified element. 
Object[] obj = c.toArray();	//This method acts as a bridge between array-based and collection-based APIs. 
c.remove("None");
c.clear();		//Removes all of the elements from this collection (optional operation).
```

## 容器互操作

`Collection<String> c1 = new ArrayList<>();`

1. addAll()	
2. containsAll(Collection<? extends E>)	
3. removeAll(Collection<? extends E>)
4. retainAll(Collection<? extends E>)

```java
c1.addAll(c);	//Adds all of the elements in the specified collection to this collection(optional operation).`
c1.containsAll(c);	//Returns true if this collection contains all of the elements in the specified collection.
c1.removeAll(c);	//Removes all of this collection's elements that are also contained in thespecified collection (optional operation). 
c1.retainAll(c);	//Retains only the elements in this collection that are contained in thespecified collection (optional operation). 
```

***

# List接口

## List's Feature	基本特征

1. 有序：List中的每个元素都有索引；
2. 可重复：List中的元素允许相同，即允许满足e1.equals(e2)的元素重复加入容器；
	
**List接口继承于Collection接口，其常用的实现类为：ArrayList、LinkedList、Vector；**

## Common Method of List  	List接口的常用方法

1. add(int,E)	*^^int index, E element* *^^指定位置插入*
2. remove(int)	*^^int index*
3. set(int,E)	*^^int index, E element* *^^指定位置覆盖*
4. get(int)		*^^int index* *return E*
5. indexOf(Object)	*^^Object为基本数据类型或对象* *^^return the index of the first occurrence of the specified element or -1 if there is no such index.* 
6. lastIndexOf(Object)
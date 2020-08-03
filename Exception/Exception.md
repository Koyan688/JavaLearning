## Exception

### try-catch捕获异常
	try{
		sentence1;
		sentence2;
	}catch(Exception1 e){
		sentence3;
	}catch(Exception2 e){
		sentence4;
	}finally{
		sentence5;
	}

### throws Exception抛出异常
方法声明中抛出异常:`method(parameters) throws Exception1,Exception2{}`

### 自定义异常类
>1. 继承Exception类，需对其进行处理（捕获或抛出）；
>2. 继承RunTimeException类，不用进行处理，需在方法体中手动抛出异常:`throw new definedException("print-tips");`
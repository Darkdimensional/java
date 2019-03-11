 基本数据类型对象包装类。
 为了方便操作基本数据类型值，将其封装成了对象，在对象中定义了属性和行为丰富了该数据的操作。
 用于描述该对象的类就称为基本数据类型对象包装类。
 
 byte		Byte
 short		Short
 int		Integer
 long		Long
 float		Float
 double		Double
 char		Character
 boolean	Boolean	
 
 该包装对象主要用于基本类型与字符串之间的转换
 
 基本类型---->字符串
 	1:基本类型数值+""
 	2:用String类中的静态方法valueOf(基本类型)；
 	3:用Integer的静态方法valueO(基本类型);
 字符串---->基本类型
 	1:使用包装类中的静态方法  Xxx parserXxx ("Xxx类型的字符串")
 	 	int parseInt("intString");
 	 	只有Character没有parser方法。
 	2:如果字符串被Integer进行对象的封装。
 		可使用另一个非静态的方法，intValue();
 		将一个Integer对象转成基本数据类型int。
 		
 整数：
 十进制---->其他进制：
 Integer.toBinaryString(i); //二进制
 Integer.toOctalString(i);  //八进制
 Integer.toHexString(i);  //十六进制
 Integer.toString(值,进制);
 其他进制---->十进制：
 Integer.parseInt("值",进制);
 
 jdk1.5以后，自动装箱，如果装箱的是一个字节（>=127），那么数据将会共享。
 Integer i = 6; //自动装箱，简化书写。
 i = i + 6; i = new Integer(i.intValue()+6);自动拆箱

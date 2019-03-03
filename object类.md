object:所有类的跟类
Object是不断抽取而来，具备这所有对象都具备的共性内容。
常用的共性功能：
public boolean equals (Object obj)
初始：判断两个对象是否相同（地址）。
一般都会覆盖此方法，根据对象的特有内容，建立判断对象是否相同的依据。
public int hashCode()
相同对象必须具有相等哈希码，所有一般重写equals时都要重写哈希。
public find Class<?> getClass()
获取对象的字节码对象。
public String toSting()
转换成简明易懂的信息表达式。建议子类重写
。。。
publice void notify()
publice void wait()

package kecheng;

import javax.management.RuntimeErrorException;

class Person extends Object
{
	private int age;
	public Person(int age) {
		this.age = age;
	}
	//比较Person的年龄，是否是同龄人
	public boolean compare (Person p)
	{
		return this.age == p.age;
	}
	//一般都会覆盖此方法，根据对象的特有内容，建立判断对象是否相同的依据。
	public boolean equals(Object obj) //Object obj == p2;
	{
		if (!(obj instanceof Person))
		{
			throw new RuntimeException("类型错误");
			//throw new ClassCastException("类型错误");
		}
		Person p = (Person)obj;
		return this.age == p.age;
	}
	//重写哈希值
	public int hashCode() {
		return age;
	}
	//toString
	public String toString() {
		return "...";
	}
}
class Demo
{
}

public class ObjectDemo {
	public static void main(String[] args) {
		Person p1 = new Person(20);
		Person p2 = new Person(20);
		//Person p3 = p1;
		//都是比较地址，是否为同一个对象
		//System.out.println(p1.equals(p2));
		//System.out.println(p1 == p2);
		Demo d = new Demo();
		System.err.println(p1.equals(d));
		
		
		System.err.println(p1);
		System.err.println(Integer.toHexString(p1.hashCode()));
		
		
		Class clazz1 = p1.getClass();
		Class clazz2 = p2.getClass();
		System.out.println(clazz1 == clazz2);
		
	}
}



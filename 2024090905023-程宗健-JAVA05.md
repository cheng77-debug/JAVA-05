1. 
 ```java
 class Person {  
    private String name;  
    private int age;  
    private int sex;  
  
    public Person() {  
    }  
    public Person(Person person) {  
        this.age=person.age;  
        this.sex=person.sex;  
        this.name=person.name;  
    }  
  
    private void eat() {  
        System.out.println(name+"正在吃东西");    
    }  
  
    private void sleep() {  
  
    }  
  
    private void dadoudou() {  
  
    }  
}
```
this就代表了你用的引用。
譬如：Person c1=new Person();
	   Person c2=new Person();
此时，若我用c1.引用的方式调用对象，那么那个this就是c1
若我用c2.引用的方式调用对象，那么那个this就是c2
实例变量的使用必须为引用.实例变量的形式，有时在实例方法中直接用了实例变量，那其实是把this.省略了。

---


2. 
```java 
public class java05 {  
    public static void main(String[] args) {  
      Person c1=new Person();  
      Person c2=new Person();  
      Person c3=new Person(c2);  
      c1.setAge(19);  
      c1.setName("YuRen");  
      c1.setSex(1);  
        
        System.out.println(c1.getAge());  
        System.out.println(c1.getName());  
        System.out.println(c1.getSex());
        System.out.println(Person.count());  
    }  
}  
class Person {  
    private String name;  
    private int age;  
    private int sex;  
  
    static int i=0;  
  
    public Person() {  
        i++;  
    }  
    public Person(Person person) {  
        this.age=person.age;  
        this.sex=person.sex;  
        this.name=person.name;  
        i++;  
    }  
  
    public String getName() {  
        return name;  
    }  
  
    public void setName(String name) {  
        this.name = name;  
    }  
  
    public int getAge() {  
        return age;  
    }  
  
    public void setAge(int age) {  
        if(age<0 || age>150){  
            System.out.println("这河里吗？");  
            return;  
        }  
        this.age = age;  
    }  
  
    public int getSex() {  
        return sex;  
    }  
  
    public void setSex(int sex) {  
        if (sex==1 || sex==0){  
        this.sex = sex;  
        }  
        else{System.out.println("1代表男性，0代表女性");  
        }  
    }  
  
    private void eat() {  
        System.out.println(name+"正在吃东西");  
    }  
  
    private void sleep() {  
  
    }  
  
    private void dadoudou() {  
  
    } 
    public static int count() {  
        return i;  
    }  
}
```

对象是具体的而类是抽象的。
可以说，类是对象的抽象概括。
比如说，每一个成电人都是一个具体的对象，而其相应共同的属性和行为就可以概括为一个类。
比如，程某人，19岁，178cm......综合起来就是我这个对象
	   姓名    ，年龄，身高........  这些就是个类    

---
3. 
public(公共的):慷慨且大方，哪里都可以访问。
default(默认的):只要还在本包内就行，本包的其他类也可以访问，出了包就不行了。
protected（保护起来的）:与default基本一致，但是出了包的子类仍然可以访问。
private(私有的): 只能在此类中访问。

---
4. 

```java
public class java05 {  
    public static void main(String[] args) {  
      Person c1=new Person();  
      Person c2=new Person();  
      Person c3=new Person(c2);   
        
        System.out.println(Person.count());  
    }  
}  
class Person {  
    private String name;  
    private int age;  
    private int sex;  
  
    static int i=0;  
  
    public Person() {  
        i++;  
    }  
    public Person(Person person) {  
        this.age=person.age;  
        this.sex=person.sex;  
        this.name=person.name;  
        i++;  
    }  
  
    public static int count() {  
        return i;  
    }  
}
```
在此例中，因为new了三次，创建了3个对象所以会输出3。（*与本题无关的删去了，为了好看*）
（但是，如果我c1=null后c1所指向的对象会被销毁，我不知道该怎么去统计销毁的对象的个数😭）

#### Перегрузка методов выполняет несколько функций:
1. Вы можете создать несколько конструкторов - с одним, двумя параметрами, и вообще без параметров. Программа будет выбирать тот,
который подходит под заданные параметры. Например:
```java
class Test {
    public static void main (String args[]){
           Cat cat1 = new Cat();
           Cat cat2 = new Cat("Murka");
           Cat cat3 = new Cat("Marka", white);
    }
}
```
Предположим, мы еще не знаете имя первого кота и его породу. А для второго - только имя. В такой ситуации, несколько 
конструкторов дают возможность сделать все аккуратно.
2. В первом примере мы говорили о конструкторах. Но то же самое применимо и к обычным методам. Одним из главных плюсов является то, что Вам не нужно запоминать названия кучи методов, выполняющих похожую функцию.  Представим, что мы хотим создать метод "add", общий для всех типов. У нас есть int, double и String:
```java
class Test {
    public static void main (String args[]) {
           int a = 100;
           double b = 1.1;
           String d = "vertex";
    }
}
```
Теперь, мы хотим создать общий для всех метод "add". Он будет выглядеть так:
```java
class Test {
    public static void main (String args[]){
           int a = 100;
           double b = 1.1;
           String c = "vertex";
    }
    public static int add (int a, int b){
           return a+= b;
    }
    public static double add (double a, double b){
           return a+= b;
    }
    public static String add (String a, String b){
           return a.concat(b);
    }
}
```
Применим наш метод и выведем результат на экран:
```java
class Test {
    public static void main (String args[]){
           int a = 100;
           double b = 1.1;
           String c = "vertex";

           System.out.println(add(a,a));
           System.out.println(add(b,b));
           System.out.println(add(c,c));
    }
    public static int add (int a, int b){
           return a+= b;
    }
    public static double add (double a, double b){
           return a+= b;
    }
    public static String add (String a, String b){
           return a.concat(b);
    }
}
```
Должно получиться следующее:
```
    200
    2.2
    vertexvertex
```
Благодаря перегрузке методов мы можем запомнить один метод - add - и с помощью него выполнить 3 операции. Будь это другой язык
программирования, который не поддерживает перегрузку, необходимо было бы создать (и запомнить) методы addInt, addDouble и, 
например, addStr. И так с каждой операцией!

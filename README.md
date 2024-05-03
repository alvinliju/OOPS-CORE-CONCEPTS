# OOPS-CORE-CONCEPTS

OOPS (Do or Die)

OOPS vs procedural oriented programming

Procedural programming is about writing procedures and methods that perform operations on data but OOPs on the other hands is about creating objects that contain both data and methods together.

OOPs is faster
OOPs is more efficient 
Follows DRY Principle(Do not repeat yourself ) 
Makes the code maintenance easy

Classes and Objects

-Classes are basically templates or blueprint for objects 
-Can be considered as set of rules its object should follow
-To create a Class in Java:
Public class ExampleClass (){
     Int num;
}
-We can access the attributes in the class with (.) operator and modify it or override it(if it is initialised earlier)
ObjName.attributeName
//modifying class attribute from attribute
ObjName.attributeName=4;
-We use Final keyword if we dont want anyone to override our attributes in a class 
Public class ExampleClass (){
     final int num;
}

-Objects are the instances/derivatives of Class in which they inherit the methods variables from class
-In order to access methods or variables in a class we need to create an object of the class
-we use new keyword to create an object(new keyword does nothing but allocates memory during the runtime of the program)
-we dont use ‘new’ keyword to do this:
int a=10;
—>Because primitives are not objects they are stored in stack memory
-They form a new memory location to store the new objects 
-We can create multiple objects of same class
-Objects created from same class have no relation to each other(different memory)

ClassName ObjectName=new ClassConstructor();
Main objName=new Main();
-Above we are creating(Main obj) a variable type of Main(user defined data type) which happens during the runtime 
-and the code in the right part(new Main();) is where the magic happens
—> thats where the object is created of class(Main) and allocates memory dynamically during the run time(using new keyword)
—>the objName here is a reference variable of type Main

Methods in Java

-Methods are nothing but a fancy of saying function in OOPS
-Methods are declared within a class
-If the method is in the same class we can call the method like this:
MethodName();

Static Keyword

-it is a special keyword used in OOPs
-Only a static method can access another static method
-you can declare both methods and variables as static
-Static method in a class does not depend on objects unlike other methods which requires an object to be accessed
-Static Methods are stored In stack memory but objects are stored in Heap memory
-you cannot access a non static stuff inside static stuff without referencing their instances in a static context
-cannot use this keyword in a static method because this keyword is based on objects 

Constructors 

-Constructors are special methods in java
-Constructors are used to initialise variables in a class
-Whenever an object is created a constructor is called(default constructor) 
Main myObj = new Main();
//Main() - This is the constructor here 

-Methods vs Constructors:
//methods have a return type
public void FunctionName(){

}

//constructors dont have a return type
public ClassName(){
  
}
—Types of Constructors

-Default constructor(if we don’t define a constructor manually java will automatically call the default constructor)
-Parameterised constructor(a constructor which takes arguments jus like method)
-Copy Constructor(copies the values of an old object to a new object)

this. Keyword

-This keyword is most simplest keyword in java
-this keyword is accessing the current object 
-By reference variable I mean objName
refrenceVariableName.Variable = Variable
-we use this keyword when the method argument and the class variables are the same so when I use this. Infront of the variable name system knows that I am accessing the current objects reference variable not the variable of the method
public class Main{
      int x; // created a class variable
      int y;
    
      public Main(int x,int y){
         this.x=x; // this.x is reaplaced by ObjName.x=x;
         this.y=y;
      }
}
RealLife Example:
Imagine a parent teachers meeting and two students A and B have same name lets consider Adhi as name.the teacher says 
Adhi’s parents are here(suppose student A’s parent is here) so the teacher points her finger and says This Adhi’s parents are here not the other one’s.

Final keyword

-final keyword is a special keyword
-this is how we use final:
final int x=10;
-final variables have to be initialised while declaring it
-you cannot modify the final variable or overwrite it 
-you cannot change the value only if it is primitive data type
-if its is an object the value can be changed but it cannot be reassigned

Garbage Collection

-Garbage collection is an automatic memory management function of java
-The java clears the memory automatically 
-You cant free the memory manually it is automatic 
-We can override the finalise method to do something when the memory is cleared but we cant clear the memory manually

Packages
-Packages in java are used to organise code
Ex:if we are working on a web devlopment project we’ll make 2 packages frontend and backend
-We use packages to avoid name conflicts because in java you cannot create 2 folders with same name inside a package
-packages makes the code more maintainable 

—>Two types of packages
-Built-in Packages
-User-Defined Packages

Built in Packages:
-These are the packages that comes with JDK for free 
-The java Api contains many pre written functions which makes coding in java much easier
-The java api library is divided into packages and classes 
-You can either a whole package that contains the Classes you want to use or you can jus import that specific class from the package
import package.name.Class; //importing a class from package
import package.name.*; //import the whole package
-A good example for this is the Scanner class that we use to get input in java
import java.util.Scanner;
-here we are importing ‘Scanner’ from java.util package with its methods and attributes 
-You can create your own package by using the ‘package’ keyword
package mypack;
class MyPackageClass {
  public static void main(String[] args) {
    System.out.println("This is my package!");
  }
}



Access modifiers:
Access Modifier	within class	within package	outside package by subclass only	outside package
Private	Yes	No	No	N
Default	Yes	Yes	No	N
Protected	Yes	Yes	Yes	N
Public	Yes	Yes	Y	Y

Principles of OOPS

Note:You cannot learn this part without implementing these principles and asking yourself why things are happening in a logical way

Inheritance:
-we achieve inheritance by using extends keyword
-inheritance means stuffs inside parent class will be available and can be accessed by the child class

Encapsulation:
-Encapsulation and abstraction are closely related 
-It solves implementation level problem but abstraction solve design level problems
-Encapsulation is done by combing both data and method into a single class 
-Makes code look much more cleaner and easier to work with

Polymorphism :
Poly:many morphism:way of representing
-There are two types of polymorphism => Static polymorphism/method overloading. Dynamic polymorphism/method Overriding

Dynamic polymorphism/method Overriding:
-Dynamic polynorphism works on principle of dynamic dispatch	
-it happens during run time
-we use a cool method call upcasting to achieve this
-late binding —>runtime
-overiding depends on objects and static methods dont depend on objects so static methods cannot be overridden

Static polymorphism/method overloading
-Method overloading happens during compile time
-we cannot overload static methods
-constructors and methods can be overloaded 
-we achieve overloading by using same method name but different arguments, parameters and order of arguments
“A parameter is a variable in a method definition. When a method is called, the arguments are the data you pass into the method's parameters.”


Abstraction :
-process of hiding the implementation part and only showing the essential information
-can be achieved with abstract classes or interfaces 
-abstract keyword is a non access modifier
-Abstract class: is a restricted class that cannot be used to create objects (to access it, it must be inherited from another class).
-Abstract keyword is used to create an abstract class
-Abstarct classes can have both abstract and static methods
-Abstarct methods can only be declared without a function definition
-Abstract method: can only be used in an abstract class, and it does not have a body. The body is provided by the subclass (inherited from).

Interfaces:
-Interfaces in java is another way to implement abstraction in our code
-we use interface in main class
-we use implements as a keyword infant of the class that we need to inherit it
-methods in interface cannot have a body
-interfaces solve the issue of multiple inheritance 
-We can use interface to inherit multiple classes(multiple inheritance)
-interface to interface => extends
-interface to classes => implements

Enum:
-An enum is a special "class" that represents a group of constants (unchangeable variables, like final variables).

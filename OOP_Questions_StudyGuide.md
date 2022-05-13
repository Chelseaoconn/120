1) **What is OOP and why is it important?**

 *OOP is a programming paradigm that was created to deal with the growing complexity of large    software systems.  By limiting the dependancies throughout, programs can be easier maintained.   Through the use of classes- and utilizing objects instantiated from these classes- the program can become an interaction of small parts and the data is containable.  These 'containers' allow for changes to be made to certain parts of the program, without it affecting the entire program.*

- *Large, complex programs can be difficult to maintain due to dependencies throughout the program. OOP lets programmers write programs in which the different parts of the program interact, thus reducing dependencies and facilitating maintenance.*

- *Coding in a non-OO way often means writing code that is useful solely within a single context. Defining basic classes and leveraging concepts like inheritance to introduce more detailed behaviors provides a greater level of reusability and flexibility.*

- *Complex coding problems are often difficult to break down and solve in a clear and systematic way. Using OOP to mwhat odel classes appropriate to the problem, and using real-world nouns to represent objects, lets programmers think at a higher level of abstraction that helps them break down and solve problems.*

  

2. **What is encapsulation?**

  *Encapsulation is shielding pieces of functionality and making it inaccessible to the rest of the codebase. It is a way of protecting data from manipulation without obvious intent.  Ruby allows for more complexity through encapsulation by the creation of objects and methods, which allow interaction with those objects. The best practice in OOP is to use real-world language, which introduces a new level of abstraction as the programmer can think of programs in terms of nouns (classes) and verbs (methods).*

  1) Objects encapsulate state- Ruby accomplishes encapsulation by creating objects and exposing interfaces (i.e. methods) to interact with those objects. 
  2) Classes encapsulate behavior

  

3. **How does encapsulation relate to the public interface of a class?** 

  **Encapsulation allows for the internal representation of an object (state and behavior?) to be hidden  from the outside.  Through the use of access controls, there is added control and discretion given to the programmer.  Because Ruby interacts with objects through methods,  we comonly refer to these as method access controls.  Ruby uses the module#public method to expose the properties and methods through the public interface. This is the default access control, so aside from the initialize method which is inheritantly private, all methods will be public unless expicitly stated otherwise. With the use of the module#private and module#protected methods, an error will be raised when trying to access those methods from outside the class.  This limits the public interface in terms of accesibility to those behaviors and states of an object.* 

  	???What is the internal representation of an object???
  				- State and behavior?

  


4. **What is an object?**

  **Everything in Ruby is an object, at least everything with a value.  Classes are the blueprint for objects, in such, objects are created from classes.  Objects are self-contained, and contain data (state) and behaviors (methods) that can communicate with other objects. Objects created from the same class have access to the same behaviors, but do not share information with other objects of the same type.* 

  ```ruby *
  ???To possess an attribute, the public interface must have access to the instance variable through the use of a getter and/or setter method. A class is said to define attributes and behaviors so are attributes just attribute signifiers???
  ```

  

5. **What is a class?**

  **Classes define the attributes and behaviors of the objects instantiated from that class.  A class in Ruby is a first-class object and each is an instance of the class Class.  It is essentially a blueprint from which objects are created.*

  

6. **What is instantiation?** 

  **The entire workflow of creating a new object or instance from a class.*  

  

7. **What is polymorphism?** 

  **The ability for different types of data to respond to a common interface.  For example, if you call an enumerable method on different class types, and each one has access to a method with the same name as the one being called upon, this is an example of polymorphism. In other words, objects of different data types responding to the same method invocation.  Polymorphism can involve inheritance from a common superclass, but that is not required.  Unless you design methods to be polymorphic with intention, you shouldn't use polymorphism.* 

  

8. **What are two different ways to implement polymorphism?**

- *Polymorphism through inheritance (can also be defined as method overriding)*

- *Polymorphism through duck-typing (unrelated types responding to the same method name)- Working on the idea of what an object can do, rather than its class.* 

- polymorphism through interface

  

9. **How does polymorphism work in relation to the public interface?**

  **Different data types can respond to a common interface.* 

  

10) **What is duck- typing? How does it relate to polymorphism- what problem does it solve?**

	**Duck-typing occurs when unrelated types respond to the same method name.  We are not concerned with the type, only the behavior of the type. Duck-typing is a form of polymorphism, and it is an informal way to classify a type to objects.  Using Duck-typing, we are able to avoid lengthy case statements and invoke methods of the same name on unrelated classes.* 
	
	
	
11) **What is inheritance?**

	**A class (subclass) inherits behaviors from another class, often called the superclass.  This allows Ruby to define basic classes with large reusability and smaller suclasses for more detailed behaviors. In this way, we can extract common behaviors and adhere to the DRY(don't repeat yourself) principle.*
	
	- *Class inheritance- superclass/subclass relationship*
	
	  - *Interface Inheritance- modules (mixins)*
	
	 
	
12) **What is the difference between superclass and subclass?**

	**A subclass inherits from a superclass.  A subclass has the characteristics of the superclass but is more refined.  The subclass has a "is-a" relationship with the superclass. Ruby does not allow for multiple inheritance.*
	
	
	
13) **What is a module?**

	**A module is a collection of behaviors that is usable in other classes via mixins. A module is mixed in to a class via the include method invocation/  Modules do not inherit and the programmer can mixin multiple modules into a class. We can achieve polymorphism through modules because classes of different types that include the same module have access to the same methods.* 
	
	
	
14) **What is a mixin?**

	**A mixin is a module (a collection of behaviors that is usable in other classes) that has been included within a class using the include method invocation.* 
	
	
	
15. **When is it good to use inheritance?**

    **Class based inheritace works great when it's used to model hierarchical domains.* 

    

16. **In inheritance, when would it be good to override a method?**

    **If an object of a class cannot perform a certain behavior, you can subclass that object and override that method(behavior).  If most other subclasses of that superclass can perform that behavior present in the superclass, overriding within the subclass that cannot may be the best option.*

    

17) **What is the method lookup path?**

	**This is the order in which Ruby will traverse the class hierarchy to look for methods to invoke.  A way to determine the lookup path is by using the ancestors class method.* 
	
	
	
18) **When defining a class, we usually focus on state and behaviors. What is the difference between these two concepts?**

	**States track attributes for individual objects; objects encapsulate state (the entirety of instance variables and their respective values). Behaviors are what the object is capable of doing.  Classes encapsulate behaviors, and all instances of that class have access to the behaviors defined within.  Instance variable are scoped at the object level and are how the objects keep track of their states. State is not shared between instances of the same class (objects are self- contained) but behaviors are shared between instances.* 
	
	
	
19) **How do you initialize a new object?**

	**The initialize method gets called every time you create a new object. The new method leads us to the initialize method.  We refer to the initialize method as a construcor.  *
	
	```ruby 
	class Being
	  def initialize(name)
	    @name = name 
	  end
	end
	
	first = Being.new('human')
	```
	
	
	
20) **What is a constructor method?**

	**A constructor gets triggered whenever we create a new object, therefor we refer to the initialize method as the constructor.* 
	
	
	
21) **What is an instance variable, and how is it related to an object?**

	**An instance variable is a way to track an object's state.  It is preceded by the @ symbol and is scoped to whatever object self refers to. Instance variables are never public, and are accessed through getter methods. They are how we tie data to objects.*
	
	
	
22) **What is an instance method?**

	**An instance method is defined within the class and is not preceded with self (which refers to the Class).  It provides functionality to one instance of a class. AKA singleton methods.*  
	
	
	
23) **How do objects encapsulate state?**

	**Objects encapsulate state. An objects state is saved in its instance variables which are only accessible through getter methods.* 
	
	
	
24) **What is the difference between classes and objects?**

	**Classes are the blueprints in which states objects are instantiated.*  
	
	
	
25) **How can we expose information about the state of the object using instance methods?**

	**Instance variables are inaccessible outside of the class unless there are specific methods to expose them.  These accessor methods are specifically called getter methods and they allow us to call a method on an object to expose the value of the instance variables.* 
	
	
	
26. **What is a collaborator object, and what is the purpose of using collaborator objects in OOP?**

    *A collaborator object is an object that is stored as state within another object.  They work in conjunction with the class they are associated with. All objects are technically collaborator objects, but we are generally referencing custom objects. They are useful to connect different pieces of your program.  Collaborator objects allow you to modularize the problem domain into cohesive pieces and are at the core of OOP.  They allow you to model more complicated problems. The collaborator object generally exhibits a "has-a" relationship with the defining object.   When an instance variable is assigned to a new object, that new objects public interface becomes available to an instance variable in a different class. This allow for purposeful connections and flexibility in a program.*

    

27) **What is an accessor method?**

	**An accessor method allows you to access the instance variables of an object. You would get a NoMethodError if you tried to access an instance variable from outside the class with no accessor methods available. There are getter methods which expose the instance variables, and setter methods which allow you to change the value of the instance variables from outside the class. In other words, getters and setters allow you to expose and change an object's state.* 
	
	
	
28) **What is a getter method?**

	**A getter method allows you to expose the state of an object(instance variable). An instance variable combined with the getter method is now said be an object's attribute. Without a getter method, a NoMethodError would arise when trying to access the instance variable from outside the class.  A shorthand for a getter method is the attr_reader which takes a symbol as an argument and returns the value of the instance variable with the same name.* 
	
	
	
29) **What is a setter method?**

	*A setter method allows you to change the state of an object from outside the class.  a shorthand for a setter is attr_writer, which takes a symbol as an argument and has the syntax* 
	
	```ruby 
	object.instance_variable_name = new_value 
	```
	
	*Setters always return the value that is passed in as an argument.*  
	
	
	
30) **What is attr_accessor?**

	**Attr_accessor is Ruby's built-in way to automatically create getter and setter methods.  It is a combination of both attr_reader and attr_writer.  This method takes symbols as arguments, and allows the user to expose and change the state of an object from both inside and outside of the class.* 
	
	
	
31) **How do you decide whether to reference an instance variable or a getter method?**

	**When using these methods from within the class, we generally want to utilize the getter and setter methods, instead of referencing the instance variables directly. This is helpful when the getter method alters the instance variable in any way.  If we reference the getter then we can easily resolve issues in the program that arise from that instance variable reference.* 
	
	
	
32) **When would you call a method with self?**

	**If we are setting a variable equal to a value, ruby will assume we are initializing a local variable instead of setting an instance variable to a new value. Using self#method allows us to call the setter method on the self object, which sets the value of the instance variable instead of creating a new local variable.* 
	
	
	
33) **What are class methods?**

	**Methods that we call on the class itself without having to instantiate a new object.  When defining a class method, we prepend the method name with the reserved word, self. Class methods are a way to have functionality that does not pertain to individual objects, or their state.*
	
	
	
34) **What is the purpose of a class variable?**

	**A class variable is created using two @ symbols (@@) and are specific to the entire class.  The class variable is scoped to the class and can be accessed from methods within the class. The class variable can reference data that is applicable to every instance of that class.  There is only one copy of a class variable and it is loaded as the code is run. This means that subclasses can change the value of a class variable for all subclasses and the superclass.* 
	
	
	
35) **What is a constant variable?**

	**A constant variable is a variable whose values you never want to change throughout the program. Constants are defined by using upper case letters (technically the first letter only needs to be capitalized).  Constants should be defined outside of the methods within the class.  Ruby constants are accessed within the class or outside of the class using this syntax: Class::constant.  The :: is a unary/scope/namespace resolution operator. Constants are available to child classes, nested classes, mix-ins, etc using this scope resolution operator*

  

 36) **What is the default to_s method that comes with Ruby, and how do you override this?**

	**The to_s method comes built in to every class in Ruby from the Object class. The to_s method returns the name of the object's class and the encoding of the object id.  Every time puts is called or string interpolation is used, Ruby calls to_s on the argument.  To override this we can make our own to_s instance method within the class.  This allows us to make a more more human- friendly output while referencing the object.* 
	
	
	
37) **What are some important attributes of the to_s method?**

	**Objects class and encoding of the object id.* 
	
	
	
38) **From within a class, when an instance method uses self, what does it reference?**

	**Self from within an instance method references the calling object, or the object instantiated from the class.* 
	
	
	
39) **What happens when you use self inside a class but outside of an instance method?**

	**Self inside a class and outside of an instance method refers to the class itself.  You see this when self is prepended to a method definition which defines a class method.* 
	
	
	
40) **Why do you need to call self when calling private setter methods?**

	**Without prepending self within a setter method, instead of changing the value of the instance variable, you will initialize a new local variable to the value you wish to set the instance variable to. The instance variable's value will remain unchanged and you will have an local variable inaccessible to the rest of your program.* 
	
	
	
41) **Why use self, and how does self change depending on the scope it is used in?**

	**Self is a way of being explicit about what our program is referencing and what our intentions are as far as behavior.  When scoped within an instance method, self refers to the instance. While defining a class method, self refers to the class itself.*  
	
	
	
43) **Give an example of how to use class inheritance.**
```ruby
	class Being;end
	class Human < Being
	end
```



44) **Give an example of overriding. When would you use it?**

```ruby
	Class Being
		def move
			"Can walk"
		end
	end

	Class Fish < Being
		def move
			"Can swim"
		end
	end
```
**In this example Fish is a subclass of Being.  When the move method is invoked by an instance of Being, "Can Walk" will be returned.  Being may contain many other methods relavant to Fish and Fish has an "is-a" relationship with Being, so subclassing is appropriate.  Overriding the method #move allows for the Fish object to resolve the call to #move within the Fish class, and therefor "Can swim" will be returned.*
		

45) **Give an example of using the super method.  When would you use it?**

	**The super keyword calls methods earlier in the method lookup path.  When you call super from within a method, it searches the method lookup path for a method with the same name, and then invokes it.  This is a way to extend functionality to a method.  Another way to use it is within the initialize method, which will call initialize and can give access to the instance variables higher in the method lookup path.* 
	
	
	
46) **Give an example of using the super method with an argument.**

	**When super is called without an argument it will take the arguments from the method it is within and forwards them to the method super is invoking.  If you specify the arguments to super, it will only take those arguments.  If you call super() then no arguments will be passed to the earlier method with the same name.* 
	
	
	
47) **When creating a hierarchical structure, under what circumstance would a module be useful?**

	**This is a way to add interface inheritance to your program.  These are useful when illistrating a "has-a" relationship. The goal here is to not repeat yourself (DRY code).  You see these mixins often named with an "able" suffix on a verb.  You can add as many mixins to your program as needed.*

  

 48. **What is interface inheritance, and under what circumstance would it be useful in comparison to class inheritance?**

     **Interface inheritance is inheritance through mixins.  It is useful from "has-a" relationships and often describes actions that an object has access to.  With interface inheritance, the class doesn't inherit from another type, but instead inherits the interface provided by the mixin module.  The result type is not a speicalized type with respect to the module.*  

     

49) **How is the method lookup path affected by module mixins and class inheritance?**

	**The method lookup path is the order in which classes are inspected when you call a method.  Ruby first looks in the class itself, then the modules (The last module included in the class will be first in the method lookup path), then the superclasses, Object, Kernal, BasicObject.  Ruby will traverse all the classes and modules in the method lookup path.  Mixins available to the superclasses will also be available to the subclass.* 
	
	
	
50) **What is namespacing?**

	**Namespacing is another use of modules, which means oeganizing similar classes under a module.  If we group related classes, we can easily recognize that they are related and it will reduce the likelihood of classes interfering with other similarly named classes in the codebase.*  
	
	
	
51) **How does Ruby provide the functionality of multiple inheritance?****

	**Because Ruby does not allow for multiple direct superclasses (single inheritance), mixins are a way to acquire multiple inheritance.  You can mixin as many modules as you like, so through class inheritance and interface inheritance you are able to have access to multiple inheritance.  Mixins act as a copy- paste of the methods within the module to the class.* 
	
	
	
52) **Descibe the use of modules as containers.**

	**Modules can work great when there are methods that seem out of place in the codebase.  By prepending the method with self (in this case, the module itself) we can call a method from outside the module using module name and method.  In this way, we can contain the out of place methods, and give them a module to call upon invocation.* 
	
	
	
53) **Why should a class have as few public methods as possible?**

	**Through encapsulation, we are able to hide the internal representation of an object from the outside and only expose the methods and properties that users of the object need.  Method access controls allow us to limit the methods available to the public interface. We are able to hide how the method is implemented.  Using the least amount of public methods as possible allows us to simplify using that class and protect the data from undesired changes from the outer world.* 
	
	
	
54) **What is the private keyword for?**

	**These are for methods that are doing work within the class but don't need to be availbale to the rest of the program. Private methods help further encapsulate an object, they’re used to shield instance methods that aren’t necessary to be public from being accessed by the rest of the code-base. This eliminates unintentional changes to an objects state.*
	
	

55) **What is the protected keyword used for?**

	**The protected keyword restricts access to the methods from outside the class by working as private, and acts as a public  from within the class.*  
	
	
	
56. **What are two rules of protected methods?**

    - *From inside the class they act just like public methods*

    - *From outside the class they act like private methods*

      

57. **Why is it generally a bad idea to override methods from the Object class, and which method is commonly overriden?**

    **A method commonly overriden is the to_s method, which outputs the class name and the encoding of the class object id.  When overriden within the class, you can give a more human- readable representation of the object when puts is called or during string interpolation.*

    **Every class you create subclasses from the class Object.  If you override a method found in the Object class, it could have far-reaching ramifications.  Every class that subsequently subclasses from that class would inherit this overriden method and that may not be the intention.*  

    

58) **What is the relationship between a class and an object?**

	**A class is a blueprint in which an object is instantiated.  A class defines data(instance variables) and behavior(methods), whereas the object is defined by state(accumulation of instance variables). An object has an "is-a" relationship with a class. Objects do not shaere state between other objects, but do share behaviors.* 
	
	
	
59) **Explain the idea that class groups behaviors.**

	**Classes define the attributes signifiers and behaviors of its objects.  The methods inside the class can be available to the class itself (class methods- not available to objects) or instances of that class (instance methods).  The class is a blueprint for the behaviors accesible to the object and class.  All objects instantiated from the class will have access to the methods within the class.*  
	
	
	
60. **What happens when you call the p method on an object? And the puts method?**

    **The p method outputs the call of #inspect on the object: the class, encoding of object id, and inititalized instance variables- state). #puts outputs the call of to_s on the object which is the class name and encoding of the object id.* 

    

61) **What is a spike?**

	**Exploratory code to play around with the problem. This is throw- away code to confirm or disprove initial hypotheses.* 
	
	
	
62) **When writing a program, what is a sign that you're missing a class?**

	**When you keep referring a noun within the instance methods,, you should probably encapsulate that logic into its own class.  If we encapsulate the logic we are able to have behaviors that we could call on the object itself, instead of calling straggling helper methods.* 
	
	
	
63) **What are some rules/ guidelines when writing code in OOP?**

	1) *Explore Problem before design (spike)*
	
	2. *Repetitive nouns in method names is a sign that you're missing a class*
	
	3. *When naming methods, don't include class name*
	
	4. *Avoid long method invocation chains*
	
	5. *Avoid deisng patterns for now - "premature optimization is the root of all evil"*
	
	   
	
64) **How does equivalence work in Ruby?**

	"One of the most common fake operators to be overridden is the `==` equality operator. Since we spent a good amount of time talking about that already, we won't cover it in depth here. Suffice it to say it's very useful to provide your own `==` method. Defining this method also gives us a `!=` method automatically."
	
  *== and .equal? are defined in BasicObject and determines if the two values are the same object,, but each class should define a == method to specify the value to compare.*
  *#equal? determines if two objects point to the same value*
    *#== is a method that you need to define to compare what value you want to compare*
    *=== Implicitly used by the case statement Does the range contain the value* 
    *#eql? Same value and same class*

  

65) **How do you determine if two variables point to the same object?**

	**.equal?*
	
	
	
66) **What is == in Ruby? How does == know what value to use for comparison?**

	**== is defined in BasicObject and determines if two objects point to the same object.  Subclasses of BasicObject define their own == method to specify which value to compare within the object for equivalence.* 
	
	
	
67) **Is it possible to compare two objects of different classes?**

	**Yes, if you implement the == to compare different classes, you can compare them.*
	
	
	
68) **What do you get for free when you define a == method?**

	**#!= (not equivalent)*
	
	
	
69) **What is the === method?**

	**The === method asks if a number is within a range of numbers. in Range (like include?)*
	*Can act as .is_a? to determine class ex/ class Being ;end a = Being.new Being == a (true)*
	*Case statements use === implicitly* 
	
	
	
70) **What is the .eql? method?**

	**Used implicitly in Hash. Determines if two objects contain the same value and if they're of the same class.*  
	
	
	
71) **What is the scoping rule for instance variables?**

	**Instance variables are scoped at the object level.  They track individual object state and do not cross over between objects.  The instance variable is accessible within the object's instance methods, even if defined outside of that method (don't require being passed in as an argument).  If you try to access an uninitialized instance variable you get nil instead of an Error.  You cannot access instance variables from outside the class without specific 'getter' methods.*
	
	
	
72. **What are the scoping rules for class variables? What are the two main behaviors of class variables?**

    *Class variables are scoped at the class level.  They are inaccesible from the outside of the class and contain data that pertains to every object of that class, in other words.. is not specific to any instance of that class. They can be used to track class level information.*

    	- *All objects share 1 copy of the class variable- objects can access class variables via instance methods*

      - *Class methods can access class variables regardless of initialization location.*

        

73) **What are scoping rules for constant variables?**

	**Constant variables have lexical scope, meaning that where the constant is defined determines where it is available.  When Ruby tries to resolve a constant, it searches lexically. Accessible to both class and instance methods.  If a Constant is defined in an unrelated class, the Constant is inaccessible and will produce a NameError unless we reach into the defining class using the namespace resolution operator.*
	
	
	
74) **Are class variables accessible to sub - classes?**

	**Yes, class variables are accessible to sub-classes and can also be resassigned from other sub-classes.. so be careful when and if you wish to reassign a class variable from a subclass bc it will affect the superclass and all subclasses of that superclass. The class variable is loaded when the class is evaluated in Ruby.*
	
	
	
75) **Why is it recommended to avoid the use of class variables when working with inheritance?**

	**Because class variables are loaded when the class is evaluated in Ruby, any reassignment of the class variable in any sub-classes will be visible upon defining that sub-class and can lead to unwanted ramifications in other subclasses as well as the superclass.  This is due to the fact that there is only one copy of the instance variable and it is accessible to any subclass.* 
	
	
	
76) **Is it possible to reference a constant defined in a different class?**

	**Yes, you can reference a constant defined in a different class using the namespace resolution operator.* 
	
	
	
77) **What is the namepace resolution operator?**

	**(scope/namespace/unary) resolution operator- helps to identify and specify the context to which an identifier refers.* 
	
	
	
78) **How are constants used in inheritance.** 

	**The constant will search lexically to resolve the constant. If that is unsuccessful, it will traverse up the inheritance hiearchy of the stucture that references that constant.* 
	
	
	
79) **What is lexical scope?**

	**AKA static scope. Occuring within the same code block..Location of the code vs what the code interprets to.* 
	
	
	
80) **When dealing with code that has modules and inheritance, where does constant resolution look first?**

	**Constant resolution will resolve the constant in a lexical fashion, meaning that if the constant is referenced within a module where the constant is defined, it will resolve the constant within the module.  If the constant is unresolved lexically, is will traverse the inheritance hierachy until it resolves the constant.* 
	
	
	
81) **When do shift methods make the most sense?**

	**They make sense in terms of lists or collections of data. <<* 
	
	
	
82) **Explain how the element getter (reference) and setter methods work, and their corresponding syntactical sugar.** 

	**Element getter and setters allow you to get and set elements of an array.  [] and []= are methods, not operators.*  
	
	```ruby 
	def [](ind)    #getter
		array[ind]
	end
	
	def []= (ind, value)  #setter
		array[ind]= value
	end
	```
	
	
	
83) **How is defining a class different than defining a method?** 

	**defining a method uses the keyword def while defining a class uses the keyword class. Both use end to close the expression. Methods use snake_case and classes use CamelCase.*
	
	
	
84) **How do you create an instance of a class?** 

	**Calling the class method new which leads you to the initialize method within the class.* 
	
	
	
85) **How do you define a class method**

	**Prepend the method with self (self here refers to the class)*
	
	
	
86. **What does the p method print out?**

    **#p print the object so that inspect is called, which lets us view the instance variables and their values along with the encoded object id.*

    

87. **When writing the name of methods in normal/ md text, how do you write the name of an instance method? A class method?**

    **ClassName#instance_method_name // ClassName::class_method_name*

    

88. **How do you override the to_s method? What does the to_s method have to do with puts?**

    **Class#puts calls to_s on the argument passed in and will output a string representation of the encoded objects id.  We can override this method within the class to give a clearer representation of the object. to_s is defined in the Object Class.* 

    

89. **When do you use parentheses with super?**

    **When you want to invoke a superclass method and explicitly pass no arguments to the superclass method to prevent an argument error.* 

    

90. **How do you find the lookup path?**

    **Call the ancestors method on the class.*

    

91. **What is namespacing and how do you instantiate a class contained in a module?**

    **Namespacing is grouping related classes, perhaps to prevent similarly named methods from colliding. You can instantiate a class contained in a module by using the namespace resolution operator, ::  (Module::Class.new)*

    

92. **When using getters and setters, in what scenario might you decide to only use a getter, and why is this important?**

    **You might only need a getter if you only want to access the data, but don’t want or need to be able to change it.*

    

93. **When might it make sense to format the data or prevent destructive method calls changing the data by using a custom getter or setter method?**

    **Anytime you want to control how the user is able to access or change data- getters and setters protect raw data. A custom getter and setter can be used to format and/ or validate the data.  This can add extra functionality to the method ex/ capitalize input .. make sure the input meets certain requirements before setting it to an instance variable.*

94. **False Operators** 

    Many operators are in fact methods that Ruby gives special treatment to. Because they are methods, we can implement them in our classes and take advantage of the special syntax for our own objects. If we do that, we must be careful to follow conventions established in the Ruby standard library. Otherwise, using those methods will be very confusing.
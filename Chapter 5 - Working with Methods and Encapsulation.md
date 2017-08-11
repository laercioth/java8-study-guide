1. All interfaces methods are implicity public. Since Java 8 now includes default and static
   methods and they are never abstract, you cannot assume the abstract modifier will be
   implicitly applied to all methods by the compiler.

2. Overriding rules:

	- the rules for overriding a method allow a subclass to define a method with an 
	exception that is a subclass of the exception in the parent method.
	- For nonprivate methods in the parent class, both methods must use static
	 (hide) or neither should use static (override).
	-  If instance variable is hide depends where the methods belongs which class it will be use the his own instance variable
	from its class.

3. Covariant Return Type
	
	Since Java5, it is possible to override method by changing the return type if subclass overrides any method 
	whose return type is Non-Primitive but it changes its return type to subclass type.

4. Which can only can be hidden and not overriden:

	- private instance methods.
	- static methods
	- public variables
	- private variables

	Variables may only be hidden, regardless of the access modifier.

5. Polymorphic

	- A reference to an object requires an explicit cast if referenced with a subclass.
	If the cast is to a superclass reference, then an explicit cast is not required.
	- Because of polymorphic parameters, if a method takes the superclass of
	an object as a parameter, then any subclass references may be used without a cast
	- All objects extend java.lang.Object, so if a method takes that
	type, any valid object, including null, may be passed.

6. Interfaces and Abastract classes

	- Only interfaces can contain default methods
	- Both abstract classes and interfaces can contain static methods
	- Both structures require a concrete subclass to be instantiated
	- Though an instance of an object that implements an interface inherits java.lang.
	Object, the interface itself doesn’t; otherwise, Java would support multiple inheritance
	for objects, which it doesn’t.
	- Interface variables are assumed to be public static final

7. Constructor:

	1. The first statement of every constructor is a call to another constructor within the class
	using this(), or a call to a constructor in the direct parent class using super().
	2. The super() call may not be used after the first statement of the constructor.
	3. If no super() call is declared in a constructor, Java will insert a no-argument super()
	as the first statement of the constructor.
	4. If the parent doesn’t have a no-argument constructor and the child doesn’t define any
	constructors, the compiler will throw an error and try to insert a default no-argument
	constructor into the child class.
	5. If the parent doesn’t have a no-argument constructor, the compiler requires an explicit
	call to a parent constructor in each child constructor.


8. Three faces of final

	Final in variable its means the variable is GLOBAL or INSTANCE and it cannot be modified
	Final in class its means the class cannot be extensible
	Final in method its means the method cannot be override

-- Tips.

All of the static variables are defined in the class (with default values).  For example, the code public static String firstName = "Jason";  would result in the creation of the variable firstName  but in this step, it is assigned the default value of null (rather than the explicit value of "Jason").  This happens for all of the classes in the hierarchy (moving up the inheritance chain).

All of the static initialization blocks and explicit values assigned to static variables (such as "Jason" above), are executed in the base class, in the order they are written (from top to bottom).  

All of the static initialization blocks and explicit values assigned to static variables are executed for the immediate child of the base class, in the order they are written (from top to bottom).

Step 3 is repeated all the way down the object hierarchy until the instantiated object type is reached.

All of the instance variables are defined with default values, for all of the classes in the hierarchy (moving up the inheritance chain).

All of the instance initialization blocks and explicit values assigned to instance variables are executed for the base class, in the order they are written (from top to bottom).  

The constructor for the base class is executed.

All of the instance initialization blocks and explicit values assigned to instance variables are executed for the immediate child of the base class, in the order they are written (from top to bottom),

The constructor for the immediate child of the base class is executed.

Steps 8 - 9 are repeated all the way down the object hierarchy until the instantiated object type is reached.
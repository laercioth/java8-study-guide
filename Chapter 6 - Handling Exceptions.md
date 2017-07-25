
1. ExceptionHandling with MethodOverriding 
	If the superclass method does not declare an exception,
	subclass overridden method cannot declare the checked exception but it can declare unchecked exception.
	If the superclass method declares an exception, subclass overridden method can declare same,
	subclass exception or no exception but cannot declare parent exception.

2. Runtime exceptions are also known as unchecked exceptions.
	They are allowed to be declared, but they don’t have to be. Checked exceptions must be handled or
	declared. Legally, you can handle java.lang.Error subclasses, but it’s not a good idea

3. Exceptions:

	- java.io.IOException is thrown by many methods in the java.io package, but it is always thrown programmatically. 
	The same is true for NumberFormatException; it is thrown programmatically by the wrapper classes of java.lang.
	- 


4. You cannot declare an checked exception which is never thrown in that context.
    try {
        out.print(test());
    } catch (IOException io) {

    }

5. Exceptions:

	- Checked exceptions are required to be handled or declared.
	- Runtime exceptions are allowed to be handled or declared. 
	- Errors are allowed to be handled or declared, but this is bad practice.

6. Commons Exceptions:

	- Runtime Exceptions

		Thrown by the JVM
			- ArithmeticException
			- ArrayIndexOutOfBoundsException
			- ClassCastException
			- NullPointerException

		Thrown by the programer
			- IllegalArgumentException
			- NumberFormatException

	- Checked Exceptions
		- FileNotFoundException
		- IOException
		- ParseException
		- ClassNotFoundException
		- SQLException

	- Errors
		- ExceptionInInitializerError
		- StackOverflowError
		- NoClassDefFoundError
		- OutOfMemoryException

7. Finally
	If occur exception in the all code programming within the try block... compiler will to pass on finally
	block code
	If occur the exception or not in the try catch, finally always is called

8. Throws
	Throws is lancher of the method and throw is the inside the method

	sample:
		public void doIt() throws Exception, and so on {
			throw new Exception("Threw error!");
		}


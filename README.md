# JAVA BASICS

## 1. OOPS CONCEPTS

  ###  Class :
  - It is a template from which objects are created.
  ###  Object :
  - An Object is a real-world entity.
  - It is a runtime entity.
  - It is an entity which has state and behaviour.
  - It is an instance of class.
 ### Inheritance :
   - It is a mechanism in which one object acquires all the properties and behaviors of a parent object.
   - It represets *IS-A relationship*
   - It uses extends keyword 

**Why Use**
i. For Method Overriding
ii. For Code reusability
**REAL TIMA AUTOMATION**
- Inheritance is used to create a Base class for driver setup, tear-down, logs, and waits.
-  All test classes extend this Base class to reuse common functionality.

### Polymorphism :
- When a method show different behaviour at different time.
#### i. Method Overloading :
- When a class having more than one method with same name but different in parameter and types of parameter and length of parameter .
#### ii.MethodOverriding:
- If a subclass has same method as declared in the parent class.

**REAL TIMA AUTOMATION**
- Polymorphism allows us to overload utility methods and override behaviours.
- For example, different driver classes override WebDriver methods, and our framework utilities overload common actions.

### Encapsulation:
	- It is a process of wrapping code and data together into a single unit.
	- Achieved using private variables + public getters/setters
	- It protects sensitive data from being access directly.
	- Improves maintainability.

**REAL TIMA AUTOMATION**	
- We use encapsulation in Page Object Model. All web elements are kept private and exposed through public action methods.
- This protects objects from direct access and increases maintainability.

### Abstraction:
-  is a process of hiding the implementation details and showing only functionality to the user.
#### Abstract Class :
- It cannot be instantiated.
- It can have constructors and static methods also.
- It can have final methods, which will force the subclass not to change the body of the method.

## 2. DIFFERENT WAY OF CONCATENATING :
  - Using "+" (String concatenation) Operator
  - Using String.concat() Method
  - Using the StringBuilder or StringBuffer Class
  - Using String.join() Method (Java 8)
    - concatenate multiple strings with a delimiter
    ```java
        String firstName = "Manoj";  
        String lastName = "Mamilla";  
        // Using String.join for concatenation with a delimiter  
        String result = String.join(" ", "Hello,", firstName, lastName);
    ```

  - Using Java String.format() Method
  - Using Collector.joining() Method(Java 8)
    ```java
          List<String> liststr = Arrays.asList("abc", "pqr", "xyz"); //List of String array  
          String str = liststr.stream().collect(Collectors.joining(", ")); //performs joining operation
    ```

    ## COLLECTION :

    ### HashMap :
    - In Java, a HashMap is part of the Collection framework and is used to store key-value pairs. It works based on the principle of hashing.
    - It contains only unique keys.
    - It may have one null key and multiple null values.
    - It is non synchronized.
    - It maintains no order.
  ### Iterate MAP
  ### i. Iterator:
   -In Java, an Iterator is an interface within the java.util package that provides a standard way to traverse elements within a collection (like ArrayList, HashSet, LinkedList, etc.) sequentially.
  ```java
       HashMap<Integer,String> hm=new HashMap<>();
		hm.put(110, "Ravi");
		hm.put(111, "Ramesh");
		hm.put(120,"Prateek");  
		hm.put(130, "Davesh");    
		hm.put(140, "Kamal");  
		hm.put(150, "Pawan");  
		
		Iterator<Integer> it=hm.keySet().iterator(); // hm.keySet() returns a Set of all keys 
													//iterator() creates an iterator to loop through those keys.
		
		while(it.hasNext())
		{
			int key=it.next();
			System.out.println("Roll No"+key+"  Name  "+hm.get(key));
		}
  ```
### ii. keyset() and value() method
 -keyset(): A keySet() method of HashMap class is used for iteration over the keys contained in the map. It returns the Set view of the keys.
 ```java
  Map<String,String> map = new HashMap<String,String>();   
  map.put("Gujarat", "Gandhi Nagar");               
  map.put("Uttar Pradesh", "Lucknow");   
  map.put("Sikkim", "Ganagtok");   
  for (String State : map.keySet())   //using keyset() method for iteration over keySet  
  System.out.println("State: " + State);   
  for (String Capital : map.values())         //using values() for iteration over keys  
  System.out.println("Capiatl: " + Capital);
```
### iii. Map.entry<K,V>method
 - Map.Entry<K,V> is an interface. It returns a collection view of the map
 - A map.entrySet() method returns a Set view of the mapping contained in the map
```java
  Map<String, Float> map = new HashMap<String, Float>();   
map.put("Cookies",  90.87f);  
map.put("Dry Fruits", 434.23f);   
map.put("Oats", 220.00f);   
map.put("Chocolate", 70.89f);   
for (Map.Entry<String,Float> entry : map.entrySet()) //using map.entrySet() for iteration  
{  
//returns keys and values respectively  
System.out.println("Item: " + entry.getKey() + ", Price: " + entry.getValue());
```
### iv. keys and getting values
- first iterate over the keys and then getting the values.
```java
Map<String, String> map = new HashMap<String, String>();   
map.put("Sumit",  "Singh");  
map.put("Devesh", "Mishra");   
map.put("Rahul", "Tiwari");   
for (String name: map.keySet())         //iteration over keys  
{  
//returns the value to which specified key is mapped  
String lastname=map.get(firstname);   
System.out.println("Key: " + name + ", Value: " + lastname);
```
### v. forEach() method
-  forEach() method of ArrayList is used to perform an action for each element of the Iterable until all elements have been processed.
  ```java
Map<String,String> map = new HashMap<String,String>();   
map.put("TCS", "$100 billion");   
map.put("Wipro", "$21.5 billion");   
//iteration over map using forEach() method  
map.forEach((k,v) -> System.out.println("Company: "+ k + ", Net worth: " + v));
```

# MULTI-THREADING:
- “Multithreading is a programming concept where multiple threads run concurrently within a single process. Each thread performs a separate task, but all threads share the same memory space. It improves performance and resource utilization and is commonly used when we need to perform multiple operations in parallel, like handling multiple client requests or background tasks.”
  
** *Multithreading * means multiple threads share the same process and memory space to perform different tasks concurrently within a single application, which makes it lightweight and faster for I/O-bound tasks.

*Multiprocessing* means running multiple processes simultaneously, where each process has its own memory and resources, and it’s mainly used to achieve true parallelism for CPU-bound tasks.” **

```java
class NumberPrinter implements Runnable {
    private String threadName;

    public NumberPrinter(String threadName) {
        this.threadName = threadName;
    }

    @Override
    public void run() {
        for (int i = 1; i <= 5; i++) {
            System.out.println(threadName + " : " + i);
            try {
                Thread.sleep(500);  // pause the thread for 500ms
            } catch (InterruptedException e) {
                e.printStackTrace();
            }
        }
    }
}

public class MultithreadingExample {
    public static void main(String[] args) {
        // Create two Runnable objects
        Runnable p1 = new NumberPrinter("Thread-1");
        Runnable p2 = new NumberPrinter("Thread-2");

        // Create thread objects
        Thread t1 = new Thread(p1);
        Thread t2 = new Thread(p2);

        // Start both threads
        t1.start();
        t2.start();
    }
}
```

## Thread Life Cycle :
A thread goes through five main states in its lifecycle:
- New (created but not started),- this is when the thread object is created but the start() method hasn’t been called yet.
- Runnable (ready and waiting for CPU),- once start() is called, the thread becomes runnable. It is ready to run and waiting for CPU time.
- Running (currently executing),- the thread gets CPU and actually starts executing the code inside the run() method.
- Blocked/Waiting (not running, waiting for a monitor or resource) - during execution, a thread might temporarily stop if it’s waiting for a lock, sleeping or waiting for some other thread to complete. This is the blocked (or waiting) state
- Terminated (finished execution) -once the run() method finishes or the thread completes its execution, it enters the terminated or dead state.


** *Deadlock* is a situation in multithreading where two or more threads are each waiting for a resource held by the other, and as a result, none of them can proceed. It causes the threads to be stuck permanently. **

## Exception : 
an exception is an event that occurs during the execution of a program and disrupts the normal flow of instructions.
Exceptions can occur for various reasons, such as invalid user input, a file not being found, or division by zero. 
## Exception Handeling :
It is a mechanism that allows a program to handle runtime errors such as ClassNotFoundException, IOException, SQLException, RemoteException, 
### Throwable :
Throwable is the parent class of all errors and exceptions in Java.
- Error

Error represents serious system-level problems.

Caused by JVM

Not meant to be handled by programmers

Usually unrecoverable

Examples:

OutOfMemoryError

StackOverflowError

VirtualMachineError

Example:

int[] arr = new int[999999999]; //



  







    

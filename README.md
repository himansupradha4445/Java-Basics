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

### Polymorphism :
- When a method show different behaviour at different time.
#### i. Method Overloading :
- When a class having more than one method with same name but different in parameter and types of parameter and length of parameter .
#### ii.MethodOverriding:
- If a subclass has same method as declared in the parent class.


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



    

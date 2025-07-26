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
    

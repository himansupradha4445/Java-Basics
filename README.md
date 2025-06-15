# JAVA BASICS

## DIFFERENT WAY OF CONCATENATING :
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
    

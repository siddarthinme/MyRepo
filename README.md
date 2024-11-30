Here is a breakdown of all the questions, starting from 1, along with their explanations and code:

---

### **1. Fibonacci Series using Recursion (Java)**

**Logic:**
The Fibonacci series is a sequence where each number is the sum of the two preceding ones, usually starting with 0 and 1. Recursion is used to calculate the Fibonacci numbers by calling the function within itself to reduce the problem size.

**Code:**
```java
class FibonacciExample2 {  
    static int n1 = 0, n2 = 1, n3 = 0;    

    static void printFibonacci(int count) {    
        if(count > 0) {    
            n3 = n1 + n2;    
            n1 = n2;    
            n2 = n3;    
            System.out.print(" " + n3);   
            printFibonacci(count - 1);    
        }    
    }    

    public static void main(String args[]) {    
        int count = 10;    
        System.out.print(n1 + " " + n2); // printing 0 and 1    
        printFibonacci(count - 2); // n-2 because 2 numbers are already printed   
    }  
}
```

---

### **2. Check if Two Strings are Anagrams (Java)**

**Logic:**
An anagram of a string is another string that contains the same characters, only the order of the characters can be different. To check if two strings are anagrams:
1. Remove spaces and convert the strings to lowercase.
2. Sort both strings and compare them.

**Code:**
```java
import java.util.Arrays;

public class AnagramString {  
    static void isAnagram(String str1, String str2) {  
        String s1 = str1.replaceAll("\\s", "");  
        String s2 = str2.replaceAll("\\s", "");  
        boolean status = true;  
        if (s1.length() != s2.length()) {  
            status = false;  
        } else {  
            char[] ArrayS1 = s1.toLowerCase().toCharArray();  
            char[] ArrayS2 = s2.toLowerCase().toCharArray();  
            Arrays.sort(ArrayS1);  
            Arrays.sort(ArrayS2);  
            status = Arrays.equals(ArrayS1, ArrayS2);  
        }  
        if (status) {  
            System.out.println(s1 + " and " + s2 + " are anagrams");  
        } else {  
            System.out.println(s1 + " and " + s2 + " are not anagrams");  
        }  
    }  
    
    public static void main(String[] args) {  
        isAnagram("Keep", "Peek");  
        isAnagram("Mother In Law", "Hitler Woman");  
    }  
}
```

---

### **3. Find the Factorial of a Given Number (Java)**

**Logic:**
Factorial is the product of all positive integers less than or equal to a number. Using a loop, you can multiply all the numbers from 1 to the given number to calculate the factorial.

**Code:**
```java
public class Factorial {
    public static void main(String[] args) {
        int number = 5;
        long factorial = 1;
        
        for (int i = 1; i <= number; i++) {
            factorial *= i;
        }
        
        System.out.println("Factorial of " + number + " is " + factorial);
    }
}
```

---

### **4. Find Missing Number in an Array (Java)**

**Logic:**
Given an array of non-duplicate numbers from 1 to `n`, the missing number can be found by calculating the sum of numbers from 1 to `n` and subtracting the sum of the array elements from it.

**Code:**
```java
public class MissingNumber {
    public static int findMissing(int[] arr, int n) {
        int sum = n * (n + 1) / 2;
        int arrSum = 0;
        
        for (int num : arr) {
            arrSum += num;
        }
        
        return sum - arrSum;
    }

    public static void main(String[] args) {
        int[] arr = {1, 2, 4, 6, 3, 7, 8};
        int n = 8;
        System.out.println("The missing number is: " + findMissing(arr, n));
    }
}
```

---

### **5. Check if a Number is a Magic Number (Java)**

**Logic:**
A magic number is a number where the sum of its digits is repeatedly calculated until a single digit is obtained. If the final single digit is 1, it is a magic number.

**Code:**
```java
class MagicNumber {
    public static boolean isMagic(int n) {
        int sum = 0;
        while (n > 0 || sum > 9) {
            if (n == 0) {
                n = sum;
                sum = 0;
            }
            sum += n % 10;
            n /= 10;
        }
        return sum == 1;
    }

    public static void main(String[] args) {
        int n = 1234;
        if (isMagic(n)) {
            System.out.println("Magic Number");
        } else {
            System.out.println("Not a Magic Number");
        }
    }
}
```

---

### **6. Create and Throw Custom Exceptions (Java)**

**Logic:**
A custom exception is created by extending the `Exception` class. A method can throw this exception if a certain condition is met, and it can be caught using a `try-catch` block.

**Code:**
```java
class InvalidAgeException extends Exception {
    public InvalidAgeException(String str) {
        super(str);
    }
}

public class TestCustomException1 {
    static void validate(int age) throws InvalidAgeException {
        if (age < 18) {
            throw new InvalidAgeException("Age is not valid to vote");
        } else {
            System.out.println("Welcome to vote");
        }
    }

    public static void main(String[] args) {
        try {
            validate(13);
        } catch (InvalidAgeException ex) {
            System.out.println("Caught the exception");
            System.out.println("Exception occurred: " + ex);
        }
        System.out.println("Rest of the code...");
    }
}
```

---

### **7. Rotate a Matrix 90 Degrees Clockwise (Java)**

**Logic:**
To rotate a matrix 90 degrees clockwise, you can print the elements of the matrix in a new order where columns of the original matrix become rows in the rotated matrix.

**Code:**
```java
import java.util.Scanner;

public class RotateMatrixClockwise {
    public static void main(String[] args) {
        Scanner scanner = new Scanner(System.in);
        int[][] matrix = new int[3][3];

        System.out.println("Enter the 3x3 matrix:");
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                matrix[i][j] = scanner.nextInt();
            }
        }

        System.out.println("Original Matrix:");
        for (int i = 0; i < 3; i++) {
            for (int j = 0; j < 3; j++) {
                System.out.print(matrix[i][j] + "\t");
            }
            System.out.println();
        }

        System.out.println("Matrix after 90 degree rotation:");
        for (int i = 0; i < 3; i++) {
            for (int j = 2; j >= 0; j--) {
                System.out.print(matrix[j][i] + "\t");
            }
            System.out.println();
        }
    }
}
```

---

### **8. Check if a Number is the Sum of Two Prime Numbers (Java)**

**Logic:**
Check whether a given number can be expressed as the sum of two prime numbers by iterating through numbers and checking if both the number and the difference are prime.

**Code:**
```java
public class SumOfTwoPrimes {
    public static boolean isPrime(int n) {
        if (n <= 1) return false;
        for (int i = 2; i <= Math.sqrt(n); i++) {
            if (n % i == 0) return false;
        }
        return true;
    }

    public static boolean isSumOfTwoPrimes(int n) {
        for (int i = 2; i < n; i++) {
            if (isPrime(i) && isPrime(n - i)) {
                return true;
            }
        }
        return false;
    }

    public static void main(String[] args) {
        int n = 10;
        if (isSumOfTwoPrimes(n)) {
            System.out.println("Yes");
        } else {
            System.out.println("No");
        }
    }
}
```

---

### **9. Tower of Hanoi Problem (Java)**

**Logic:**
The Tower of Hanoi problem is a classic example where you need to move disks from one rod to another while adhering to specific rules. The recursion divides the problem into smaller sub-problems by moving smaller numbers of disks.

**Code:**
```java
class TowerOfHanoi {
    public static void towerOfHanoi(int n, char from_rod, char to_rod, char aux_rod) {
        if (n == 1) {
            System.out.println("Move disk 1 from rod " + from_rod + "

 to rod " + to_rod);
            return;
        }
        towerOfHanoi(n - 1, from_rod, aux_rod, to_rod);
        System.out.println("Move disk " + n + " from rod " + from_rod + " to rod " + to_rod);
        towerOfHanoi(n - 1, aux_rod, to_rod, from_rod);
    }

    public static void main(String[] args) {
        int n = 3;
        towerOfHanoi(n, 'A', 'C', 'B');
    }
}
```

---

### **10. Binary Search Algorithm using Recursion (Java)**

**Logic:**
Binary search works by repeatedly dividing the search interval in half. A recursive approach divides the range until the element is found.

**Code:**
```java
class BinarySearch {
    int binarySearch(int arr[], int l, int r, int x) {
        if (r >= l) {
            int mid = l + (r - l) / 2;
            if (arr[mid] == x) return mid;
            if (arr[mid] > x) return binarySearch(arr, l, mid - 1, x);
            return binarySearch(arr, mid + 1, r, x);
        }
        return -1;
    }

    public static void main(String[] args) {
        BinarySearch bs = new BinarySearch();
        int arr[] = {2, 3, 4, 10, 40};
        int n = arr.length;
        int x = 10;
        int result = bs.binarySearch(arr, 0, n - 1, x);
        if (result == -1) System.out.println("Element not present");
        else System.out.println("Element found at index " + result);
    }
}
```

---

These solutions encompass a variety of concepts, including recursion, sorting, searching, exception handling, and mathematical problems.

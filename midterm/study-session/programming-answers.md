# Programming Answers
## Midterm Study Session

1. Below is one possible solution; but please note there are many correct solutions to this problem.

  ```java
  public static boolean balanceCheckbook(Scanner console) {
      System.out.print("initial balance? ");
      double balance = console.nextDouble();
      System.out.print("how many transactions? ");
      int count = console.nextInt();
      double min = balance;
      for (int i = 1; i <= count; i++) {
          System.out.print(i + "/" + count + " amount? ");
          double amount = console.nextDouble();
          balance = balance + amount;
          System.out.println("new balance = $" + balance);
          if (balance < min) {
              min = balance;
          }
      }
      System.out.println("minimum balance = $" + min);
      return (min < 0);
  }
  ```java

2. Below is one possible solution; but please note there are many correct solutions to this problem.

  ```java
  public static void printTwoDigit(Random r, int n) {
      boolean seen42 = false;
      for (int i = 1; i <= n; i++) {
          int number = r.nextInt(90) + 10;
          System.out.println("next = " + number);
          if (number == 42) {
              seen42 = true;
          }
      }
      if (seen42) {
          System.out.println("We saw a 42");
      } else  {
          System.out.println("no 42");
      }
  }
  ```
  
3. Below is four possible solutions; but please note there are many correct solutions to this problem.

  ```java
  public static boolean anglePairs(int a1, int a2, int a3) {
      if (a1 + a2 == 90 || a2 + a3 == 90 || a3 + a1 == 90) {
          if (a1 + a2 == 180 || a2 + a3 == 180 || a3 + a1 == 180) {
              return true;
          } else {
              return false;
          }
      } else {
          return false;
      }
  }
  ```

  ```java
  public static boolean anglePairs(int a1, int a2, int a3) {
      return (a1 + a2 == 90 || a2 + a3 == 90 || a3 + a1 == 90) &&
          (a1 + a2 == 180 || a2 + a3 == 180 || a3 + a1 == 180);
  }
  ```

  ```java
  // eliminate false cases first solution
  public static boolean anglePairs(int a1, int a2, int a3) {
      if (a1 + a2 != 90 && a2 + a3 != 90 && a3 + a1 != 90) {
          return false;
      }
      if (a1 + a2 != 180 && a2 + a3 != 180 && a3 + a1 != 180) {
          return false;
      }
      return true;
  }
  ```
  
  ```java
  // nest by which pair matches 90 vs. 180
  public static boolean anglePairs(int a1, int a2, int a3) {
      if (a1 + a2 == 90) {
          if (a2 + a3 == 180 || a1 + a3 == 180) {
              return true;
          } else {
              return false;
          }
      } else if (a2 + a3 == 90) {
          if (a1 + a2 == 180 || a1 + a3 == 180) {
              return true;
          } else {
              return false;
          }
      } else if (a1 + a3 == 90) {
          if (a1 + a2 == 180 || a2 + a3 == 180) {
              return true;
          } else {
              return false;
          }
      } else {
          return false;
      }
  }
  ```

4. Below is two possible solutions; but please note there are many correct solutions to this problem.

  ```java
  public static String graduation(double gpa, int credits, int honorsCredits) {
      if (credits >= 180 && gpa >= 2.0) {
          if (honorsCredits >= 15 && gpa >= 3.8) {
              return "summa cum laude";
          } else if ((honorsCredits >= 15 && gpa >= 3.6) || gpa >= 3.8) {
              return "magna cum laude";
          } else if (gpa >= 3.6) {
              return "cum laude";
          } else {
              return "graduating";
          }
      } else {
          return "not graduating";
      }
  }
  ```
  
  ```java
  public static String graduation(double gpa, int credits, int honorsCredits) {
      if (credits < 180 || gpa < 2.0) {
          return "not graduating";
      } else if (honorsCredits >= 15 && gpa >= 3.8) {
          return "summa cum laude";
      } else if (honorsCredits >= 15 && gpa >= 3.6 || gpa >= 3.8) {
          return "magna cum laude";
      } else if (gpa >= 3.6) {
          return "cum laude";
      } else {
          return "graduating";
      }
  }  
  ```

5.  Below is three possible solutions; but please note there are many correct solutions to this problem.

  ```java
  public static void cheerleader(int lines, int cheers) {
  for (int line = 0; line < lines; line++) {
  for (int space = 1; space <= line * 3; space++) {
  System.out.print(" ");
  }

  System.out.print("Go");
  for (int cheer = 2; cheer <= cheers; cheer++) {
  System.out.print(" Team Go");
  }
  System.out.println();
  }
  }
  ```
  
  ```java
  public static void cheerleader(int lines, int cheers) {
      String indent = "";
      for (int line = 1; line <= lines; line++) {
          System.out.print(indent);
          for (int cheer = 1; cheer <= cheers - 1; cheer++) {
              System.out.print("Go Team ");
          }
          System.out.println("Go");
          indent += " ";
      }
  }
  ```
  
  ```java
  public static void cheerleader(int lines, int cheers) {
      for (int line = 1; line <= lines; line++) {
          for (int space = 1; space <= line - 1; space++) {
              System.out.print(" ");
          }
          for (int cheer = 1; cheer <= cheers - 1; cheer++) {
              System.out.print("Go Team ");
          }
          System.out.println("Go");
      }
  } 
  ```
  
 
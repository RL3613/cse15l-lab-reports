# Part 1: StringServer
## Code
### Handler Class

```java
class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    String display = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return display;
        } else if (url.getPath().equals("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if(parameters[0].equals("s") && parameters.length > 1) {
                String toAdd;
                if(display.equals("")) {
                    toAdd = parameters[1];
                } else {
                    toAdd = "\n" + parameters[1];
                }
                display = display.concat(toAdd);
                return display;
            } else {
                return "Invalid query.";
            }
        } else {
            return "404 Not Found!";
        }
    }
}
```
### StringServer class
```java
class StringServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```
## Screenshots
### First Screenshot
![image](https://user-images.githubusercontent.com/110417529/214984221-b5178a13-bcf2-4152-b0b6-a31b9265e519.png)
In this screenshot, we added "Hello!" to our message.

The `main` method in StringServer is called, which calls the `start` method in Server. Server then calls `HandleRequest`.

So `HandleRequest` is called, and the URI parameter is our URL `localhost:4000/add-message?s=Hello!`.

`getQuery` is called, which outputs the part after the `/`. Splitting the query by `=`, we get that `parameter[0]` is `"s"` and `parameter[1]` is `"Hello!"`.

Variable `display` is `null` before the method. After the method is executed, variable `toAdd` is initiated to `parameter[1]`, and `display` is concatenated with `toAdd` to become `"Hello!"`.

### Second Screenshot
![image](https://user-images.githubusercontent.com/110417529/214987127-4c4b115e-3c00-482f-b46f-813cc05a0ac1.png)
In this screenshot, we add "What's up?" to our message.

The `HandleRequest` method is again called, and the URI parameter is `http://localhost:4000/add-message?s=What%27s%20up?`.

`getQuery` is called, which outputs the part after the `/`. Splitting the query by `=`, we get that `parameter[0]` is `"s"` and `parameter[1]` is `"What's up?"`.

Variable `display` is `"Hello!"` before the method. After the method is executed, variable `toAdd` is set to `"\n" + parameter[1]` and `display` is concatenated with `toAdd` to become `"Hello!\nWhat's up?"`.

# Part 2: Buggy Code
The reverseInPlace method is buggy.
## Buggy Testcase
The following test breaks it:
```java
  @Test
  public void testReverseInPlace() {
    int[] input1 = {1,2,3,4};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{4,3,2,1}, input1);
  }
```
It produces the following result:
![image](https://user-images.githubusercontent.com/110417529/214993872-01fdb9b4-6fb8-4cfc-b837-197fde3c1c84.png)

## Nonbuggy Testcase
The following test does not detect the bug:
```java
  @Test
  public void testReverseInPlace() {
    int[] input1 = {2};
    ArrayExamples.reverseInPlace(input1);
    assertArrayEquals(new int[]{2}, input1);
  }
```
It produces the following result:
![image](https://user-images.githubusercontent.com/110417529/214993275-0c9e30d2-c91c-45f5-b1b0-675e460fa60e.png)

## Buggy Code
```java
  static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = arr[arr.length - i - 1];
    }
  }
```
  
  The problem with this code is that it mirrors the array rather than reverse it.
  For example, on the input `[1, 2, 3, 4]`, after the first two iterations, it becomes `[4, 3, 3, 4]`. Then on the last two iterations, it replaces 3 with itself and 4 with itself, as it does not save `1` and `2` after replacing them.
  
  ## Fixed Code
  ```java
    static void reverseInPlace(int[] arr) {
    for(int i = 0; i < arr.length/2; i += 1) {
      int temp = arr[i];
      arr[i] = arr[arr.length - i - 1];
      arr[arr.length - i - 1] = temp;
    }
  }
  ```
  The fix addresses the issue because it stores the old values of the first half in `temp` and replaces the corresponding second half with `temp`. It only needs to go up to `arr.length/2` as it replaces two elements at a time, so it does not need to look through the whole array to alter every value.
  
  # Part 3: Something New
  I learned JUnit syntax from lab. I learned how to use `assertEquals` and `assertArrayEquals` from CSE15L.
  
  I also learned markdown, URLHandler, and how to use Github Desktop to clone repositories.
  

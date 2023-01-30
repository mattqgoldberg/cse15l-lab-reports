# Part 1

## StringServer.java
![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/SERVER.png?raw=true)

The code in this file uses the Server.java file from the wavelet repository and is similar to the server classes written in lab.
The handleRequest method checks to see if the path of add-message is in the url, and if it does adds any message written after the
'=' in the query to the String with a newline. This string is always what the handleRequest method returns.

![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/string1.png?raw=true)

When this url is entered, the handleRequest method is called with the URI argument of the url that was typed.
This then checks to see if the path of the url contains "add-message", which it does.
It also checks if the query argument is "s", then the value of the String s is changed to add on the end of the query the "hello" after the "=".
This String s is returned by the method and displayed on the screen.

![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/string2.png?raw=true)

In the second screen shot you will notice that what is displayed does not change and "world" is not added.
The handleRequest method checks to see if the path contains "add-message", which it does, but there is no query argument of "s",
because the url contains "?string=hello" instead of "?s=hello" so "hello" is not added to the string and is not shown.

# Part 2

## Function to be tested:
```
static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```
  
## Test passes:
```
  @Test
  public void testReversedEmpty() {
    int[] input = {};
    assertArrayEquals(new int[]{}, ArrayExamples.reversed(input));
  }
```
  
## Test fails:
```
  @Test 
  public void testReversedList() {
    int[] input = {1, 4, 7, 1};
    assertArrayEquals(new int[]{1, 7, 4, 1}, ArrayExamples.reversed(input));
  }
```
  
![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/jUnit.png?raw=true)

## Before:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      arr[i] = newArray[arr.length - i - 1];
    }
    return arr;
  }
```

## After:
```
  static int[] reversed(int[] arr) {
    int[] newArray = new int[arr.length];
    for(int i = 0; i < arr.length; i += 1) {
      newArray[i] = arr[arr.length - i - 1];
    }
    return newArray;
  }
```

The original code was creating a new array and setting elements from the original array equal to original array arr, then returning arr.
This does not work because newArray is empty when created so nothing will be added to the array. This explains why the testReversedEmpty() passed initially because
the bug will return an empty array which in that test case is the correct output.

To fix this, we just need to swap newArray and arr inside the for loop, so that the elements of the original array arr are added to newArray instead of the other way around.
Then we change the return statement to return newArray and the function works as intended and passes the testReversedList() case.


# Part 3

I think that the most interesting thing that I learned was about ports. When we created our web servers and ran them on ieng6 remotely, an error would occur because all the students were trying to use port 4000 at first. So, I learned that on the same machine, you cannot use the same port for multiple things and need to change to a different port number in order for it to work.

# Part 1

## StringServer.java
![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/SERVER.png)

The code in this file uses the Server.java file from the wavelet repository and is similar to the server classes written in lab.
The handleRequest method checks to see if the path of add-message is in the url, and if it does adds any message written after the
'=' in the query to the String with a newline. This string is always what the handleRequest method returns.

![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/String1.png)

When this url is entered, the handleRequest method is called with the URI argument of the url that was typed.
This then checks to see if the path of the url contains "add-message", which it does.
It also checks if the query argument is "s", then the value of the String s is changed to add on the end of the query the "hello" after the "=".
This String s is returned by the method and displayed on the screen.

![Image](https://github.com/mattqgoldberg/cse15l-lab-reports/blob/main/img/Report%202/String2.png)

In the second screen shot you will notice that what is displayed does not change and "world" is not added.
The handleRequest method checks to see if the path contains "add-message", which it does, but there is no query argument of "s",
because the url contains "?string=hello" instead of "?s=hello" so "hello" is not added to the string and is not shown.

# Part 2




# Part 3

I think that the most interesting thing that I learned was about ports. When we created our web servers and ran them on ieng6 remotely, an error would occur because all the students were trying to use port 4000 at first. So, I learned that on the same machine, you cannot use the same port for multiple things and need to change to a different port number in order for it to work.

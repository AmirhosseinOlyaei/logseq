- Quiz 1: FizzBuzz
-
- Exercise
  >1. Write a program in Jsitor that uses console.log to print all the numbers from 1 to 100, with two exceptions. For numbers divisible by 3, print "Fizz" instead of the number, and for numbers divisible by 5 (and not 3), print "Buzz" instead.  
  
  >2. When you have that working, in a new Jsitor, modify your program to print "FizzBuzz" for numbers that are divisible by both 3 and 5 (and still print "Fizz" or "Buzz" for numbers divisible by only one of those)  
  <br>
- Prerequisite reading
	- [Eloquent Javascript, Chapter 2](https://raw.githubusercontent.com/msimbo/student-hub-old/main/resources/Eloquent%20Javascript%20A%20Modern_Introduction%20to%20Programming.pdf)
- How to Submit Your Work
	- Submit the following to the appropriate section on Moodle
		- Your working Jsitor link for exercise 1
- Another working Jsitor link for exercise 2
-
- ```js
  for (let i = 1; i <= 100; i++) {
    if (i % 3 === 0 && i % 5 === 0) {
      console.log("FizzBuzz");
    } else if (i % 3 === 0) {
      console.log("Fizz");
    } else if (i % 5 === 0) {
      console.log("Buzz");
    } else {
      console.log(i);
    }
  }
  ```
  https://jsitor.com/xTdws4lx-h  
  <br>
  ```js
  for (let i = 1; i <= 100; i++) {
    if (i % 3 === 0) {
      console.log("Fizz");
    } else if (i % 5 === 0) {
      console.log("Buzz");
    } else {
      console.log(i);
    }
  }
  ```
  https://jsitor.com/VuESvg9EBx
## For Loops
Loops can be a helpful tool if you want to run the same code over and over again. For example, loops can be used to keep track of a counter when using a timer or stopwatch. Notice the timer counts down toward zero, while the stopwatch counts up away from zero. Loops can be used for a variety of functions, and are commonly used to filter through an array. This tutorial will only cover the basics of a JavaScript _for-loop_.
```JavaScript
for (var i = 0; i < 10; i++){
  //do something...
}
```

### Prerequisites
An understanding of some JavaScript basics is recommended:
* Variables
* Operators
* Reserved words
* Writing output to the console


### Objectives
By the end of this training you will be able to:
* Identify the basic components of a for-loop
* Reproduce a series of for-loops that vary in complexity


### Basic Components of a for loop.
A for loop is composed of three statements. Each of these statements has a specific purpose, and is essential to determining how the for loop will function:

1. Sets the index.
    ```JavaScript
    var i = 0;
    ```
2. Checks the condition
    ```JavaScript
    i < 10;
    ```
3. Updates the index
    ```JavaScript
    i++;
    ```

### How to create a for loop
First type the reserved word _for_, followed by an opening & closing set of parentheses and curly braces.
```JavaScript
for(){

}
```
The parentheses must contain two semicolons. The semicolons are usually used to separate the three _for-loop_ statements.
```JavaScript
for(;;){

}
```

The first statement placed in parentheses initializes a variable and sets the index. This variable is used to track the progress of the loop. This first statement is optional. If the variable is initialized prior to the for-loop, it’s not required within the parentheses.

```JavaScript
//common version
for(var i = 0;;){
  //do something...
}
```

```JavaScript
//optional version
var i = 0

for(;;){
  //do something...
}
```

The second statement checks the condition. It is similar to a _while loop_; which uses a test expression to check whether the counter has reached a defined boundary. If the statement returns _true_, the loop will repeat. But, once that boundary has been reached, the condition will return _false_, and the loop will end. This statement is also optional, if omitted a _break_ is required inside the loop, otherwise, it won’t end.
```JavaScript
//common version
for(var i = 0; i < 10;){
  //do something...
}
```

```JavaScript
//optional version
for(var i = 0;;){
  //do something...

  break;
}
```

The third statement is used to update the index (i.e. the variable), by either incrementing or decrementing its value. This statement executes after each iteration of the loop. Statement 3 is also optional, and if omitted from parentheses, it must be placed inside the loop. Note, this value can be changed through addition, subtraction, multiplication, or division. This loop will run while _i_ is less than 10.
```JavaScript
//common version
for(var i = 0; i < 10; i++){
  //do something...
}
```

```JavaScript
//optional version
for(var i = 0; i < 10;){
  //do something...

  i++;
}
```

### How to write a program using a for loop
Once the basics are understood, the process of building loops is simple. Marijn Haverbeke demonstrates a building block approach by starting with a simplified for loop that grows in complexity as the problem progresses [(Haverbeke, 2014)](#citations). This problem has been parsed so that it can be worked on in smaller chunks.

1. _Write a program that uses console.log to print all the numbers from 1 to 100._
    ```JavaScript
    for(var i = 1; i <= 100; i++) {
    	console.log(i);
    }
    ```
    * Notice variable _i_ is set to 1, the condition will return _true_ while _i_ is less than or equal to 100. Each time the _for-loop_ ends, _i_ will increase by 1. It’s important to note this isn’t the only solution, but it’s an eloquent option.

2. _For numbers divisible by 3, print "Fizz"._

    ```JavaScript
    for(var i = 1; i <= 100; i++) {
    	var word = “”;
    	if (i %3 == 0){
        word = "Fizz";
      } else {
         word = i;
      }
      console.log(word);
    }
    ```
    * The variable _word_ is initialized at the start of the _for-loop_, and set to an empty string. The modulo operator determines if _i_ is divisible by 3. If it is: it will have a remainder of 0, the condition will return _true_, and _word_ will be set _Fizz_. Otherwise, it will return _false_, move to the next _else_ statement, and _word_ will be set to the value of _i_.

    * Table 1.1 will help illustrate the outcome for each iteration: when _i_ equals 1, _word_ equals 1; when _i_ equals 2, _word_ equals 2; when _i_ equals 3, _word_ equals _Fizz_; etc.

    |_i_ =   |1|2|3     |
    |--------|-|-|------|
    |_word_ =|1|2|_Fizz_|

3. _For numbers divisible by 5 (and not 3), print "Buzz"._

    ```JavaScript
    for(var i = 1; i <= 100; i++) {
    	var word = "";
    	if (i %3 == 0){
        word += "Fizz";
      } else if (i % 5 == 0) {
    		word += "Buzz";
    	} else {
         word = i;
      }
      console.log(word);
    }
    ```
    * A new _else if_ conditional statement has been introduced. This modulo operator determines if _i_ is divisible by 5. If it is: it will have a remainder of 0, the condition will return _true_, and _word_ will be set to _Buzz_.

    * Table 1.2 will illustrate this set of iterations. Starting with _i_ set equal to 4. _word_ is initialized as an empty string. Since 4 is not divisible by 3, or 5, the loop skips to the last statement, which assigns _word_ to equal 4. Next, _console.log()_ will print the value of _word_, and _i_ will increment by 1 at the end of the loop.

    * This time _i_ equals 5, and _word_ is initialized as an empty string. 5 is not divisible by 3, but 5 is divisible by 5. When the loop reaches the second statement, the condition returns _true_, and _word_ is set to _Buzz_.  The loop will skip over the final _else_ statement, print the value of _word_ to the console, increment _i_ by 1, and the pattern continues.

    |_i_ =   |1|2|3     |4|5     |
    |--------|-|-|------|-|------|
    |_word_ =|1|2|_Fizz_|4|_Buzz_|

4. _Modify your program to print "FizzBuzz" for numbers that are divisible by both 3 and 5.
    ```JavaScript
    for(var i = 1; i <= 100; i++) {
    	var word = "";
    	if (i % 3 == 0){
        word += "Fizz";
      }
    	if (i % 5 == 0) {
    		word += "Buzz";
    	}
      console.log(word || i);
    }
    ```
    * Notice this problem is more complex, but the code is brief compared to the previous examples. What happened? All that’s happened is the excess code has been removed. Let’s take a look at how this code produces an eloquent solution using the number 15.

    * Table 1.3 will illustrate this set of iterations. _word_ is initialized as an empty string. The loop runs into the first _if_ statement. 15 is divisible by 3, so _Fizz_ is concatenated onto _word_. The loop runs into the second _if_statement. 15 is divisible by 5, so _Buzz_ is also concatenated onto _word_. In this case, producing _FizzBuzz_.

    |_i_ =   |1|2|3     |4|5     |...|15        |
    |--------|-|-|------|-|------|---|----------|
    |_word_ =|1|2|_Fizz_|4|_Buzz_|...|_FizzBuzz_|

****
<h3>
<div style="text-align:center; text-decoration:underline">Citations</div>
</h3>

Haverbeke, Marijn. “Eloquent Javascript A Modern Introduction to Programming.” 2014, <a style="color:#0D6EE4" href="http://eloquentjavascript.net/02_program_structure.html">http://eloquentjavascript.net/02_program_structure.html</a>

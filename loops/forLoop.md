## For Loops
Loops can be a helpful tool if you want to run the same code over and over again. For example, loops can be used to keep track of a counter when using a timer or stopwatch. Notice the timer counts down toward zero, while the stopwatch counts up away from zero. Loops can also be used to filter through an array’s index. Loops can be used for a variety of functions. However, this tutorial will only cover the basics of a JavaScript _for-loop_. Here is an example of its basic layout.
```JavaScript
for (var i = 0; i < 10; i++){
  //do something...
}
```

### Objectives
By the end of this training you will understand:
* The basic components of a for loop
* How to write a program using a for loop


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
First type the reserved word _for_, followed by opening & closing set of parentheses and curly braces.
```JavaScript
for(){

}
```
The parentheses must contain two semicolons. The semicolons are usually used to separate the three _for-loop_ statements.
```JavaScript
for(;;){

}
```

The first statement placed in parentheses initializes a variable and sets the index. This variable is used to track the progress of the loop. Furthermore, this first statement is optional in JavaScript. If the variable is initialized with a set value prior to the for-loop, it’s not required within the parentheses. Both of the following first statements are perfectly acceptable:

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

The second statement checks the condition. It is similar to a _while loop_; which uses a test expression to check whether the counter has reached a defined boundary. If the statement returns _<span style="color:#005cc5">true</span>_, the loop will start over again. Once that boundary has been reached, the condition will return _<span style="color:#005cc5">false</span>_, and the loop will end. This statement is also optional, but if omitted, a _<span style="color:#d73a49">break</span>_ is required inside the loop, otherwise, it will never end.
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
true
false


  break
}
```
<!-- Code Block initialize within parentheses-->
<!-- Code Block initials optional at end of loop-->

The third statement is used to update the index (i.e. the variable), by either incrementing or decrementing its value. This statement executes after each iteration of the loop. Statement 3 is also optional, but if omitted from the parentheses, it must be placed inside the loop. Note, this value can be changed through addition, subtraction, multiplication, or division.
<!-- Code Block initialize within parentheses-->
<!-- Code Block initials optional at end of loop-->


### How to write a program using a for loop
Loops can be used to solve almost any problem that is repetitive in nature. Once the basics are understood, the process of building solutions for more complex problems aren’t too far off.

Marijn Haverbeke demonstrates a building block approach by starting with a simplified for loop  that grows in complexity as the problem progresses (Haverbeke, 2014).
<!-- http://eloquentjavascript.net/02_program_structure.html -->

_Write a program that uses console.log to print all the numbers from 1 to 100, with two exceptions. For numbers divisible by 3, print "Fizz" instead of the number, and for numbers divisible by 5 (and not 3), print "Buzz" instead.
When you have that working, modify your program to print "FizzBuzz", for numbers that are divisible by both 3 and 5 (and still print "Fizz" or "Buzz" for numbers divisible by only one of those)._

Logical solutions can be derived by parsing this information into smaller pieces.
_Write a program that uses console.log to print all the numbers from 1 to 100._

```JavaScript
for(var i = 1; i <= 100; i++) {
	console.log(i);
}
```

* Notice variable _i_ is set to the value 1, the condition will return _<span style="color:#005cc5">true</span>_ _while i_ is less than or equal to 100; and each time the _for-loop_ ends _i_ will increase by a value of 1. It’s important to note this isn’t the only solution, but it’s an eloquent option.




_For numbers divisible by 3, print "Fizz"._

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

*There have been a few modifications to the code in this example. Starting with the variable _word_, it is initialized at the start of the _for-loop)_, and set to an empty string. The _if_ condition uses the modulo operator to determine whether _i_ is divisible by the value 3. If it is: it will have a remainder of 0, the condition will return _<span style="color:#005cc5">true</span>_, and _word_ will be set to the string _Fizz_. Otherwise, the if condition will return _<span style="color:#005cc5">false</span>_, the code will skip to the _else_ statement, and _word_ will be set to the value of _i_. Again, this isn’t the only solution, but it’s an eloquent one.

*Table 1.1 will help illustrate the outcome for each iteration: when _i_ is equal to 1, _word_ will equal 1; when _i_ is equal to 2, _word_ will equal 2; when _i_ is equal to 3, _word_ will equal _Fizz_; etc.

<!-- Table 1.1 console log table for values 1 through 3 -->











_For numbers divisible by 5 (and not 3), print "Buzz"._

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

* So now we want to print the word _Buzz_ only if the value is divisible by 5. There have only been couple changes in this code. First, a new _else if_ conditional statement has been introduced. But, it’s similar to the previous condition. This condition uses the modulo operator to determine whether _i_ is divisible by the value 5. If it is: it will have a remainder of 0, the condition will return _<span style="color:#005cc5">true</span>_, and _word_ will be set to the string _Buzz_.

* Table 1.2 will help illustrate the outcome for this next set of iterations. Let’s run through this _for-loop_ continuing where we left off in the previous example; starting with the value 4. The variable _word_ is initialized as an empty string. 4 is not divisible by 3, so the for-loop skips to the next statement. 4 is not divisible by 5, and the for-loop skips to the last statement, which sets _word_ to the value 4. _console.log()_ will print the value for word, and _i_ will increment by 1 at the end of the _for-loop_.

* The next time through the _for-loop_, _i_ is equal to 5.
The variable _word_ is initialized as an empty string. 5 is not divisible by 3, but 5 is not divisible by 5. When the _for-loop_ reaches the second statement, the condition returns _<span style="color:#005cc5">true</span>_, and _word_ is set to the string _Buzz_.  The loop will skip over the final _else_ statement, print _word_ to the console, increment _i_ by 1, and the pattern will continue.

<!-- Table 1.2 console log table show 1 through three but explain starting at value 4 and go to 5-->


_Modify your program to print "FizzBuzz" for numbers that are divisible by both 3 and 5.
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


* So this last part, we want to print the word “FizzBuzz” for numbers that are divisible by both 3 and 5. Notice this problem is more complex, but the code is brief compared to the its previous examples. What happened? Remember, the best code is brief. All that’s happened is the excess load has been removed. Let’s take a look at how this code produces the final solution, by looking at the number 15.

* The variable _word_ is initialized as an empty string. The loop runs into the first _if_ statement. 15 is divisible by 3, so _Fizz_ is concatenated onto _word_. The loop runs into the second _if_statement; which now stands on it’s own. 15 is also divisible by 5, so _Buzz_ is also concatenated onto _word_. In this case, producing the _FizzBuzz_.

<!--Table 1.3 console log table skip to the value 15-->

* The process of building problems in complexity doesn’t have to stop here. Pulse questions can be introduced periodically to further understand a problem and it’s solutions. For example:
** Why was the variable _word_ initialized inside the _for-loop_, rather than before it?
** In the second example, within the _if/else_ blocks,  _word_ was always followed by an equal (=) sign. However, in the third and fourth examples, sometime _word_ was followed by a plus and equal (+=) sign. Please explain this reasoning?



****
<h3><div style="text-align:center;text-decoration:underline">Citations</div></h3>

Haverbeke, Marijn. “Eloquent Javascript A Modern Introduction to Programming.” 2014, <a style="color:#0D6EE4" href="http://eloquentjavascript.net/02_program_structure.html">http://eloquentjavascript.net/02_program_structure.html</a>

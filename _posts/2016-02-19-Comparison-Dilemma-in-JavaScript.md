In real life, you may not encounter such situation however, this article will give you insights on how type conversion and comparisons happen in javascript. 

Let’s start with code

    var a = -1;   
    if(a)   
    console.log("Anything but JS");   
    else   
    console.log("Even assembly will do!");   
**Output** Anything but JS

Reason behind this output is that any NUMBER except 0 is converted to true. Implicit type conversion happened and -1 is converted to true.

Well let’s see the sloppy side of it by another example-

    var a = -1;    
    if(a == true)    
     console.log("There are 2 type of people in this world.");    
    else    
      console.log("1 who hate JS. And 1 who don’t know it!");  
**Output:** “1 who hate JS. And 1 who don’t know it!”

Unexpected, right?

**Explanation**

For understating this, we need to understand that in case of = = (Double equals), implicit type conversion happens when data type of operands are not same. And the variable which will get converted is decided on the basics of ECMA specification algorithm for at- Abstract Equality Comparison Algorithm.

And according to this, in case of number and Boolean comparison, Boolean variable is the one which will get converted.

And irony is that true is always converted to 1, and false is always converted to 0.

So this code will work as expected-

    var a = 1;   
    if(a == true)   
    console.log("This happens when even standards are sloppy.");   
    else   
    console.log("Now we know the output");   
**Output:**
This happens when even standards are sloppy. 

The message to take away from here is to keep that algorithm in mind while comparing two different data type values or use explicit conversion.

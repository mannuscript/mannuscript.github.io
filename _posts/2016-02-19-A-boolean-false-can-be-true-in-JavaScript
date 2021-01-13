JavaScript has bad reputation for its sloppiness,anything can happen in javascript. Lets see such an example.

**What is boolean ?**

Boolean() is a constructor function in javascript which can be used to make a boolean data type variable. It can be used either for making boolean data type variable or a boolean object depending upon the usage.

**How a boolean false instance can behave like it is true?**

Lets understand it by an example-

    var abc = new Boolean(false); //a boolean false is created
    //now lets see if its value is false or not  
    if(abc) {  
     console.log('JS is for SuperHumans!');  
    } else {
    console.log('javascript is cool!');
    }

**Output** - JS is for SuperHumans!

Confused? Lets take another example-

    var efg  = Boolean(false);  
  
    if(efg) {  
    console.log("Have you started thinking JS is cool?");
    } else  { 
    console.log("This cant be the output!");
    }
  
**Output** – This cant be the output!

Confused more? Good, because javascript is for superhumans!

**Explanation-**

When we use “new” keyword with any constructor in javascript (be it Number(),String() or any other) then a complex object is made instead of primitive value.

While creating an instance without using new keyword creates a primitive value.

While a complex object irrespective of the values of its properties(or even if it does not have any property) is truthy.

We can understand this by taking an example -

    var hij = new Boolean(false);  
    var klm = Boolean(false);  
    console.log(typeof hij);  
    console.log(typeof klm);  
**output -**
object

boolean
This holds not only for boolean but for every constructor except Object() itself.

So the lesson to learn here is never use “new” keyword while creating a primitive variable because it can cause trouble while using typeof operator or in case shown above.

Use either the constructor or true/false keywords itself. Like-

    var nop = true; //it also uses the constructor without new keyword behind the scenes. 
 Well this is JavaScript one of the most sloppy language, accept this kind of behavior from it.

And stay tuned till I reveal more sloppiness of javaScript!

Two ways of defining empty arrays with number of elements specified
    
    var arr1 = new Array(3);  
    var arr2 = [,,]; 
But new keyword for array definition is never recommended.

Now Suppose I have 3 text fields ,whose data I want to store in an array.

    var arr = [,,];  
    for(var i=0; i< arr.length ;i++) {  
    arr[i] = document.getElementById('mytextblock'+i).value;  
    }  
Lets see what is wrong with the code above

    arr.forEach(function(data){  
     console.log(data);  
    });  
//logs only 2 values instead of three.  
**Why?**

When we initialize an empty array using this notion
`var arr = [,,];  `

It initializes array with the number of elements equal to the number of comma used inside square brackets []. So in above case, length of the array will be 2 instead of 3.

    var arr1 = [,,];  
    var arr2 = [,,,];  
    console.log(arr1.length); //logs 2  
    console.log(arr2.length); //logs 3  
And in the above example, as we made use of length property to iterate the array it loops for 2 times instead of 3.

**Solution**

Well, arrays are dynamic in javascript , they can grow and shrink according to our requirement. So there is no point of defining its length at initialization. And even if we do so,then we should avoid using the length property of the array.

So above code could be written as
    
    var arr = [];  
    var i;  
    for(i=0;document.getElementById('mytextblock'+i);i++){  
    arr[i] = document.getElementById('mytextblock'+i).value;  
    }  
**Conclusion**

Knowledge is the power, And if we are not familiarized with such sloppiness of javascript, we may find ourself in situations of dead confusion.

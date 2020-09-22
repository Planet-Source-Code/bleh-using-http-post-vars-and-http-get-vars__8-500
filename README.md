<div align="center">

## Using $HTTP\_POST\_VARS and $HTTP\_GET\_VARS


</div>

### Description

This describes how to use while(), list() and each() in conjunction with the predefined PHP variables $HTTP_POST_VARS and $HTTP_GET_VARS to read information passed to a page without knowing the variable names, or how many variables were passed.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[bleh](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/bleh.md)
**Level**          |Beginner
**User Rating**    |4.6 (55 globes from 12 users)
**Compatibility**  |PHP 3\.0, PHP 4\.0
**Category**       |[Internet/ Browsers/ HTML](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/internet-browsers-html__8-9.md)
**World**          |[PHP](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/php.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/bleh-using-http-post-vars-and-http-get-vars__8-500/archive/master.zip)





### Source Code

<font face="Verdana" size="2">
<div align="center"><b>Looping Through $HTTP_GET_VARS and $HTTP_POST_VARS</b></div>
<p>
<b>Quick Associative Array Overview</b>
</p>
<p>First off, to understand how to use these variables, you must understand what an associative array is. If you already know, then you can skip this part.</p>
<p>An associative array is simply an array who's key is not a number (i.e. $myArray[0], $myArray[1], etc.) but a word, as it were. For instance, if I have an associative array named "$myAssoc" who's values are the persons last name, and the keys are their first names, then it would look like this.<br><br>
<font color="green">$myAssoc["charles"] = "chadwick";</font> <br>
where "charles" is the key (like 0, 1, etc) and "chadwick" is the value. </p>
<p>
If you want a better explanation of this, I suggest reading the associative array information in the PHP manual found at www.php.net.</p>
<b>Reading Variables Passed Through GET and POST</b>
<p>For this example, I am going to use a standard while() loop to help us traverse through the associative array and read both it's keys and values. This will, as I am sure you are aware, execute until such time as there are no more keys to be read. So our first bit of code will use not only the while() statement, but two others, list() and each(). List() is used to assign a list of variables specified values in one operation. The each() function will pull a key and a value out of an array, and then advance the pointer to the next element in the array. So the first part of the code will look like so.</p>
<p><font color="green">
while(list($key, $value) = each($HTTP_GET_VARS))
</font></p>
<p>This code is basically using the list function to assign information to our $key and $value variables, which is coming from the each() function. Then all we need to do is echo this information out to our page.</p>
<p><font color="green">
while(list($key, $value) = each($HTTP_GET_VARS)) <br>
{ <br>
	echo "$key = $value(br)"; <br>
} <br>
</font><br>
<font size="1">
<b>NOTE:</b> At the end of my echo statement, I have put parens () around my HTML line break because it won't display on this page otherwise. If you are using this code on a site, make sure to replace the parens with actual HTML opening and closing brackets. Also note that both the equal sign and the HTML line break are NOT necassary in this code.
</font>
</p>
<p>
Let's say that our url is this: <br><br>
<font color="green">
www.myhomepage.com/test.php?var1=one&var2=two&var3=three&var4=four
</font>
</p>
<p>
This is the GET method. Our variables are "var1", "var2", "var3", and "var4". Their respective values in this example are "one", "two", "three", and "four". If we pass this along to a page that has our code on it, then the output would be like so:
</p>
<p>
var1 = one<br>
var2 = two<br>
var3 = three<br>
var4 = four<br>
</p>
<p>
If we are using the POST method, with the same variables, we would have the same output. However, you would need to use the $HTTP_POST_VARS variable. </p>
<p>
<font size="1">
<b>NOTE:</b> If you are using these, or any other predefined PHP variables in a function, you must declare them as global inside the function or this won't work. </font>
<p>That's it. This is pretty much beginner information, but I went for a while without realizing that this could be done, and it caused me to spend a lot more time coding than need be.</p></font>


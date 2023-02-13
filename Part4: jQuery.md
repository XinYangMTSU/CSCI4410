# CSCI 330 Fall 2021
# Part 4: jQuery


# Why Study jQuery ?
+ jQuery is a library to the JavaScript programming language.
+ Learning jQuery is the fastest and easiest way to add interactivity and animation to your website.
+ Not only is it a great way to get introduced to the what JavaScript can help you accomplish,
+ but this lightweight library will also let you leverage the HTML and CSS skills you’ve already learned.

# jQuery Get Started
+ Adding jQuery to your web pages.
+ jQuery CDN.
  - you can include it from a CDN (Content Delivery Network).
  - To use jQuery from Google:
  
~~~~
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
</head>
~~~~
  - To use jQuery from Microsoft:
~~~~
<head>
<script src="https://ajax.aspnetcdn.com/ajax/jQuery/jquery-3.5.1.min.js"></script>
</head>
~~~~
  - One big advantage of using the hosted jQuery from Google or Microsoft:

    + Many users already have downloaded jQuery from Google or Microsoft when visiting another site. As a result, it will be loaded from cache when they visit your site, which leads to faster loading time. Also, most CDN's will make sure that once a user requests a file from it, it will be served from the server closest to them, which also leads to faster loading time.

# The Document Object Model
+ To get the most out of jQuery, we should review how an HTML page is put together.
+ An HTML document is structured according to the [**Document Object Model**](https://en.wikipedia.org/wiki/Document_Object_Model), or **DOM**.
+ It’s by interacting with the **DOM** that jQuery is able to access and modify HTML.

# The Document Nodes
In the HTML **DOM** (Document Object Model), everything is a **node**:
+ The document itself is a **document node**.   
+ All HTML elements are **element nodes**.
+ All HTML attributes are **attribute nodes**.   
+ Comments are **comment nodes.**

# The Document Object
+ When an HTML document is loaded into a web browser, it becomes a **document object**.
+ The document object is the **root node** of the HTML document and the “owner” of all other nodes.
+ The document object provides **properties** and **methods** to access all node objects, from within JavaScript.

# $(document).ready()
We’ll start our jQuery magic using the $(document).ready():
+ **$()** says, “We are going to use jQuery !”.
+ Putting **document** between the parentheses tells us that we’re about to work our magic on the **HTML document** itself.
+ **.ready()** is a **function**, or basic action, in jQuery. It tells us jQuery is going to do stuff as soon as the HTML document is ready.
+ Whatever goes in <b>.ready()</b>’s parentheses is the jQuery **event** that occurs as soon as the HTML is ready.
+ **$(document).ready(something)** says “when the HTML document is ready, do something!”.
+ Note that **.ready();** ends with a **semicolon**.
+ This tells jQuery that you’re done giving it a command.

# The functional approach
+ Now we need to put something inside our **ready()** function.
+ Functions are the basic unit of doing work in jQuery.
+ For this reason, jQuery includes a **function** keyword. The syntax looks like this:

~~~~
$(document).ready(function(){

  // jQuery methods go here...

});
~~~~

+ **$(document)** is a jQuery object. The **$()** is actually a function in disguise; it turns the document into a jQuery object.

+ **functions()** is the action that **.ready()** will perform as soon as the HTML document is loaded.

+ Now we just need to include an action in the body of our function.
+ We’ll turn our target element into a jQuery object so jQuery can manipulate it.
+ Let’s include our **function** keyword and two new actions together, **mouseenter()** and **hide()**.

## mouseenter() and hide()
+ **mouseenter()** does what you might expect: it produces a change when your mouse enters a given HTML element. For example:
~~~~
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script >
        
        $(document).ready(function(){
            $('h1').mouseenter(
                    function(){
                        $('h1').hide();
                    }
                )
        })

    </script>
~~~~
+ This example would hide every `<h1>` on the page as soon as you mouse over one.
  
+ Instead of hide(), however, we’ll place fadeTo() inside mouseenter().
+ fadeTo() takes three arguments, or inputs, between its parentheses, separated by a comma:

|argument|explanation|values|
|----|----|----|
|speed|the duration of the effect|"slow", "fast", or milliseconds.|
|opacity|fading to a given opacity|value between 0 and 1|
|callback|a function to be executed after the function completes||

~~~~
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script >
        
        $(document).ready(function(){
        
            $('h1').mouseenter(
                    function(){
                        $('h1').fadeTo("fast",0.2);
                    }
                )
                
              
        })

    </script>
~~~~

## mouseleave() and fadeTo()
~~~~
<script >
        
         $(document).ready(function(){
        
            $('h1').mouseenter(
                    function(){
                        $('h1').fadeTo("fast",0.5);
                    }
                )
                
            $('h1').mouseleave(
                    function(){
                        $('h1').fadeTo("fast",1);
                    }
                ) 
        })

    </script>
~~~~~

## click() and fadeOut()

+ fadeOut() syntax
~~~~
$(selector).fadeOut(speed,callback);
~~~~

~~~~
      <script >
        
         $(document).ready(function(){
        
            $('h1').click(
                    function(){
                        $('h1').fadeOut("slow");
                    }
                )
           
        })

    </script>
    
~~~~



# Variables

~~~~
var i = 0;
var name = "Ning";
var flag = true;


var $p = $("p");
~~~~
+ Variable **$p** stores the result of a jQuery selector **$("p")**.
+ This is just a handy way to save this information for later.


# Selecting by Class
+ We don’t have to limit ourselves to selecting HTML elements like `<p>` and `<div>`.
+ Essentially, we can put any CSS selector in quotes and pass it into **$()**. This means we can select classes, too!  

~~~~
<!DOCTYPE html>
<html>
<head>
    <title>jQuery</title>
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script > 
         $(document).ready(function(){
        
            $("button").click(
                    function(){
                        $('.vanish').fadeOut("slow");
                    }
                )
           
        })
    </script>
</head>
<body>
    <button>Click</button>
    <h1 class="vanish">This is a h1.</h1>
    <h1>This is another h1.</h1>
    <h2 class = "vanish">This is a h2.</h2>
</body>
</html>
~~~~

# Selecting by ID
+ If we can select by class, it follows that we can also select by ID.
+ We do this by putting the ID name (in quotes) inside **$()**. Just as we need the **. for classes**, we need the **# for IDs**.

~~~~
<!DOCTYPE html>
<html>
<head>
    <title>jQuery</title>
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script > 
         $(document).ready(function(){
        
            $("button").click(
                    function(){
                        $('#h1_1').fadeOut("slow");
                    }
                )
           
        })
    </script>
</head>
<body>
    <button>Click</button>
    <h1 id="h1_1">This is a h1.</h1>
    <h1 id="h1_2">This is another h1.</h1>
    <h2>This is a h2.</h2>
</body>
</html>
~~~~


# Compound selector
+ Anything you can target with CSS, you can modify with jQuery.
+ We can apply a fadeTo() to multiple selectors like this:
~~~~
<!DOCTYPE html>
<html>
<head>
    <title>jQuery</title>
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script > 
         $(document).ready(function(){
        
            $("button").click(
                    function(){
                        $('#h1_1, .h2').fadeOut("slow");
                    }
                )
           
        })
    </script>
</head>
<body>
    <button>Click</button>
    <h1 id="h1_1">This is a h1.</h1>
    <h1 id="h1_2">This is another h1.</h1>
    <h2 class="h2">This is a h2.</h2>
</body>
</html>
~~~~

# `this` is Important!
~~~~
      <script > 
         $(document).ready(function(){
            $("h1").click(
                    function(){
                        $('h1').hide();
                    }
                )        
        })
    </script>
~~~~
+ In this example, **$("h1").hide()** won’t just hide the **h1** you mouse into; it will hide **all the h1s**.
+ How can we tell jQuery we only want to affect **this** particular element?
+ **this**, of course!
+ The **this** keyword refers to the jQuery object you’re currently doing something with.
+ If you use an event handler on **$(this)**, the event will only affect the element you’re currently doing something with.
~~~~
<!DOCTYPE html>
<html>
<head>
    <title>jQuery</title>
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script > 
         $(document).ready(function(){
            $("h1").click(
                    function(){
                        $(this).hide();
                    }
                )        
        })
    </script>
</head>
<body>
    <button>Click</button>
    <h1>This is a h1.</h1>
    <h1>This is another h1.</h1>
    <h2>This is a h2.</h2>
</body>
</html>
~~~~

# Toggling Your Panel: .slideToggle()
+ The slideToggle() method toggles between slideUp() and slideDown() for the selected elements.
+ This method checks the selected elements for visibility. slideDown() is run if an element is hidden. slideUp() is run if an element is visible - This creates a toggle effect
+ syntax:
  - speed
  - easing
    + "swing": moves slower at the beginning/end, but faster in the middle
    + "linear": moves in a constant speed
  - callback

~~~~~
$(selector).slideToggle(speed,easing,callback)
~~~~~

 


~~~~~
<!DOCTYPE html>
<html>
<head>
    <title>jQuery</title>
    
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
      <script > 
         $(document).ready(function(){
            $("button").click(
                    function(){
                        $("h1").slideToggle(1000);
                    }
                )        
        })
    </script>
</head>
<body>
    <button>Click</button>
    <h1>This is a h1.</h1>
    <h1>This is another h1.</h1>
    <h2>This is a h2.</h2>
</body>
</html>
~~~~~


# Adding and Removing Elements
+ Dynamically adding elements to our HTML page is a powerful tool.
+ It lets us modify not only the formatting, but the actual structure of our websites in response to a user’s actions.

## Inserting Elements
+ We can insert our newly created elements using a few jQuery actions:
  - **.append()** inserts the specified element as the last child of the target element.
  - **.prepend()** inserts the specified element as the first child of the target element.
  - **.after()** inserts the specified element after the target element.
  - **.before()** inserts the specified element before the target element.
  
~~~~
  <!DOCTYPE html>
  <html>

  <head>
    <title>jQuery</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script>
    $(document).ready(function() {
        $("#btn1").click(function() {
            $("p").append(" <b>Appended text</b>.");
        });

        $("#btn2").click(function() {
            $("ol").append("<li>Appended item</li>");
        });
    });
    </script>
  </head>

  <body>
    <p>This is a paragraph.</p>
    <p>This is another paragraph.</p>
    <ol>
        <li>List item 1</li>
        <li>List item 2</li>
        <li>List item 3</li>
    </ol>
    <button id="btn1">Append text</button>
    <button id="btn2">Append list items</button>
  </body>

  </html>
~~~~



## Moving Elements Around
+ All we need to do is use the jQuery functions we just learned on existing elements instead of creating new ones.

~~~~
  <!DOCTYPE html>
  <html>

  <head>
    <title>jQuery</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script>
    $(document).ready(function() {
        $("#btn1").click(function() {
            $("#p2").after(" <p>Appended paragraph</p>.");
        });

        $("#btn2").click(function() {
            $("#p2").after($("#p1"));
        });
    });
    </script>
  </head>

  <body>
    <p id="p1">This is a paragraph.</p>
    <p id="p2">This is another paragraph.</p>
    
    <button id="btn1">Append</button>
    <button id="btn2">Move</button>
  </body>

  </html>
  ~~~~
  
  ## Removing Elements Around
  
 + We have two jQuery functions, **.empty()** and **.remove()**, that help us delete content from our pages.
  - **.empty()** Removes the child elements from the selected element.
  - **.remove()**, Removes the selected element (and its child elements).
  
 ~~~~
   <!DOCTYPE html>
  <html>

  <head>
    <title>jQuery</title>
    <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
    <script>
    $(document).ready(function() {
        $("#btn1").click(function() {
            $("#div1").empty();
        });

        $("#btn2").click(function() {
            $("#div2").remove();
        });
    });
    </script>
  </head>

  <body>  
  	<div id="div1" style="background-color: red">
  		<p>This is a paragraph.</p>
    	<p>This is another paragraph.</p>
  	</div>
    
    <div id="div2" style="background-color: green">
  		<p>This is a paragraph.</p>
    	<p>This is another paragraph.</p>
  	</div>
    
    <button id="btn1">empty</button>
    <button id="btn2">remove</button>
  </body>

  </html>
  ~~~~


# We don’t have to limit ourselves to adding or removing entire elements.
+ jQuery includes two functions, **.addClass()** and **.removeClass()**, that can be used to add or remove a class from an element. The syntax looks like this:

~~~~
$('selector').addClass('className');
$('selector').removeClass('className');
~~~~

## .addClass()

~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#h1").addClass("blue");
    $("div").addClass("important");
  });
});
</script>
<style>
.important {
  font-weight: bold;
  font-size: xx-large;
}

.blue {
  color: blue;
}
</style>
</head>
<body>

<h1 id="h1">Heading 1</h1>
<h2>Heading 2</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<div>This is some important text!</div><br>

<button>Add classes to elements</button>
</body>
</html>
~~~~

## .removeClass()
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#h1").removeClass("blue");
    $("div").removeClass("important");
  });
});
</script>
<style>
.important {
  font-weight: bold;
  font-size: xx-large;
}

.blue {
  color: blue;
}
</style>
</head>
<body>

<h1 id="h1" class="blue">Heading 1</h1>
<h2>Heading 2</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<div class="important">This is some important text!</div><br>

<button>Remove classes from elements</button>
</body>
</html>
~~~~

## Toggling Classes
+ The **.toggleClass()** method toggles between adding and removing one or more class names from the selected elements.
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#h1").toggleClass("blue");
    $("div").toggleClass("important");
  });
});
</script>
<style>
.important {
  font-weight: bold;
  font-size: xx-large;
}

.blue {
  color: blue;
}
</style>
</head>
<body>

<h1 id="h1" class="blue">Heading 1</h1>
<h2>Heading 2</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<div class="important">This is some important text!</div><br>

<button>Toggle classes from elements</button>
</body>
</html>
~~~~

# Changing Your style: CSS
+ jQuery also includes a general-purpose **.css()** function that takes two inputs: 
  - the first is the CSS element property to alter,
  - the second is the value to set it to. 
  
  ~~~~
  css("propertyname","value")
  ~~~~
  
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#h1").css("color","blue");
  });
});
</script>


</head>
<body>

<h1 id="h1">Heading 1</h1>
<h2>Heading 2</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<div>This is some important text!</div><br>

<button>general css() method</button>
</body>
</html>
~~~~


# Modifying HTML Elements
## content
+ We can update the contents of our HTML elements by using **.html()**.

~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    $("#h1").html("a new heading 1");
  });
});
</script>


</head>
<body>

<h1 id="h1">Heading 1</h1>
<h2>Heading 2</h2>

<p>This is a paragraph.</p>
<p>This is another paragraph.</p>

<div>This is some important text!</div><br>

<button>html() method</button>
</body>
</html>
~~~~
## attribute 
+ get attribute value by **.attr(attributeName)**
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
	var rv = $("button").attr("id");
	console.log(rv);
});
</script>


</head>
<body>
<button id="btn1">animation</button>
</body>
</html>
~~~~
+ set attribute value by **.attr(attributeName, value)**
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
	$("button").attr("id","btn2");
	var rv = $("button").attr("id");
	console.log(rv);
});
</script>


</head>
<body>
<button id="btn1">animation</button>
</body>
</html>
~~~~

# HTML Forms
+ [Reference](https://www.w3schools.com/html/html_forms.asp)
+ The HTML `<form>` element defines a form that is used to collect user input.
+ An HTML form contains form elements.
+ The **<input>** element can be displayed in several ways, depending on the type attribute.

|Type|Description|
|----|----|
|`<input type = "text">`|Define a one-line text input|
|`<input type = "radio">`|Define a radio button(for selecting one of many choices)|
|`<input type = "submit">`|Define a submit button(for submitting the form)|

See more types [here](https://www.w3schools.com/html/html_form_input_types.asp).

~~~~
<body>

<form>
	First Name: <br>
	<input type="text" name="firstname"> <br>
	Last Name: <br>
	<input type="text" name="lastname"> <br>
</form>

<button>Add name</button>
</body>
~~~~

# store the user’s input: .val()
+ We’ll need to store the user’s input in a variable, which will allow us to append that input to the body of the HTML document later on.
+ You can set a variable equal to the contents of the input field using `.val()`
+ Get the value from an input: `var first_name = $("input[name=firstname]").val()` or `var last_name = $("#lastname").val()`

~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
    var first_name = $("input[name=firstname]").val()
    var last_name = $("#lastname").val()

    console.log(first_name);
    console.log(last_name);
  });
});
</script>


</head>
<body>

<form>
	First Name: <br>
	<input type="text" name="firstname"> <br>
	Last Name: <br>
	<input type="text" id="lastname"> <br>
</form>

<button>Add name</button>
</body>
</html>
~~~~

# Append to body

~~~~
<script>
$(document).ready(function(){
  $("button").click(function(){
    var first_name = $("input[name=firstname]").val()
    var last_name = $("input[name=lastname]").val()

    console.log(first_name);
    console.log(last_name);

    $('body').append("<p>"+first_name+ " "+ last_name + "</p>");
  });
});
</script>
~~~~


# general event handlers .on()
+ We need a new event handler: `.on()`. You can think of `.on()` as a general handler that takes the `event`, its `selector`, and an `action` as inputs.

~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $(document).on(
  	"click",
  	"h1",
  	function(){
  		$(this).remove();
  	}

  	);


  	$("ol").on(
  	"click",
  	"li",
  	function(){
  		$(this).remove();
  	}

  	);
});
</script>


</head>
<body>
<ol>
	<li>item 1</li>
	<li>item 2</li>
	<li>item 3</li>
</ol>
<h1>This is heading 1</h1>
<p>This is a paragraph</p>


</body>
</html>
~~~~




# other events
+ **.on()**
+ **.hover()**
~~~~
$(selector).hover(inFunction,outFunction)
~~~~


+ **.dblclick()**
+ **.keydown()**
  - find the key you press down
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $(document).keydown(
  	function(event){
  		console.log(event.which);
  	}

  	);

});
</script>


</head>
<body>

</body>
</html>
~~~~


+ **.animate()**
  - The .animate() effect takes two inputs: the animation to perform, and the time in which to perform the animation.
  - set absolute value
~~~~
<!DOCTYPE html>
<html>
<head>
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.5.1/jquery.min.js"></script>
<script>
$(document).ready(function(){
  $("button").click(function(){
  $("div").animate({
    right: "100px",
  });
}); 

});
</script>


</head>
<body>
<button>animation</button>
<div id="div1" style=" height:100px; width:100px; position:absolute">
	<img src="sau.jpg" style="height: 100px; width: 100px">
  	</div>


</body>
</html>
~~~~
  - set multiple values
~~~~
<script>
$(document).ready(function(){
  $("button").click(function(){
  $("div").animate({
    right: "100px",
    bottom: "100px",
  });
}); 

});
</script>
~~~~
  - set relative value
~~~~
<script>
$(document).ready(function(){
  $("button").click(function(){
  $("div").animate({
    right: "+=100px",
    bottom: "+=100px",
  });
}); 

});
</script>
~~~~

[Homework 4](https://github.com/ZhangNingSAU/Fall-2021-CSCI-330-Web-Programming/blob/master/Homework/HW4.md)

# Reference: [w3school](https://www.w3schools.com/jquery/)

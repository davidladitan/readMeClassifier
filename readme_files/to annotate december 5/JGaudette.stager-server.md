# Calculator Lab

`git clone` this repo to start the calculator homework.

You can open `calculator.html` to see the (nonfunctional) calculator page.
You're gonna make it work!

## Stage 0: Getting Started

**Try the following before jumping to the solution**. Note this lab will require lots of code repetition. We aren't writing clean code. We will write a very rough draft of code that you can later clean up.

1. The `calculator.js` file is linked in the `calculator.html`, but you won't be able to manipulate the page before the `window` loads. Write a function to handle the `window.onload`
	* The `window.onload` handler should `alert("loaded")`
	* Use a selector to grab each `div` that is a number button using the id. Note: this is highly repetitive and will require `9` selector statements.
	* Add an `onclick` listener to each button and `alert` a message with which one number is clicked.
	
==========

Solution:


```
  window.onload = function () {
  	alert("Window loaded!");
  	var buttons = document.querySelectorAll(".button");
  		
	// Grab number buttons
	var numOne = document.getElementById("number_1"),
	    numTwo = document.getElementById("number_2"),
	    numThree = document.getElementById("number_3");
	    // and so on
	 
	// alert which num was clicked
	numOne.onclick = function () {
		alert("1");
	};
	
	numTwo.onclick = function () {
		alert("2");
	};
	
	numThree.onclick = function () {
		alert("3");
	}
  };


```

==========


## Stage 0.5: A Little More Setup


* Modify the `calculator.html` so that each `operation` button, `+, -, *, /` has an id that can be used to select it.
* Select each operation button from the DOM using their above ids.
* Add an `onclick` listener onto each operation button that alerts which operation was clicked


==========

Solution:


```
window.onload = function () {
  	alert("Window loaded!");
  	var buttons = document.querySelectorAll(".button");
  		
	// Grab number buttons
	var numOne = document.getElementById("number_1"),
	    numTwo = document.getElementById("number_2"),
	    numThree = document.getElementById("number_3");
	    // and so on
	 
	// alert which num was clicked
	numOne.onclick = function () {
		alert("1");
	};
	
	numTwo.onclick = function () {
		alert("2");
	};
	
	numThree.onclick = function () {
		alert("3");
	}
	
	
	// if you had id's like the following:
	var addOp = document.getElementById("op_plus"),
	   subOp = document.getElementById("op_sub"),
	   multOp = document.getElementById("op_mult"),
	   divOp = document.getElementById("op_div"),
	   entOp = document.getElementById("op_ent"),
	   clrOp = document.getElementById("op_clr");
	   
	// add click listeners to each operation
	addOp.onclick = function () {
		alert("+");
	};

	subOp.onclick = function () {
		alert("-");
	};
	
	multOp.onclick = function () {
		alert("*");
	};

	divOp.onclick = function () {
		alert("/");
	};
	
	// also add them to calculator operations
	entOp = function () {
		alert("enter pushed");
	}
	clrOp = function () {
		alert("clear pushed");
	}
};


```

==========




## Stage 1: Displaying Numbers


* Like how you selected `numbers` and `operations` earlier so that you could manipulate them and listen to them for clicks, you now want to select the display div. In particular, you need to select `#result_display_value`.
* Now go back and modify your number click listeners to not just alert, but also, they should concat it onto the `innerHTML` of the `#result_display_value` div.
	
	```
		Imagine an empty display
		
		 -----------
	    |			|
	     ----------
	     
	    You click 1
	    
		 -----------
	    |		1	| and it shows up 
	     ----------    
	    
	    You click 2 after
		 -----------
	    |		12	| it displays says 12
	     ----------	    
	    
	```


======
 Solution will be coded together... CODE ALONG! :D

======

## Stage 2: Entering An Operation


Thus far we've left our calculator with a number being input in the display, `123`. If someone pushes an operation you then need to clear the screen, and display the operation somewhere a user can remember it. You should display the operation pushed in the div with id `operator_display`.


	```
		Enters a number
		 -----------
	    |		123	| 
	     ----------	
	     
	    Pushes +
		 -----------
	    |			| clears the display first
	     ----------	
	     
		 -----------
	    |+			| then display shows the operation
	     ----------		    	    
	    
	    
	```

## Stage 3: Entering A Second Number

With the ability to enter one number onto the screen and then press an operation we cleared out the display. We should save the first number in a variable somewhere, so it isn't lost. 

Modify your work from stage three to add the following features when someone enters an operation: 

* Save the first number input to the display in a variable called `first`  when someone pushes an `operation`. 
* Save the operation in a variable called `op`.

When someone starts entering their second number you don't have to worry about losing any information and you can just display it.


## Stage 4: Calculating?


* When a user clicks the `enter` button use the `last` value and the number currently in the display to perform the operation stored in `op`.
* Use the result calculated above and display it in the `#result_display_value`. 
* Once you have the result above clear out the `#operator_display`.







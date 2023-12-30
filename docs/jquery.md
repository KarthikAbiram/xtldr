---
hide:
  - navigation
---
# jQuery
## Setting Up
One of the most popular javascript libraries is jQuery, which is much more concise and easy to use.  To include jQuery, refer to [jQuery releases](https://releases.jquery.com/) section. Include the jQuery javascript above your javascript include statement in HTML:
```
<script src="https://code.jquery.com/jquery-3.6.3.min.js" integrity="sha256-pvPw+upLPUjgMXY0G+8O0xUf+/Im1MZjXxxgOcBQBXU=" crossorigin="anonymous"></script>
```

## Adding and Removing CSS Classes 
To dynamically add/remove a CSS class from a HTML object, using jQuery:
```
$("#myId").addClass("css-class-name");
$("#myId").removeClass("css-class-name");
```
To check if a HTML element has a class:
```
$("#myId").hasClass("css-class-name");
```
## Updating Text of HTML Element
Using jQuery, we can update text of a HTML element as shown below.
```
$("#myheading").text(); //Returns the text
$("#myheading").text("My New Heading"); //Updates the text

$("#myheading").html(); //Returns the inner HTML present which would include styles like <b>, <i>
$("#myheading").html("<b>My New</b> <i>Heading</i>"); //Updates the inner HTML with the styling provided
```
## Updating Attributes
Using jQuery, we can get attribute values as well as set attributes as shown below:
```
$("img").attr("src"); //Returns the src attribute value for the img tag
$("img").attr("src","logo.png"); //Updates the attribute value to "logo.png" for the img tag
```
## Updating CSS
Use the CSS property name to query the current value of a CSS property. When the value is passed as the 2nd argument, the value gets set.
```
$("h1").css("color"); //Returns the font color of h1
$("h1").css("color","red"); //Sets the font color
```
## Adding Event Listeners
To register for a click event for "h1" tag using jQuery:
```
$("h1").click(function(){
console.log("clicked");
});
```
Or more generically where you can pass the event type as a string:
```
$("h1").on("click",(function(){
console.log("clicked");
}));
```

To register for key press across the entire web page, you can use "body" as the identifier:
```
$("body").keypress(function(event){
console.log(event.key); //Logs the key pressed by the user
});
```
or directly passing document as the argument (and not as a string):
```
$(document).keypress(function (event) {
console.log(event.key); //Logs the key pressed by the user
$("h1").text(event.key);
});
```
## Adding HTML Elements
To add a HTML element before/after an element:
```
$("h1").before("<button>My New Button</button>");
$("h1").after("<button>My New Button</button>");
```
To add a HTML element within an element:
```
$("h1").prepend("<button>My New Button</button>"); //Within h1,but before h1 text
$("h1").append("<button>My New Button</button>"); //Within h1,but after h1 text
```
## Animations
Various options available to hide and unhide:
```
$("h1").hide();
$("h1").show();
$("h1").toggle(); //Alternates between hide and show

//With fading
$("h1").fadeOut(); //Similar to hide
$("h1").fadeIn();
$("h1").fadeToggle();

//With Sliding
$("h1").slideUp(); //Collapse
$("h1").slideDown(); //Uncollapse
$("h1").slideToggle();
```
Custom animations are possible using animate:
```
$("h1").animate({opacity:0.5});
```
It is also possible to chain functions and they get executed one by one from left to right.
```
$("h1").slideUp().slideDown().animate({opacity:0.5});
```
# jQuery
* Let's first review Web APIs DOM

## DOM Manipulation
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic JavaScript Dump</title>
</head>
  <body>

    <!-- We created an empty HTML div. Note that there is no content inside. -->
    <div id="empty-div"></div>

  </body>
</html>
```

## Add text to an existing element
```
// MORE CODE

<body>

    <div id="empty-div"></div>

    <!-- We now create a new JavaScript script. -->
    <script type="text/javascript">

      // Inside, we latch onto the "emptyDiv" using the JavaScript ".getElementById" selector.
      var targetDiv = document.getElementById("empty-div");

      // We then use the JavaScript method ".textContent" to change the content to "Hello friends!"
      targetDiv.textContent = "Hello friends!";

    </script>

  </body>
// MORE CODE
```

## Overwrite existing content
```
// MORE CODE

<body>

    <div id="empty-div"></div>

    <script type="text/javascript">

      var targetDiv = document.getElementById("empty-div");

      targetDiv.textContent = "Hello friends!";

      // If we try to add to the div using the same .textContent method... it just replaces the old content.
      targetDiv.textContent = "A pleasure to meet you!";

    </script>

  </body>
// MORE CODE
```

## Create new elements
```
// MORE CODE

<body>

    <div id="empty-div"></div>

    <script type="text/javascript">

      var targetDiv = document.getElementById("empty-div");

      targetDiv.textContent = "Hello friends!";

      // In this example, we instead create a new div called "newDiv".
      var newDiv = document.createElement("div");

      // We then give this newDiv the text "A pleasure to meet you!".
      newDiv.textContent = "A pleasure to meet you!";

      // Now we use the ".appendChild" method to combine the two divs together on the page.
      targetDiv.appendChild(newDiv);

    </script>

  </body>
// MORE CODE
```

## Change attributes
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic JavaScript Dump</title>

    <!-- Here we create a bit of CSS for classes called ".fancy" -->
    <style>
      .fancy {
        font-size: 100px;
        color: green;
      }
    </style>

</head>
  <body>

    <div id="empty-div"></div>

    <script type="text/javascript">

      var targetDiv = document.getElementById("empty-div");

      targetDiv.textContent = "Hello friends!";

      var newDiv = document.createElement("div");
      newDiv.textContent = "A pleasure to meet you!";

      targetDiv.appendChild(newDiv);

      // We then apply that CSS to our newDiv.
      newDiv.setAttribute("class", "fancy");

    </script>

  </body>
</html>
```

## Now let's jump into jQuery
## Let's convert Web API to jQuery DOM manipulation
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic JavaScript Dump</title>

    <!-- Here we create a bit of CSS for classes called ".fancy" -->
    <style>
      .fancy {
        font-size: 100px;
        color: green;
      }
    </style>

</head>
  <body>

    <div id="empty-div"></div>

    <script type="text/javascript">

      var targetDiv = document.getElementById("empty-div");

      targetDiv.textContent = "Hello friends!";

      var newDiv = document.createElement("div");
      newDiv.textContent = "A pleasure to meet you!";

      targetDiv.appendChild(newDiv);

      // We then apply that CSS to our newDiv.
      newDiv.setAttribute("class", "fancy");

    </script>

  </body>
</html>
```

## jQuery selectors and manipulating content
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Basic JavaScript Dump</title>

    <!-- Here we create a bit of CSS for classes called ".fancy" -->
    <style>
      .fancy {
        font-size: 100px;
        color: green;
      }
    </style>

</head>
  <body>

    <div id="empty-div"></div>

    <script type="text/javascript">

      var targetDiv = document.getElementById("empty-div");

      targetDiv.textContent = "Hello friends!";

      var newDiv = document.createElement("div");
      newDiv.textContent = "A pleasure to meet you!";

      targetDiv.appendChild(newDiv);

      // We then apply that CSS to our newDiv.
      newDiv.setAttribute("class", "fancy");

    </script>

  </body>
</html>
```

## What's the difference here?
```
// MORE CODE

// NOTICE THE DIFFERENCE
    // ---------------------
    // $("#empty-div")   <-- FIND a DOM node with the ID empty-div
    // $("<div>")        <-- CREATE a new DIV
// MORE CODE
```

## Adding content vs creating an element and adding content
```
// MORE CODE

// NOTICE THE DIFFERENCE
    // ---------------------
    // $("#empty-div")   <-- FIND a DOM node with the ID empty-div
    // $("<div>")        <-- CREATE a new DIV
// MORE CODE
```

## Add and append content
```
// MORE CODE

<body>

  <div id="empty-div"></div>

  <script type="text/javascript">

    $("#empty-div").html("<h1>Hello friends!</h1>");

    // If we needed each line to be its own div, we could just as easily create a new div.
    var newDiv = $("<div>");
    newDiv.text("A pleasure to meet you!");

    // NOTICE THE DIFFERENCE
    // ---------------------
    // $("#empty-div")   <-- FIND a DOM node with the ID empty-div
    // $("<div>")        <-- CREATE a new DIV

    // We can then  append it to the other div using the same ".append" method.
    $("#empty-div").append(newDiv);

  </script>

</body>
// MORE CODE
```

## My DOM "Prototype" technique
* Just build the HTML first and get it to the way you like
* Take that code and make it a comment in your JavaScript file and use that to write your DOM manipulation code

## Change attributes with jQuery
```
// MORE CODE

<body>

  <div id="empty-div"></div>

  <!-- Here we're adding a bit of CSS -->
  <style>
    .fancy {
      font-size: 100px;
      color: green;
    }
  </style>

  <script type="text/javascript">

    $("#empty-div").html("<h1>Hello friends!</h1>");

    // jQuery alternative to: var newDiv = document.createElement("div");
    var newDiv = $("<div>");

    // jQuery alternative to: newDiv.textContent = "A pleasure to meet you!";
    newDiv.text("A pleasure to meet you!");

    // jQuery alternative to: document.querySelector("#empty-div").appendChild(newDiv);
    $("#empty-div").append(newDiv);

    // If we need to apply some CSS, we can quickly do so, using the jQuery ".attr" method.
    newDiv.attr("class", "fancy");

  </script>

</body>
// MORE CODE
```

## jQuery Drink list
```
// MORE CODE

<!-- Here we create a generic drink-options div -->
  <div id="drink-options"></div>

  <script type="text/javascript">

    // Array holds all of the drinks available
    var drinkList = [
      "Coffee: $5",
      "Espresso: $7",
      "Cappuccino: $6",
      "Latte: $4",
      "Tea: $3",
      "Ice Coffee: $6",
      "Ice Espresso: $8",
      "Ice Latte: $6",
      "Ice Tea: $4"
    ];

    // This line of jQuery selects the div with the matching id (#drink-options)
    var drinkDiv = $("#drink-options");

    // Here we loop through our array using the .each() method and append a new div with each iteration
    $.each(drinkList, function(i, drink) {
      drinkDiv.append("<div>" + drink + "</div>");
    });

  </script>
// MORE CODE
```

## jQuery events
### jQuery `ready`
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Trigger Clicked</title>

  <!-- Added link to the jQuery library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

</head>
<body>

  <!-- Header with an id of click-me -->
  <h3 id="click-me">CLICK ME!</h3>

  <script type="text/javascript">

    // This "document.ready" code isn't necessary in this example... but is useful to become familiar with.
    // "document.ready" makes sure that our JavaScript doesn't get run until the HTML document is finished loading.
    $(document).ready(function() {

      // Here we use jQuery to select the header with "click-me" as its ID.
      // Notice I have the #click-me, click, and then the function
      // So $("#id|.class|element").on("action", function(){});
      // And so whenever it is clicked...
      $("#click-me").on("click", function() {
        alert("I've been clicked!");
      });

    });

</script>

</body>
</html>
```

## jquery events
* Click on links that will increment and show increment and image in UI

```
// MORE CODE

<body>

    <h1>Click to Eat Sandwich</h1>
    <h3 id="pbj">Peanut Butter Jelly</h3>
    <h3 id="grilledcheese">Grilled Cheese</h3>
    <h3 id="roastbeef">Roast Beef</h3>

    <div id="image-div"></div>

    <script type="text/javascript">

    // This document.ready isn't necessary in this example... but is needed in cases where the HTML is complex.
    // This code makes sure that the JavaScript doesn't get run until the HTML is finished loading
    // It's useful to become familiar with now.

    $(document).ready(function() {

      // VARIABLES
      // ====================================================================

      // Here we create variables for tracking the number of sandwiches eaten

      var pbjCounter = 0;
      var grilledCheeseCounter = 0;
      var roastBeefCounter = 0;

      // FUNCTIONS
      // ====================================================================
      // Here we create various "on click" events which capture clicks
      // Inside each click event is the code to create an alert, update the counter, and show the updated count.
      // Take note that you can chain events onto an element
      // With this even if our ids are created at a later date our events will still always work
      $("#pbj").on("click", function() {

        alert("Mmm... Peanut Butter Jelly Time.");
        pbjCounter++;
        alert("You've eaten " + pbjCounter + " PB&J sandwiches");

        // BONUS
        $("#image-div").html("<img src='https://i1.wp.com/snotapwi.com/wp-content/uploads/2017/03/PBJ-Sandwiches.jpg?resize=590%2C368&ssl=1' />");

      });
      $("#grilledcheese").on("click", function() {

        alert("Nom nom nom. Gooey Gooey Grilled Cheese!");
        grilledCheeseCounter++;
        alert("You've eaten " + grilledCheeseCounter + " grilled cheese sandwiches");

        // BONUS
        $("#image-div").html("<img src='http://cdn.funcheap.com/wp-content/uploads/2014/04/The-Perfect-Grilled-Cheese-Sandwich-800-158111.jpg' />");

      });
      $("#roastbeef").on("click", function() {

        alert("No qualms about animal rights here. I'm all about that roast beef.");
        roastBeefCounter++;
        alert("You've eaten " + roastBeefCounter + " roast beef sandwiches");

        // BONUS
        $("#image-div").html("<img src='https://www.cscassets.com/recipes/wide_cknew/wide_25336.jpg' />");

      });
    });

  </script>

  </body>
// MORE CODE
```

## Random Number
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Trigger Random</title>

  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/font-awesome/4.7.0/css/font-awesome.min.css">
  <!-- Added link to the jQuery library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

  <!-- Added a link to Bootstrap-->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

</head>
<body>

  <div class="jumbotron">

    <h1 class="text-center">Generate a Random Number!</h1>

    <div class="text-center">

      <!-- Here we have our button for generating random numbers (#random-button) -->
      <button id="random-button" class="btn btn-primary btn-lg fa fa-question"></button>

    </div>

  </div>

  <!-- Here we have div called "randomNumber" where our random number will go -->
  <h1 class="text-center" id="random-number"></h1>

  <script type="text/javascript">

    $(document).ready(function() {

      // Notice I didn't set $(".jumbotron") to a var this time?
      // If you only plan to use that selector once it doesn't need to be a var
      $("#random-button").on("click", function() {

        // ... we generate a random number
        var random = Math.floor(Math.random() * 1000) + 1;

        // ... and then dump the random number into our random-number div.
        $("#random-number").text(random);

      });

    });

  </script>

</body>
</html>
```

## Lottery
```
// MORE CODE

  <!-- Added link to the jQuery Library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

  <!-- Added a link to Bootstrap-->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">
</head>
<body>

  <div class="jumbotron">

    <h1 class="text-center">Generate Lottery Numbers!</h1>

    <div class="text-center">

      <!-- Here we have our button with id random-button -->
      <button id="random-button" class="btn btn-primary btn-lg"><h1>?</h1></button>

    </div>

  </div>

  <!-- Here we have div called "random-number" where our random number will go -->
  <h1 class="text-center" id="random-number"></h1>

  <script type="text/javascript">

    $(document).ready(function() {

      $("#random-button").on("click", function() {

        // Create a string which will hold the lottery number
        var lottoNumber = "";

        // Then initiate a loop to generate 9 separate numbers
        for (var i = 0; i < 9; i++) {

          // For each iteration, generate a new random number between 0 and 9.
          var random = Math.floor(Math.random() * 10);

          // Take this number and then add it to the rest of the string.
          // In essence, we are iteratively building a string of numbers. (e.g. First: 1, Second: 13, Third: 135, etc.)
          lottoNumber = random + lottoNumber;

        }

        // ... and then dump the random number into our random-number div.
        $("#random-number").prepend("<br><hr>" + lottoNumber);

      });

    });

  </script>

</body>
// MORE CODE
```

## Number checker
```
<!-- Added link to the jQuery Library -->
  <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

  <!-- Added a link to Bootstrap-->
  <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0/css/bootstrap.min.css">

</head>

<body>

  <div class="jumbotron">
    <h1 class="text-center">Number Guesser</h1>
    <h2 class="text-center">See if you can guess the number the computer is thinking of!</h2>
  </div>

  <div class="container">

    <div class="row">
      <div class="col-md-12">
        <div class="card mb-2">
          <h3 class="card-header">Computer Pick</h3>
          <div class="card-body text-center">
            <h1 id="computer-pick">???</h1>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12">
        <div class="card mb-2">
          <h3 class="card-header">You Pick</h3>
          <div class="card-body text-center">
            <button id="button-1" class="btn btn-danger btn-choice" value="1">
              <h1>1</h1>
            </button>
            <button id="button-2" class="btn btn-danger btn-choice" value="2">
              <h1>2</h1>
            </button>
            <button id="button-3" class="btn btn-danger btn-choice" value="3">
              <h1>3</h1>
            </button>
            <button id="button-4" class="btn btn-danger btn-choice" value="4">
              <h1>4</h1>
            </button>
          </div>
        </div>
      </div>
    </div>

    <div class="row">
      <div class="col-md-12">
        <div class="card mb-2">
          <h3 class="card-header">Result</h3>
          <div class="card-body text-center">
            <h1 id="result"></h1>
          </div>
        </div>
      </div>
    </div>

  </div>

  <script type="text/javascript">

    $(document).ready(function() {

      // Initial Variables
      var computerPick = Math.floor(Math.random() * 4) + 1;
      var lockGame = false;

      // We log the computer's pick to console to make it easier to troubleshoot
      console.log("Computer Pick: " + computerPick);

      // Here we create the on click event that gets the user"s pick
      $(".btn-choice").on("click", function() {

        // Here this lockGame line prevents the user from changing the option after the game is done.
        if (lockGame !== true) {

          // We get the value associated with the button the user picked from here
          var yourPick = $(this).val();
          console.log("Your Pick: " + yourPick);

          // We then reveal the computer's pick in the html
          $("#computer-pick").text(computerPick);

          // If your pick matched the computer's pick you let them know.
          if (parseInt(yourPick) === computerPick) {
            $("#result").text("Yep! You got it! Refresh the page to play again.");
            lockGame = true;
          }

          // If the numbers did not match. You also let them know
          else {
            $("#result").text("Nope. Refresh the page to play again.");
            lockGame = true;
          }
        }

      });
    });

  </script>

</body>
```

## Fridge game
```
<!DOCTYPE html>
<html>

<head>
  <meta charset="UTF-8">
  <title>Fridge Magnets</title>
</head>

<!-- CSS Styles (These styles are provided to you. Don't touch these!) -->
<style>
  body {
    background: url(assets/fridge.png) no-repeat;
  }

  .letter {
    width: 30px;
    height: 30px;
    border-style: solid;
    padding: 2px;
    float: left;
    margin: 2px;
  }

  .letter-button-color {
    color: darkcyan;
  }

  .fridge-color {
    color: orange;
  }

  #display {
    margin-top: 78px;
    height: 500px;
    width: 220px;
    margin-left: 60px;
  }

  #buttons {
    padding-top: 60px;
  }

  #clear {
    margin-left: 20px;
    font-size: 25px;
    color: black;
    border-style: solid;
    width: 100px;
  }
</style>

<body>
  <div id="display"></div>
  <div id="buttons"></div>
  <button id="clear">clear</button>

  <script type="text/javascript" src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.2.1/jquery.min.js"></script>

  <script type="text/javascript">
    $(document).ready(function() {

      // Here we are provided an initial array of letters.
      // Use this array to dynamically create buttons on the screen.
      var letters = ["A", "B", "C", "D", "E", "F", "G", "H", "I", "J", "K", "L", "M", "N", "O", "P", "Q", "R", "S", "T", "U", "V", "W", "X", "Y", "Z", "_"];

      // MAJOR TASK #1: DYNAMICALLY CREATE BUTTONS
      // =================================================================================

      // 1. Create a for-loop to iterate through the letters array.
      for (var i = 0; i < letters.length; i++) {

        // Inside the loop...

        // 2. Create a variable named "letterBtn" equal to $("<button>");
        var letterBtn = $("<button>");

        // 3. Then give each "letterBtn" the following classes: "letter-button" "letter" "letter-button-color".
        letterBtn.addClass("letter-button letter letter-button-color");

        // 4. Then give each "letterBtn" a data-attribute called "data-letter".
        letterBtn.attr("data-letter", letters[i]);

        // 5. Then give each "letterBtns" a text equal to "letters[i]".
        letterBtn.text(letters[i]);

        // 6. Finally, append each "letterBtn" to the "#buttons" div (provided).
        $("#buttons").append(letterBtn);

      }

      // Be sure to test that your code works for this major task, before proceeding to the next one!

      // MAJOR TASK #2: ATTACH ON-CLICK EVENTS TO "LETTER" BUTTONS
      // =================================================================================

      // 7. Create an "on-click" event attached to the ".letter-button" class.
      $(".letter-button").on("click", function() {

        // Inside the on-click event...

        // 8. Create a variable called "fridgeMagnet" and set the variable equal to a new div.
        var fridgeMagnet = $("<div>");

        // 9. Give each "fridgeMagnet" the following classes: "letter fridge-color".
        fridgeMagnet.addClass("letter fridge-color");

        // 10. Then chain the following code onto the "fridgeMagnet" variable: .text($(this).attr("data-letter"))
        // attr acts as both a setter and a getter for attributes depending on whether we supply one argument or two
        // NOTE: There IS a $(data) jQuery method, but it doesn't do what you'd expect. So just use attr.
        fridgeMagnet.text($(this).attr("data-letter"));

        // 11. Lastly append the fridgeMagnet variable to the "#display" div (provided);
        // Again you can see we use that find, and once its found we append the item
        $("#display").append(fridgeMagnet);

      });

      // Be sure to test that your code works for this major task, before proceeding to the next one!

      // MAJOR TASK #3: ATTACH ON-CLICK EVENTS TO "CLEAR" BUTTON
      // =================================================================================

      // 12. Create an "on-click" event attached to the "#clear" button id.
      $("#clear").on("click", function() {

        // Inside the on-click event...

        // 13. Use the jQuery "empty()" method to clear the contents of the "#display" div.
        // We use find here and once its found it will empty the element
        $("#display").empty();

      });

    });
  </script>
</body>

</html>
```


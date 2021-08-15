# StarsRating
## Description 
  ### Demo : 
   https://yuvam2017.github.io/StarsRating/
  How to use star rating in your website <br>
  Here are the best options:
 
  ### 1. Using Jquery
  #### Jquery File 
  You can download it from the above link
            
    //ES5
    $.fn.stars = function() {
        return $(this).each(function() {
            var rating = $(this).data("rating");
            var fullStar = new Array(Math.floor(rating + 1)).join('<i class="fas fa-star"></i>');
            var halfStar = ((rating%1) !== 0) ? '<i class="fas fa-star-half-alt"></i>': '';
            var noStar = new Array(Math.floor($(this).data("numStars") + 1 - rating)).join('<i class="far fa-star"></i>');
            $(this).html(fullStar + halfStar + noStar);
        });
    }

    //ES6
    $.fn.stars = function() {
        return $(this).each(function() {
            const rating = $(this).data("rating");
            const numStars = $(this).data("numStars");
            const fullStar = '<i class="fas fa-star"></i>'.repeat(Math.floor(rating));
            const halfStar = (rating%1!== 0) ? '<i class="fas fa-star-half-alt"></i>': '';
            const noStar = '<i class="far fa-star"></i>'.repeat(Math.floor(numStars-rating));
            $(this).html(`${fullStar}${halfStar}${noStar}`);
        });
    }
               
   #### HTML
           
           
        <span class="stars" data-rating="3.5" data-num-stars="5" ></span>
        
  But need to add this statement in your HTML FILE
   ##### 1. FONT AWESOME CSS FILE
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.min.css" rel="stylesheet">
   ##### 2. JQUERY JS FILE
        <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
   ##### 3. StarRating JS FILE 
        <script src="js/jquery.Rating.js"></script>
   ##### 4. THIS FUNCTION
        
            $(function(){
                $('.stars').stars();
            });

 ##### NOTE :
  1. If you are using javascript and want to add this 4 number function code try to use it in the script tag in html only <br>
  2. By default the color is black using CSS you can change the color of the stars
  ###### CSS 
      .stars {
        color: #ff7b00;
        font-size : 1.3rem;
      }
 
 
 
 ## WHOLE CODE:
  ### HTML
     <!DOCTYPE html>
      <html lang="en">
      <head>
          <meta charset="UTF-8">
          <meta name="viewport" content="width=device-width, initial-scale=1.0">
          <meta http-equiv="X-UA-Compatible" content="ie=edge">
          <title>Star Rating</title>
          <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/5.9.0/css/all.min.css" rel="stylesheet">
          <script src="https://cdnjs.cloudflare.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
          <script src="js/jquery.Rating.js"></script>
          <script>
              $(function(){
                  $('.stars').stars();
              });
          </script>
      </head>
      <body>

          <span class="stars" data-rating="3.5" data-num-stars="5" ></span>

      </body>
      </html>
      
  ### JS
  
      //ES5
      $.fn.stars = function() {
          return $(this).each(function() {
              var rating = $(this).data("rating");
              var fullStar = new Array(Math.floor(rating + 1)).join('<i class="fas fa-star"></i>');
              var halfStar = ((rating%1) !== 0) ? '<i class="fas fa-star-half-alt"></i>': '';
              var noStar = new Array(Math.floor($(this).data("numStars") + 1 - rating)).join('<i class="far fa-star"></i>');
              $(this).html(fullStar + halfStar + noStar);
          });
      }

      //ES6
      $.fn.stars = function() {
          return $(this).each(function() {
              const rating = $(this).data("rating");
              const numStars = $(this).data("numStars");
              const fullStar = '<i class="fas fa-star"></i>'.repeat(Math.floor(rating));
              const halfStar = (rating%1!== 0) ? '<i class="fas fa-star-half-alt"></i>': '';
              const noStar = '<i class="far fa-star"></i>'.repeat(Math.floor(numStars-rating));
              $(this).html(`${fullStar}${halfStar}${noStar}`);
          });
      }

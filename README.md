# Imagecarousell-for-a-website
This is just a fun tutorial for begginers in web development. Add on your knowledge with these amazing skills. Learn how to diplay your images in a carousel for a website.

Comment from gnawood.
I found this very useful to generate a slide show on my website http://www.abacus-arts.org.uk  
The carousell works fine, but an SEOptimer.com evaluation report says there is a problem with the Java script.   
  “Cannot read property 'className' of undefined at showSlides (http://www.abacus-arts.org.uk/:78:8) ”    
Line 78 is near the end below and says:-  dots[slideIndex-1].className += " active";   

Should I ignore the report, or is there a fix? 

```
<div>
<!-- code for slides 1 to 4 removed, below are slides 5 and 6 in the carousell -->
  <div class="mySlides">
    <div class="picnumber"> 5 / 6</div> <img src="Pic-5-DM.jpg" alt="Pic5" style="width:100%";> 
     <div class="pictitle"> Breakout room LHS view                      </div> </div>
  <div class="mySlides">
    <div class="picnumber"> 6 / 6</div> <img src="Pic-6-GW.jpg" alt="Pic6" style="width:100%";> 
     <div class="pictitle"> Street view of entrance  </div> </div>
     
 <!-- Back and forward buttons jump to the Java Script lower down -->
  <a class="prev" onclick="plusSlides(-1)"> &lt;</a>
  <a class="next" onclick="plusSlides(1)">  &gt;</a>
</div>

 <!-- based on GITHUB https://github.com/KanizoRGB/Imagecarousell-for-a-website/blob/main/imagecarousell.css -->
<script>
var slideIndex = 1;
showSlides(slideIndex);
 function plusSlides(n)   {   showSlides(slideIndex += n); }
 function currentSlide(n) {   showSlides(slideIndex = n);  }
 function showSlides(n)   {   var i;
   var slides = document.getElementsByClassName("mySlides");
   var dots = document.getElementsByClassName("demo");
   var captionText = document.getElementById("caption");
   if (n > slides.length) {slideIndex = 1                }
   if (n < 1)             {slideIndex = slides.length    }
   for (i = 0; i < slides.length; i++) { slides[i].style.display = "none";  }
   for (i = 0; i < dots.length; i++)  
   { dots[i].className = dots[i].className.replace(" active", "");  }
   slides[slideIndex-1].style.display = "block";
   dots[slideIndex-1].className += " active";
  captionText.innerHTML = dots[slideIndex-1].alt;   }
</script>
```



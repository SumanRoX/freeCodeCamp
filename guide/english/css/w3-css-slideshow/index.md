---
title: W3 CSS Slideshow
---

### The Following content is credited to W3Schools

## Manual Slideshow

Displaying a manual slideshow with W3.CSS is very easy.

Just create many elements with the same class name:
```
<div class="w3-content w3-display-container">
  <img class="mySlides" src="img1.jpg" style="width:100%">
  <img class="mySlides" src="img2.jpg" style="width:100%">
  <img class="mySlides" src="img3.jpg" style="width:100%">
  <img class="mySlides" src="img4.jpg" style="width:100%">
```

### And two buttons to scroll the images:
```
  <button class="w3-button w3-black w3-display-left" onclick="plusDivs(-1)">&#10094;</button>
  <button class="w3-button w3-black w3-display-right" onclick="plusDivs(1)">&#10095;</button>
</div>
```
## And add a JavaScript to select images:

```
var slideIndex = 1;
showDivs(slideIndex);

function plusDivs(n) {
    showDivs(slideIndex += n);
}

function showDivs(n) {
    var i;
    var x = document.getElementsByClassName("mySlides");
    if (n > x.length) {slideIndex = 1} 
    if (n < 1) {slideIndex = x.length} ;
    for (i = 0; i < x.length; i++) {
        x[i].style.display = "none"; 
    }
    x[slideIndex-1].style.display = "block"; 
}
```
### Fundamentals of JavaScript working in the code

1. First, set the slideIndex to 1. (First picture)

2. Then call showDivs() to display the first image.

3. When the user clicks one of the buttons call plusDivs().

4. The plusDivs() function subtracts one or  adds one to the slideIndex.

5. The showDiv() function hides (display="none") all elements with the class name "mySlides", and displays (display="block") the element with the given slideIndex.

6. If the slideIndex is higher than the number of elements (x.length), the slideIndex is set to zero.

7. If the slideIndex is less than 1 it is set to number of elements (x.length).

### Automatic Slideshow

Javascript Sample
```
var slideIndex = 0;
carousel();

function carousel() {
    var i;
    var x = document.getElementsByClassName("mySlides");
    for (i = 0; i < x.length; i++) {
      x[i].style.display = "none"; 
    }
    slideIndex++;
    if (slideIndex > x.length) {slideIndex = 1} 
    x[slideIndex-1].style.display = "block"; 
    setTimeout(carousel, 2000); // Change image every 2 seconds
}
```
### For More Information on Slideshows and more cool stuff checkout the links below

1. <a href="https://www.w3schools.com/w3css/w3css_slideshow.asp" target="_blank">W3School SlideShow</a>
2. <a href="https://www.w3schools.com" target="_blank">W3School Home</a>

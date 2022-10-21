---
layout: single
title:  "Installing Git in Windows"
date:   2022-10-21 20:06:44 +0800
categories: blog
toc: true
toc_sticky: true
tags: git scm vcs beginner
#permalink:
published: true
---
Git has been one of the most use and popular tool and SCM when setting up a new PC / laptop for development. It is free, open source and can run on multiple OS such as Windows, Mac and Linux. This post is for people who are into software development and considered as a newbie on using SCM (source control management). The steps documented below might change over time depending on the version of the installer.

1. Open your favorite browser and go to https://git-scm.com/download/win
2. Download the installer by clicking the hyperlink "Click Here to Download". Once downloaded, open/run the downloaded below. 

<style>
* {box-sizing: border-box}
body {font-family: Verdana, sans-serif; margin:0}
.mySlides {display: none}
img {vertical-align: middle;}

/* Slideshow container */
.slideshow-container {
  max-width: 1000px;
  position: relative;
  margin: auto;
}

/* Next & previous buttons */
.prev, .next {
  cursor: pointer;
  position: absolute;
  top: 50%;
  width: auto;
  padding: 16px;
  margin-top: -22px;
  color: rgb(76, 0, 153);
  font-weight: bold;
  font-size: 25px;
  transition: 0.6s ease;
  border-radius: 0 3px 3px 0;
  user-select: none;
}

/* Position the "next button" to the right */
.next {
  right: 0;
  border-radius: 3px 0 0 3px;
}

/* On hover, add a black background color with a little bit see-through */
.prev:hover, .next:hover {
  background-color: rgba(0,0,0,0.8);
  color: rgb(255,255,255);
}

/* Caption text */
.text {
  color: #f2f2f2;
  font-size: 15px;
  padding: 8px 12px;
  position: absolute;
  bottom: 8px;
  width: 40%;        
  /*text-align: center; */
  right: 0px;
  word-wrap: break-word;
}

/* Number text (1/3 etc) */
.numbertext {
  color: #f2f2f2;
  font-size: 12px;
  padding: 8px 12px;
  position: absolute;
  top: 0;
}

/* The dots/bullets/indicators */
.dot {
  cursor: pointer;
  height: 15px;
  width: 15px;
  margin: 0 2px;
  background-color: #bbb;
  border-radius: 50%;
  display: inline-block;
  transition: background-color 0.6s ease;
}

.active, .dot:hover {
  background-color: #717171;
}

/* Fading animation */
.fade {
  animation-name: fade;
  animation-duration: 1.5s;
}

@keyframes fade {
  from {opacity: .4} 
  to {opacity: 1}
}

/* On smaller screens, decrease text size */
@media only screen and (max-width: 300px) {
  .prev, .next,.text {font-size: 11px}
}
</style>

# Installation Steps
Installing Git through an installer is straightforward, below shows the installation steps by steps through captured screenshots. 
Use **>** to transition to the next screenshot, **<** to go back to the previous screenshot.

<div class="slideshow-container">

<div class="mySlides fade">
  <div style="text-align:center">It begins displaying the General Public License information</div>
  <img src="/assets/images/install-git-02.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Change the destination location if you prefer to install it on another drive or path</div>
  <img src="/assets/images/install-git-03.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Select additional components as needed, most of the time no additional selection is needed</div>
  <img src="/assets/images/install-git-04.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">By default it would create a Start Menu, however users can also opt out by ticking the checkbox "Don't create start menu"</div>
  <img src="/assets/images/install-git-05.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Choose the preferred editor, leave it as the default setting if you are not sure what to use</div>
  <img src="/assets/images/install-git-06.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">By default the branch created is <bold>master</bold>, after the incident on Black Lives Matter some software companies gives the option to change the default branch name into a different name</div>
  <img src="/assets/images/install-git-07.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">By default the recommended option is selected</div>
  <img src="/assets/images/install-git-08.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Most of the time OpenSSL is selected</div>
  <img src="/assets/images/install-git-09.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Use the default setting</div>
  <img src="/assets/images/install-git-10.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Use the default setting</div>
  <img src="/assets/images/install-git-11.png" style="width:100%">
</div>
<div class="mySlides fade">
 <div style="text-align:center">Use the default setting</div>
  <img src="/assets/images/install-git-12.png" style="width:100%">
</div>
<div class="mySlides fade">
 <div style="text-align:center">Use the default setting</div>
  <img src="/assets/images/install-git-13.png" style="width:100%">
</div>
<div class="mySlides fade">
 <div style="text-align:center">Use the default setting</div>
  <img src="/assets/images/install-git-14.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Use the default setting</div>
  <img src="/assets/images/install-git-15.png" style="width:100%">
</div>
<div class="mySlides fade">
  <div style="text-align:center">Viola yoo have just installed Git in your Windows machine</div>
  <img src="/assets/images/install-git-16.png" style="width:100%">
</div>

<a class="prev" onclick="plusSlides(-1)">❮</a>
<a class="next" onclick="plusSlides(1)">❯</a>

</div>
<br>
<div style="text-align:center">
  <span class="dot" onclick="currentSlide(1)"></span> 
  <span class="dot" onclick="currentSlide(2)"></span> 
  <span class="dot" onclick="currentSlide(3)"></span> 
  <span class="dot" onclick="currentSlide(4)"></span> 
  <span class="dot" onclick="currentSlide(5)"></span> 
  <span class="dot" onclick="currentSlide(6)"></span> 
  <span class="dot" onclick="currentSlide(7)"></span> 
  <span class="dot" onclick="currentSlide(8)"></span> 
  <span class="dot" onclick="currentSlide(9)"></span>  
  <span class="dot" onclick="currentSlide(10)"></span> 
  <span class="dot" onclick="currentSlide(11)"></span> 
  <span class="dot" onclick="currentSlide(12)"></span> 
  <span class="dot" onclick="currentSlide(13)"></span> 
  <span class="dot" onclick="currentSlide(14)"></span> 
  <span class="dot" onclick="currentSlide(15)"></span> 
</div>
<br/>
# What's next?
* Installing Git in Windows is straightforward using the installer
* Go to command prompt, type ```git version``` to verify if it was successfully installed
* To learn more about git visit [https://git-scm.com/doc](https://git-scm.com/doc)


<script>
let slideIndex = 1;
showSlides(slideIndex);

function plusSlides(n) {
  showSlides(slideIndex += n);
}

function currentSlide(n) {
  showSlides(slideIndex = n);
}

function showSlides(n) {
  let i;
  let slides = document.getElementsByClassName("mySlides");
  let dots = document.getElementsByClassName("dot");
  if (n > slides.length) {slideIndex = 1}    
  if (n < 1) {slideIndex = slides.length}
  for (i = 0; i < slides.length; i++) {
    slides[i].style.display = "none";  
  }
  for (i = 0; i < dots.length; i++) {
    dots[i].className = dots[i].className.replace(" active", "");
  }
  slides[slideIndex-1].style.display = "block";  
  dots[slideIndex-1].className += " active";
}
</script>

# How to create mockup from https://www.coinmarketplus.com/ page?

This guide describes how to add slider(carousel) to https://www.coinmarketplus.com/ page.

## Prerequisites
### Step 1
Download index.html document from the web page and save it to the empty folder
![Alt text](/doc/prerequisites_step1.png?raw=true)
### Step 2
In the root directory of our project create two more folders such as "fonts" and "images".
![Alt text](/doc/prerequisites_step2.png?raw=true)
### Step 3
Add four pictures in "images" directory, that you are going to use to create slider.
![Alt text](/doc/prerequisites_step3.png?raw=true)
### Step 4
Download the .ttf file of the Open Sans regular font using https://fonts.google.com/specimen/Open+Sans?selection.family=Open+Sans and save it to the "fonts" directory
![Alt text](/doc/prerequisites_step4.1.png?raw=true)
![Alt text](/doc/prerequisites_step4.2.png?raw=true)
## Adding code
### Step 1
Open the index.html file
### Step 2
Find the 'style' tag in the head and add the following code there, which will define visual appearance of the title and slider.
```
		@font-face {
			font-family: 'Open Sans';
			src: url("fonts/OpenSans-Regular.ttf");
		}

		.Live-Token a {
			font-family: Open Sans, sans-serif;
		}

		.slidesshow-container {
			max-width: 1024px;
			position:relative;
			margin:auto;
		}

		.prev, .next {
			cursor:pointer;
			position: absolute;
			top: 350px;
			width:auto;
			margin-top: -22px;
			padding: 16px;
			color:black;
			font-weight: bold;
			font-size:40px;
			transition: 0.6 ease;
		}
		.next{
			right:0;
		}

		.prev {
			left:0;
		}
		
		.mySlides img{
			display: block;
			margin:auto!important;
				height:100%;
		}
		.mySlides{
			height: 600px;
			vertical-align: middle;

		}
		.dot{
		cursor:pointer;
		height: 13px;
		width:13px;
		margin: 0 2px;
		background: #bbb;
		border-radius: 50%;
		display: inline-block;
		transition: background-color 0.6s ease;
		}

		.active {
			background-color: #717171;
		}
		
		.dot:hover{
			background-color: #717171;
		}

		.fades{
		animation-name:fade;
		animation-duration: 1.5s;
		}

		@keyframes fade {
			from{opacity:.4}
			to{opacity:1}
		}
```
![Alt text](/doc/adding_code_step2.png?raw=true)
### Step 3
Find the 'a' tag inserted in 'h1' tag that has class - "Live-Token" and change the title of your article. 
![Alt text](/doc/adding_code_step3.png?raw=true)
### Step 4
Right before 'h1' tag with the class name "Live-Token" add the following html code that will represent slider.
```
	<div class="slideshow-container">
        	<div class="mySlides fades" >
        		<img src="images/bitcoin1.jpg" style="width: 80% ;" align="middle" alt="">
        	</div>
        	<div class="mySlides fades" style="display:none">
        		<img src="images/bitcoin2.jpg" style="width: 80%" alt="">
        	</div>
        	<div class="mySlides fades" style="display:none">
        		<img src="images/bitcoin3.jpg" style="width: 80%" alt="">
        	</div>
        	<div class="mySlides fades" style="display:none">
        		<img src="images/bitcoin4.jpg" style="width: 80%" alt="">
        	</div>
       		<a class="prev" onclick="plusSlides(-1)">&#10094</a>
    		<a class="next" onclick="plusSlides(1)">&#10095</a>
        </div>
        <br>
        <div  style="text-align: center;">
        	<span class="dot" onclick="currentSlide(1)"></span>
        	<span class="dot" onclick="currentSlide(2)"></span>
        	<span class="dot" onclick="currentSlide(3)"></span>
        	<span class="dot" onclick="currentSlide(4)"></span>
        </div>
```
![Alt text](/doc/adding_code_step4.png?raw=true)
### Step 5
Finnaly, right before 'body' tag closes add the following script tag that will describe slider behaviour 
```
<script>
	var slideIndex = 1;
	showSlides(slideIndex);
	function plusSlides(n){
		showSlides(slideIndex+=n);
	}
	function currentSlide(n){
		showSlides(slideIndex=n);
	}
	function showSlides(n){
		var i;
		var slides = document.getElementsByClassName("mySlides");
		var dots = document.getElementsByClassName("dot");
		if(n>slides.length){
			slideIndex = 1;
		}
		if(n<1){
			slideIndex = slides.length;
		}
		for ( var i=0; i<slides.length; i++){
			slides[i].style.display = "none";
		}

		for(var i=0; i<dots.length; i++){
			dots[i].classList.remove("active");
		}
		slides[slideIndex-1].style.display = "block";
		dots[slideIndex-1].classList.add("active") ;
	}
</script>
```
![Alt text](/doc/adding_code_step5.png?raw=true)
## Finnaly
### Step 1
Create new repository on github.
### Step 2
Push your project.

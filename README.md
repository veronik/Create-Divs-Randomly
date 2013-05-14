Create-Divs-Randomly
====================
<!doctype html>
<html lang="en">
<head>
    <title>JavaScript-HomeWork</title>
    <meta charset="utf-8" />
    <style>
      button{
        background-color: #000;
      	color: #fff;
      	font-weight: bold;
      	margin: 20px 0 0 20px;
      	padding: 5px 10px;
      	border: 1px solid #000;
      	border-radius: 5px;
      }
      #containerDivs{
      	width: 1000px;
      	height: 500px;
      	border: 3px solid #000;
      	margin: 30px auto;
      	position: relative;
      }
      div{
      	text-align: center;
      }
    </style>
</head>
<body>
  <button id="buttonStart">Start</button>
	<button id="buttonStop">Stop</button>
	<div id="containerDivs">
	</div>
  <script type="text/javascript">
      (function(){  
      	var buttonStart = document.getElementById("buttonStart");
      	buttonStart.addEventListener("click",function(e){
      		start = setInterval(function(){createDivs()},500);
      	});
      	
      	var buttonStop = document.getElementById("buttonStop");
      	buttonStop.addEventListener("click",function(e){
      		var int=window.clearInterval(start);
      	});
      }());
      
      function createDivs(){
      	var wrapperDiv = document.getElementById("containerDivs");
      	var createDiv = document.createElement("div");
      	var createStrong = document.createElement("strong");
      	createStrong.innerHTML  = "div"
      	createDiv.appendChild(createStrong);
      	styleDiv(createDiv);
      	wrapperDiv.appendChild(createDiv);
      	return
      }
      
      function styleDiv(div) {
      	var width = generateWidth();
      	div.style.width = width + "px";
      	
      	var height =  generateHeight();
      	div.style.height = height + "px";
      	
      	var borderWidth =  generateBorderWidth();
      	var borderColor = generateRandomColor();
      	div.style.border = borderWidth + "px solid " + borderColor;
      	
      	div.style.backgroundColor = generateRandomColor();
      	div.style.color = generateRandomColor();
      	div.style.borderRadius = generateBorderRadius();
      	
      	div.style.position = "absolute";
      	var topPos = parseInt(Math.random() * (500 - height - (2*borderWidth)));
      	div.style.top = topPos + "px";
      	var left = parseInt(Math.random() * (1000 - width - (2*borderWidth)));
      	div.style.left = left + "px";
      }
      
      function generateRandomColor(){
      	var red = (Math.random() * 256) | 0;
      	var green = (Math.random() * 256) | 0;
      	var blue = (Math.random() * 256) | 0;
      
      	return "rgb(" + red + "," + green + "," + blue + ")";
      }
      
      function generateWidth(){
      	var width = (Math.random() * 100) | 20;
      	return width;
      }
      
      function generateHeight(){
      	var height = (Math.random() * 100) | 20;
      	return height;
      }
      
      function generateBorderRadius(){
      	var radius = (Math.random() * 20) | 0;
      	return radius + "px";
      }
      
      function generateBorderWidth(){
      	var width = (Math.random() * 20) | 1;
      	return width;
      }
  </script>   
</body>
</html>

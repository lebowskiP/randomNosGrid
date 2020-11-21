# randomNosGrid

1. Its a static HTML page with 12 boxes(divs) fashioned in 3x4 grid manner.
2. Every box has a randomly generated integer in [1,100].
3. If the integer is less than 10, the box becomes blue. (OR) If the integer is more than 10, the box becomes red.

### HTML Markup
```html
<!DOCTYPE html>
<html>
<head>
	<title>Grids</title>
</head>
<body onload="randomNoGenerator()">
	<div id="main" class='wrapper'>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
		<div class="box">
			<p class="nos"></p>
		</div>
	</div>
</body>
</html>
```
## CSS
```CSS
		body,html {
			padding: 0;
			margin: 0;
		}
		.wrapper {
			display: grid;
			grid-template-columns: 1fr 1fr 1fr 1fr;
			grid-template-rows: 1fr 1fr 1fr;
			grid-row-gap: 1em;
			grid-column-gap: 1em;
			background-color: black;

		}
		.box {
			background-color: #0069b3;
			display: flex;
			justify-content: center;
			align-items: center;
			padding: 20px;
			font-size: 70px;
			color: white;
			line-height: 1;
			font-weight: 200;
			cursor: pointer;
			transition: all .3s ease;
			
			border-radius: 6px;
		}
		.box:hover{
			background-color: #0069ff;
		}
```
## JavaScript
```JavaScript
		var myVar = setInterval(randomNoGenerator, 400);
		function randomNoGenerator() {
			var i=0;
			while(i<12){
				var y = document.getElementsByClassName("box")[i];
                var z = y.getElementsByClassName("nos")[0];
				z.innerHTML = Math.floor((Math.random() * 100) + 1);
                if(z.innerHTML > 10){
                	y.style.backgroundColor = "red";
                }
                else y.style.backgroundColor = "#0069b3";
				i++;
			}
		}
```

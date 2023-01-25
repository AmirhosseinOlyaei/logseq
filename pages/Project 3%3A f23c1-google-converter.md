- **f23c1-google-converter**
- An app that converts from Fahrenheit to Degree Celsius like Google's mini-app
- Algorithms:
	- Design a set of instructions to solve a problem
		- >1. Get data from the user
		  2. When I get the data? to convert to F
		  3. [?] What data from the user
		  4. [?] What sort of formula?
		  5. Show the user the result
			- > **Get data from the user**
				- Data type
					- >1. Number
						- ```js
						  const userInput = 23;
						  const userInput = 24.5;
						  ```
						- `var` makes variables global
						- `const` are used to declare variables that cannot be reassigned after they are initialized.
					- >2. String
						- ```js
						  const appName = "Google Converter";
						  const appVersion = "0.0.1";
						  const isANewApp = "false";
						  typeof (typeof (answer));
						  ```
					- >3. Boolean
						- ```js
						  const isANewApp = true;
						  ```
				- >**Making decisions:**
					- >4. Conditional Operators;
						- equal?`===`, `==`, `=`, not equal`!==`, `>`, `<`
					-
					- >5. Conditional statements;
						- ```js
						  const isNewApp = true;
						  if (typeof (answer) === "number"){
						  	console.log("This is your conversation");
						  }
						  if(typeof(answer) === "string"){
						  	console.log("")
						  }
						  ```
			- >**Convert to F**
				- ```txt
				  (23C x 9.5) + 32 = 73.4F
				  
				  console.log(
				  	userInput / userInputOne
				  )
				  ```
			-
	- ```js
	   const userInput = 40;
	   const results = (userInput - 32) * (5 / 9);
	   console.log(
	     userInput + "°F = " + results + "°C"
	   );
	  ```
	- ```js
	  let fahrenheit = prompt("Enter a temperature in Fahrenheit:");
	  let celsius = (fahrenheit - 32) * (5 / 9);
	  console.log(fahrenheit + " degrees Fahrenheit is equal to " + celsius + " degrees Celsius.");
	  ```
	- ```js
	  document.getElementById("demo").innerHTML = "Formula: (" + userInput + boldText + " - 32) × 5 / 9 = " + results + "<b>°C</b>";
	  ```
	- ```js
	  const fehrenheit = "°F";
	  const boldFehrenheit = fehrenheit.bold();
	  const userInput = 74; //prompt("Enter a temperature in " + fehrenheit);
	  const results = (userInput - 32) * (5 / 9); //.toFixed(2);
	  const roundedResults = Math.round(results*100)/100;
	  console.log(
	    userInput + "°F = " + roundedResults + "°C"
	  );
	  console.log(
	    "Formula: (" + userInput + "°F - 32) × 5 / 9 = " + roundedResults + "°C"
	  );
	  document.getElementById("demo").innerHTML = 
	  `<span style='background-color: orange;'>Formula</span> ( ${userInput}${boldFehrenheit} - 32) × 5 / 9 = ${roundedResults}<b>°C</b>`;
	  ```
-
- [[Jetbrains]]
	- https://www.jetbrains.com/lp/devecosystem-2022/
	- Here’s the starting point to solve the Google converter problem: [https://jsitor.com/Qg9XumxV2L](https://jsitor.com/Qg9XumxV2L)
-
- [[Template literals]]
	- https://developer.mozilla.org/en-US/docs/Web/JavaScript/Reference/Template_literals
-
- [[Deliberate practice]]
	- is defined as **being effortful in nature, with the main goal of personal improvement of performance rather than enjoyment, and is often performed without immediate reward**. From: Performance Psychology, 2011.
-
- [[GitHub issues]]
	- https://robinpowered.com/blog/best-practice-system-for-organizing-and-tagging-github-issues
-
- https://playcode.io/1092856 Dele's sample code
- https://jsitor.com/xTWbs1cnrZ my progress
-
- ```html
  <!DOCTYPE html>
  <html lang="en">
  
  <head>
  	<meta charset="UTF-8">
  	<meta http-equiv="X-UA-Compatible" content="IE=edge">
  	<meta name="viewport" content="width=device-width, initial-scale=1.0">
  	<title>Google Mini Temp Converter</title>
    <script src="https://cdn.tailwindcss.com"></script></head>
  
  <body>
  	<h1 class="text-2xl m-4">Google Temperature Unit Converter</h1>
  
  	<div class="border w-[40rem] rounded-md ml-6">
  		<!-- Select a unit category to convert -->
  		<select name="units" id="unitSelect" class="bg-[#f8f9fa] border rounded-md w-3/4 m-4 text-sm py-1.5">
  			<option value="">Please choose an option</option>
  			<option value="Temperature" selected>Temperature</option>
  		</select>
  		<!-- Temperature unit convertor area -->
  		<div class="flex w-4/5">
  			<div class="flex flex-col m-4">
  				<!-- Fahrenheit to Celsius -->
  				<input type="number" value="32" id="inputFah"
  					class="border w-full text-2xl text-center p-1.5 focus:outline-none">
  				<select name="units" id="unitSelected" class="bg-[#f8f9fa] border rounded-b-sm w-full text-sm py-1.5">
  					<option value="Celsius">Degree Celsius</option>
  					<option value="Fahrenheit" selected>Fahrenheit</option>
  					<option value="Kelvin">Kelvin</option>
  				</select>
  			</div>
  			<div class="flex items-center text-2xl">=</div>
  			<div class="flex flex-col m-4">
  				<!-- Celsius to Fahrenheit -->
  				<input type="number" value="0" id="inputCel"
  					class="border w-full text-2xl text-center p-1.5 focus:outline-none">
  				<select name="units" id="unitConverted" class="bg-[#f8f9fa] border rounded-b-sm w-full text-sm py-1.5">
  					<option value="Celsius" selected>Degree Celsius</option>
  					<option value="Fahrenheit">Fahrenheit</option>
  					<option value="Kelvin">Kelvin</option>
  				</select>
  			</div>
  		</div>
  		<div>
  			<!-- Show results within its formula  -->
  			<p id="demo" class="m-4 text-sm"></p>
  			<p id="demo2" class="m-4 text-sm"></p>
  		</div>
  	</div>
  	<a href="#" class="ml-9"><small>More info</small></a>
  </body>
  
  </html>
  ```
- ```js
  // Fahrenheit to Celsius
  const userFahElement = document.getElementById('inputFah');
  const userDemoElement = document.getElementById('demo');
  userFahElement.addEventListener("change", function(){
    const userFahNum = Number(userFahElement.value);
    const convertToCel = (userFahNum - 32) * (5 / 9); 
    const roundedConvertToCel = Math.round(convertToCel*100)/100;
    userDemoElement.innerHTML = `<span class="bg-[#f9ab00]">Formula</span> ( ${userFahNum}<b>°F</b> - 32) × 5 / 9 = ${roundedConvertToCel}<b>°C</b>`;
    document.getElementById('inputCel').value = roundedConvertToCel;
  });
  
  // Celsius to Fahrenheit
  const userCelElement = document.getElementById('inputCel');
  const userDemoElement2 = document.getElementById('demo2');
  userCelElement.addEventListener("change", function () {
    const userCelNum = Number(userCelElement.value);
    const convertToFah = (userCelNum * (9 / 5)) + 32;
    const roundedConvertToFah = Math.round(convertToFah*100)/100;
    document.getElementById('inputFah').value = roundedConvertToFah;
    userDemoElement.innerHTML = `<span class="bg-[#f9ab00]">Formula</span> ( ${roundedConvertToFah}<b>°F</b> - 32) × 5 / 9 = ${userCelNum}<b>°C</b>`;
    //userDemoElement2.innerHTML = `<span class="bg-[#f9ab00]">Formula</span> ( ${userCelNum}<b>°C</b> × 9 / 5 ) + 32 = ${roundedConvertToFah}<b>°F</b>`;
  });
  ```
- **f23c1-google-converter**
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
					- >4. Conditional Operators; `===`, `==`, `=`
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
		-
- https://www.jetbrains.com/lp/devecosystem-2022/
- Here’s the starting point to solve the Google converter problem: [https://jsitor.com/Qg9XumxV2L](https://jsitor.com/Qg9XumxV2L)
-
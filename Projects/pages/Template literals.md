- ```js
  console.log(
    "Formula: (" + userInput + "°F - 32) × 5 / 9 = " + roundedResults + "°C"
  );
  
  //using backticks in template literals to simplify strings.
  
  document.getElementById("demo").innerHTML = 
  `<span style='background-color: orange;'>Formula</span> ( ${userInput}${boldFehrenheit} - 32) × 5 / 9 = ${roundedResults}<b>°C</b>`;
  
  ```
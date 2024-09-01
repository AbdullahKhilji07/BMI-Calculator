HTML CODE FOR BMI CALCULATOR
<!DOCTYPE html>
<html>

<head>
    <!-- Include JS files -->
    <script src="./bmi.js"></script>
</head>

<body>
    <div class="container">
        <h1>BMI Calculator</h1>
<h3>HI MADAM!</h3>
        <!-- Option for providing height 
            and weight to the user-->
        <p>Height :(in cm)</p>

        <input type="text" id="height">

        <p>Weight :(in kg)</p>

        <input type="text" id="weight">

        <button id="btn">Calculate</button>

        <div id="result"></div>
    </div>
</body>
</html>


                                                                            JS CODE FOR BMI CALC
window.onload = () => {
    let button = document.querySelector("#btn");
    
    // Function for calculating BMI
    button.addEventListener("click", calculateBMI);
    };
    
    function calculateBMI() {
    
    /* Getting input from user into height variable.
    Input is string so typecasting is necessary. */
    let height = parseInt(document
            .querySelector("#height").value);
    
    /* Getting input from user into weight variable. 
    Input is string so typecasting is necessary.*/
    let weight = parseInt(document
            .querySelector("#weight").value);
    
    let result = document.querySelector("#result");
    
    // Checking the user providing a proper
    // value or not
    if (height === "" || isNaN(height)) 
        result.innerHTML = "Provide a valid Height!";
    
    else if (weight === "" || isNaN(weight)) 
        result.innerHTML = "Provide a valid Weight!";
    
    // If both input is valid, calculate the bmi
    else {
    
        // Fixing upto 2 decimal places
        let bmi = (weight / ((height * height) 
                            / 10000)).toFixed(2);
    
        // Dividing as per the bmi conditions
        if (bmi < 18.6) result.innerHTML =
            `Under Weight : <span>${bmi}</span>`;
    
        else if (bmi >= 18.6 && bmi < 24.9) 
            result.innerHTML = 
                `Normal : <span>${bmi}</span>`;
    
        else result.innerHTML =
            `Over Weight : <span>${bmi}</span>`;
    }
    }


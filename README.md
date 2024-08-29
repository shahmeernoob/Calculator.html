<!DOCTYPE html>
<html lang="en">

<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Document</title>
    <style>
        .btn-1{
            padding: 4px 2px;
            margin: 4px 0px;
        }

        .w-1{
            width: 125px;
        }
    </style>

</head>

<body>
        <input class="w-1" type="text" value="" id="ans">

    
    <div onclick="che()" class="btn-1" id="demo1"></div>
    

    <script>

    let display = document.getElementById("ans");
let box = document.getElementById("demo1");

let arry = [1, 2, 3, 4, 5, 6, 7, 8, 9, "+", "-", "*", "/", "=", "C"];


let currentInput = "";
let operation = "";


arry.forEach((e) => {
    let btn = document.createElement("button");
    btn.innerText = e;
    btn.addEventListener('click', () => handleClick(e));
    box.append(btn);
});


function handleClick(value) {
    if (value === "C") {
        
        currentInput = "";
        operation = "";
        display.value = "";
    } else if (value === "=") {
        
        try {
            currentInput = calculate(operation).toString();
            operation = currentInput; 
            display.value = currentInput;
        } catch (error) {
            display.value = "Error";
            operation = "";
        }
    } else {
        
        operation += value;
        display.value = operation;
    }
}


function calculate(){
    var res = [];
    var answer;
    
    if(document.getElementById("ans").value.includes("+")){
    res = document.getElementById("ans").value.split('+');
    return parseFloat(res[0]) + parseFloat(res[1]);
    }
    
    else if(document.getElementById("ans").value.includes("-")){
    res = document.getElementById("ans").value.split('-');
    return parseFloat(res[0]) - parseFloat(res[1]);
    }
    
    else if(document.getElementById("ans").value.includes("/")){
    res = document.getElementById("ans").value.split('/');
    return parseFloat(res[0]) / parseFloat(res[1]);
    }
    
    else{
    res = document.getElementById("ans").value.split('*');
    return answer= parseFloat(res[0]) * parseFloat(res[1]);
    }
}
    </script>  
    
       
   
</body>
</html>

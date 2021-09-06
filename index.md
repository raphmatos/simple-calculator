
<html lang="en-GB">

    <head>        
        <title>Simple Calculator</title>
        <style>

           table {
                margin-left: auto;
                margin-right: auto;
                max-width: 500px;
                user-select: none;
                -moz-user-select: none;
                -khtml-user-select: none;
           }

           td, th {
                border: 1px solid black;
                text-align: center;
                padding: 5px 20px 5px 20px;
                width: 25%;
                color: white;
                background-color: darkslateblue;
                font-size: large;
                font-family: Arial, Helvetica, sans-serif;
                text-shadow:1px 1px 3px black;    
            }

            th{
                font-size: 40px;
            }

            td:hover {
                background-color: rgba(72,61,139, 0.5);
            }

            td:active {
                background-color: rgba(72,61,139, 0.7);
            }

            td:link, td:visited, .resultLine:hover, .resultLine:active, .resultLine:link, .resultLine:visited {
                background-color: darkslateblue;
            }

            #result {
                background-color: darkslateblue;
                color: white;
                font-size: 40px;
                text-align: right;
                text-shadow:1px 1px 3px black;
                border: none;
            }

            #memoryField {
                background-color: darkslateblue;
                color: white;
                font-size: 20px;
                text-align: right;
                text-shadow:1px 1px 3px black;
                border: none;
            }

        </style>

    </head>

    <body>

            <script>

                let memory = new Number(0), entry1 = new Number(0), entry2 = new Number(0), entry2Zeros = new Number(0), entry = new Number(0), digit = new Number(0);

                let hasPoint = new Boolean(false);

                const maxDigits = 15;

                let operator = "none";

                function num (event){


                        if(event.target.innerHTML == "."){
                            if(hasPoint == false) { hasPoint = true; document.getElementById("result").value = entry1.toString() + "."}
                        } else {
                              if(document.getElementById("result").value.length < maxDigits || document.getElementById("result").value == "Unable to divide by zero!") {
                                if(event.target.innerHTML == "0"){ digit = 0;}
                                else if(event.target.innerHTML == "1"){ digit = 1;}
                                else if(event.target.innerHTML == "2"){ digit = 2;}
                                else if(event.target.innerHTML == "3"){ digit = 3;}
                                else if(event.target.innerHTML == "4"){ digit = 4;}
                                else if(event.target.innerHTML == "5"){ digit = 5;}
                                else if(event.target.innerHTML == "6"){ digit = 6;}
                                else if(event.target.innerHTML == "7"){ digit = 7;}
                                else if(event.target.innerHTML == "8"){ digit = 8;}
                                else if(event.target.innerHTML == "9"){ digit = 9;}

                                if(hasPoint == true){
                                    if(entry2 == 0 && digit == 0){ entry2Zeros++; } else { entry2 = (entry2 * 10) + digit; }
                                    entry = entry1 + (entry2 / (10 ** (entry2.toString().length + entry2Zeros)));
                                    document.getElementById("result").value = entry1.toString() + "." + "0".repeat(entry2Zeros);
                                    if(entry2 != 0) { document.getElementById("result").value = document.getElementById("result").value + entry2.toString(); }
                                } else {
                                    entry1 = (entry1 * 10) + digit;
                                    entry = entry1;
                                    document.getElementById("result").value = entry.toString();
                                }
                        }
                    }
                }

                function calc (event){
                    if(event.target.innerHTML == "ClearEntry"){ entry1 = entry2 = entry = entry2Zeros = 0; hasPoint = false; document.getElementById("result").value = "0";}
                    if(event.target.innerHTML == "ClearAll"){ entry1 = entry2 = entry = entry2Zeros = memory = 0; operator = "none"; hasPoint = false; document.getElementById("result").value = "0"; document.getElementById("memoryField").value = "";}
                    if(event.target.innerHTML == "ClearDigit"){
                        entry = Number(entry.toString().slice(0, -1));
                        if(Number.isInteger(entry) && entry2Zeros == 0){
                            hasPoint = false;
                            entry2 = entry2Zeros = 0;
                            entry1 = entry;
                            document.getElementById("result").value = entry.toString();
                        }else{
                            if(entry2 == 0) { entry2Zeros--; } else { entry2 = Number(entry2.toString().slice(0, -1)); }
                            document.getElementById("result").value = entry1.toString() + "." + "0".repeat(entry2Zeros);
                            if(entry2 > 0) { document.getElementById("result").value = document.getElementById("result").value + entry2.toString(); }
                        }
                    }
                    if(event.target.innerHTML == "√X"){
                        entry = Math.sqrt(entry);
                        entry1 = Math.trunc(entry);
                        if(Number.isInteger(entry)) {
                            hasPoint = false;
                            entry2 = entry2Zeros = 0;
                        } else {
                            hasPoint = true;
                            entry2 = Number(entry.toString().substring(entry.toString().indexOf(".") + 1));
                            entry2Zeros = entry.toString().length - 1 - entry1.toString().length - entry2.toString().length;
                        }
                        if(entry == 0) { document.getElementById("result").value = "0"; } else { 
                            if(entry.toString().length > maxDigits){ document.getElementById("result").value = entry.toString().substring(0, maxDigits); 
                            } else { document.getElementById("result").value = entry.toString(); }
                        }
                    }

                     if(event.target.innerHTML == "X<sup>2</sup>"){
 
                        entry = entry**2;
                        entry1 = Math.trunc(entry);
                        if(Number.isInteger(entry)) {
                            hasPoint = false;
                            entry2 = entry2Zeros = 0;
                        } else {
                            hasPoint = true;
                            entry2 = Number(entry.toString().substring(entry.toString().indexOf(".") + 1));
                            entry2Zeros = entry.toString().length - 1 - entry1.toString().length - entry2.toString().length;
                        }
                        if(entry == 0) { document.getElementById("result").value = "0"; } else {
                            if(entry.toString().length > maxDigits){ document.getElementById("result").value = entry.toString().substring(0, maxDigits); 
                            } else { document.getElementById("result").value = entry.toString(); }
                            }

                     }

                     if(event.target.innerHTML == "1/X"){
                        if(entry != 0){
                        entry = 1/entry;
                        entry1 = Math.trunc(entry);
                        if(Number.isInteger(entry)) {
                            hasPoint = false;
                            entry2 = entry2Zeros = 0;
                        } else {
                            hasPoint = true;
                            entry2 = Number(entry.toString().substring(entry.toString().indexOf(".") + 1));
                            entry2Zeros = entry.toString().length - 1 - entry1.toString().length - entry2.toString().length;
                        }
                        if(entry == 0) { document.getElementById("result").value = "0"; } else {
                            if(entry.toString().length > maxDigits){ document.getElementById("result").value = entry.toString().substring(0, maxDigits); 
                            } else { document.getElementById("result").value = entry.toString(); }
                            }

                    } else {
                            document.getElementById("result").value = "Unable to divide by zero!";
                        }    
                }

                if(event.target.innerHTML == "%"){
                    if(operator = "none"){
                        entry = entry/100;
                    } else if(operator == "+"){
                        entry = memory + memory*(entry)/100;
                    } else if(operator == "-") {
                        entry = memory - memory*(entry)/100;
                    } else if(operator == "×"){
                        entry = memory * memory*(entry)/100;
                    } else if(operator == "÷"){
                        entry = memory / memory*(entry)/100;
                    }

                    entry1 = Math.trunc(entry);
                        if(Number.isInteger(entry)) {
                            hasPoint = false;
                            entry2 = entry2Zeros = 0;
                        } else {
                            hasPoint = true;
                            entry2 = Number(entry.toString().substring(entry.toString().indexOf(".") + 1));
                            entry2Zeros = entry.toString().length - 1 - entry1.toString().length - entry2.toString().length;
                        }
                        if(entry == 0) { document.getElementById("result").value = "0"; } else {
                            if(entry.toString().length > maxDigits){ document.getElementById("result").value = entry.toString().substring(0, maxDigits); 
                            } else { document.getElementById("result").value = entry.toString(); }
                        }
                }

                if(event.target.innerHTML == "+"){
                    operator = "+";
                    memory = entry;
                    entry1 = entry2 = entry = entry2Zeros = 0; hasPoint = false;
                    document.getElementById("memoryField").value = memory.toString() + " + ";
                }

                if(event.target.innerHTML == "-"){
                    operator = "-";
                    memory = entry;
                    entry1 = entry2 = entry = entry2Zeros = 0; hasPoint = false;
                    document.getElementById("memoryField").value = memory.toString() + " - ";
                }

                if(event.target.innerHTML == "×"){
                    operator = "×";
                    memory = entry;
                    entry1 = entry2 = entry = entry2Zeros = 0; hasPoint = false;
                    document.getElementById("memoryField").value = memory.toString() + " × ";
                }

                if(event.target.innerHTML == "÷"){
                    operator = "÷";
                    memory = entry;
                    entry1 = entry2 = entry = entry2Zeros = 0; hasPoint = false;
                    document.getElementById("memoryField").value = memory.toString() + " ÷ ";
                }

                if(event.target.innerHTML == "="){
                    if(entry == 0 && operator == "÷"){
                        memory = entry = entry1 = entry2 = entry2Zeros = 0;
                        hasPoint = false;
                        operator = "none";
                        document.getElementById("result").value = "Unable to divide by zero!";
                        document.getElementById("memoryField").value = "";
                    } else {

                    if(operator == "+"){
                        entry = memory + entry;
                    } else if(operator == "-") {
                        entry = memory - entry;
                    } else if(operator == "×"){
                        entry = memory * entry;
                    } else if(operator == "÷"){
                            entry = memory / entry;
                    }
                        memory = 0;
                        operator = "none";
                        entry1 = Math.trunc(entry);
                        if(Number.isInteger(entry)) {
                            hasPoint = false;
                            entry2 = entry2Zeros = 0;
                        } else {
                            hasPoint = true;
                            entry2 = Number(entry.toString().substring(entry.toString().indexOf(".") + 1));
                            entry2Zeros = entry.toString().length - 1 - entry1.toString().length - entry2.toString().length;
                        }
                        if(entry == 0) { document.getElementById("result").value = "0"; } else {
                            if(entry.toString().length > maxDigits){ document.getElementById("result").value = entry.toString().substring(0, maxDigits); 
                            } else { document.getElementById("result").value = entry.toString(); }
                            }
                            document.getElementById("memoryField").value = "";
                    }
                }
                
            }

            </script>

            <table>
                <tr><th colspan="4">Simple Calculator ±</th></tr>
                <tr class="resultLine"><td colspan="4"><input type="text" readonly disabled value="" id="memoryField"></td></tr>
                <tr class="resultLine"><td colspan="4"><input type="text" readonly disabled value="0" id="result"></td></tr>
                <tr><td onclick='num(event)'>.</td><td onclick='calc(event)'>ClearDigit</td><td onclick='calc(event)'>ClearEntry</td><td onclick='calc(event)'>ClearAll</td></tr>
                <tr><td onclick='num(event)'>0</td><td onclick='num(event)'>5</td><td onclick='calc(event)'>+</td><td onclick='calc(event)'>%</td></tr>
                <tr><td onclick='num(event)'>1</td><td onclick='num(event)'>6</td><td onclick='calc(event)'>-</td><td onclick='calc(event)'>X<sup>2</sup></td></tr>
                <tr><td onclick='num(event)'>2</td><td onclick='num(event)'>7</td><td onclick='calc(event)'>&#215;</td><td onclick='calc(event)'>&#8730;X</td></tr>
                <tr><td onclick='num(event)'>3</td><td onclick='num(event)'>8</td><td onclick='calc(event)'>&#247;</td><td onclick='calc(event)'>1/X</td></tr>
                <tr><td onclick='num(event)'>4</td><td onclick='num(event)'>9</td><td onclick='calc(event)' colspan="2">=</td></tr>
            </table>

    </body>

</html>

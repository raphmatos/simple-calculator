
<html lang="en-GB">

    <head>        
        <title>Simple Calculator</title>
        <style>

            table{
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

            #result {
                background-color: darkslateblue;
                color: white;
                font-size: 40px;
                text-align: center;
                text-shadow:1px 1px 3px black;
            }

            td:hover {
                background-color: rgba(72,61,139, 0.5);
            }

            td:active {
                background-color: rgba(72,61,139, 0.7);
            }

            td:link, td:visited, .resultline:hover, .resultline:active, .resultline:link, .resultline:visited {
                background-color: darkslateblue;
            }

        </style>

    </head>

    <body>

            <script>

                var entry1 = 0;
                var entry2 = 0;
                var digit = 0;

                function point (event){
                    alert("point");
                }
                function cleardigit (event){
                    alert("cleardigit");
                }
                function clearentry (event){
                    alert("clearentry");
                }
                function clearall (event){
                    alert("clearall");
                }
                function num (event){
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

                    document.getElementById("result").value = digit;
                }
                function plus (event){
                    alert("plus");
                }
                function percentage (event){
                    alert("percentage");
                }
                function minus (event){
                    alert("minus");
                }
                function squared (event){
                    alert("squared");
                }
                function times (event){
                    alert("times");
                }
                function root (event){
                    alert("root");
                }
                function division (event){
                    alert("division");
                }
                function inversion (event){
                    alert("inversion");
                }
                function process (event){
                    alert("process");
                }
                
            </script>

    <!--
        Buttons:
        point / cleardigit / clearentry / clearall
        zero / five / plus / percentage
        one / six / minus / squared
        two / seven / times / root
        three / eight / division / inversion
        four / nine / process
    -->
            <table>
                <tr><th colspan="4">Simple Calculator</th></tr>
                <tr class="resultline"><td colspan="4"><input type="text" readonly disabled maxlength="16" value="0" id="result"></td></tr>
                <tr><td onclick='point(event)'>.</td><td onclick='cleardigit(event)'>ClearDigit</td><td onclick='clearentry(event)'>ClearEntry</td><td onclick='clearall(event)'>ClearAll</td></tr>
                <tr><td onclick='num(event)'>0</td><td onclick='num(event)'>5</td><td onclick='plus(event)'>+</td><td onclick='percentage(event)'>%</td></tr>
                <tr><td onclick='num(event)'>1</td><td onclick='num(event)'>6</td><td onclick='minus(event)'>-</td><td onclick='squared(event)'>X<sup>2</sup></td></tr>
                <tr><td onclick='num(event)'>2</td><td onclick='num(event)'>7</td><td onclick='times(event)'>&#215;</td><td onclick='root(event)'>&#8730;X</td></tr>
                <tr><td onclick='num(event)'>3</td><td onclick='num(event)'>8</td><td onclick='division(event)'>&#247;</td><td onclick='inversion(event)'>1/X</td></tr>
                <tr><td onclick='num(event)'>4</td><td onclick='num(event)'>9</td><td onclick='process(event)' colspan="2">=</td></tr>
            </table>

    </body>

</html>

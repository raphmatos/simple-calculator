
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
                function zero (event){
                    document.getElementById("result").value = 0;
                }
                function five (event){
                    document.getElementById("result").value = 5;
                }
                function plus (event){
                    alert("plus");
                }
                function percentage (event){
                    alert("percentage");
                }
                function one (event){
                    document.getElementById("result").value = 1;
                }
                function six (event){
                    document.getElementById("result").value = 6;
                }
                function minus (event){
                    alert("minus");
                }
                function squared (event){
                    alert("squared");
                }
                function two (event){
                    document.getElementById("result").value = 2;
                }
                function seven (event){
                    document.getElementById("result").value = 7;
                }
                function times (event){
                    alert("times");
                }
                function root (event){
                    alert("root");
                }
                function three (event){
                    document.getElementById("result").value = 3;
                }
                function eight (event){
                    document.getElementById("result").value = 8;
                }
                function division (event){
                    alert("division");
                }
                function inversion (event){
                    alert("inversion");
                }
                function four (event){
                    document.getElementById("result").value = 4;
                }
                function nine (event){
                    document.getElementById("result").value = 9;
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
                <tr><td onclick='zero(event)'>0</td><td onclick='five(event)'>5</td><td onclick='plus(event)'>+</td><td onclick='percentage(event)'>%</td></tr>
                <tr><td onclick='one(event)'>1</td><td onclick='six(event)'>6</td><td onclick='minus(event)'>-</td><td onclick='squared(event)'>X<sup>2</sup></td></tr>
                <tr><td onclick='two(event)'>2</td><td onclick='seven(event)'>7</td><td onclick='times(event)'>&#215;</td><td onclick='root(event)'>&#8730;X</td></tr>
                <tr><td onclick='three(event)'>3</td><td onclick='eight(event)'>8</td><td onclick='division(event)'>&#247;</td><td onclick='inversion(event)'>1/X</td></tr>
                <tr><td onclick='four(event)'>4</td><td onclick='nine(event)'>9</td><td onclick='process(event)' colspan="2">=</td></tr>
            </table>

    </body>

</html>

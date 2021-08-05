
<html lang="en-GB">

    <head>        
        <title>Simple Calculator</title>
        <style>

            table{
                margin-left: auto;
                margin-right: auto;
                max-width: 500px;
                table-layout: fixed;
            }

           td {
                border: 1px solid black;
                text-align: center;
                padding: 10px;
                width: 25%;
                color: white;
                background-color: darkslateblue;
                font-size: large;
                font-family: Arial, Helvetica, sans-serif;
                text-shadow:1px 1px 3px black;
            }

            .main {
                height: 50px;
                text-align: center;
            }

            .result {
                background-color: darkslateblue;
                color: white;
                font-size: 40px;
                text-align: center;
                text-shadow:1px 1px 3px black;
                width: 100%;
            }

        </style>
    </head>

    <body>
            <table>
                <tr><td colspan="4" class="main"><input type="text" readonly disabled maxlength="16" value="0.00" class="result"></td></tr>
                <tr><td>,</td><td>ClearDigit</td><td>ClearEntry</td><td>ClearAll</td></tr>
                <tr><td>0</td><td>5</td><td>+</td><td>%</td></tr>
                <tr><td>1</td><td>6</td><td>-</td><td>X<sup>2</sup></td></tr>
                <tr><td>2</td><td>7</td><td>&#215;</td><td>&#8730;X</td></tr>
                <tr><td>3</td><td>8</td><td>&#247;</td><td>1/X</td></tr>
                <tr><td>4</td><td>9</td><td colspan="2">=</td></tr>
            </table>
    </body>

</html>

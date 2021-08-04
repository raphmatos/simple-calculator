
<html lang="en-GB">

    <head>        
        <title>Simple Calculator</title>
        <style>

            table{
                margin-left: auto;
                margin-right: auto;
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

            th, tr {
                height: 50px;
                text-align: center;
            }

            .result {
                background-color: darkslateblue;
                color: white;
                font-size: 40px;
                text-align: center;
                text-shadow:1px 1px 3px black;
                padding-right: 20px;
            }

        </style>
    </head>

    <body>
            <table>
                <tr><th colspan="4"><input type="text" readonly maxlength="1000000000000000" value="0.00" size="20" class="result"></th></tr>
                <tr><td colspan="4"></td></tr>
                <tr><td>,</td><td>Clear Digit</td><td>Clear Entry</td><td>Clear All</td></tr>
                <tr><td>0</td><td>5</td><td>+</td><td>%</td></tr>
                <tr><td>1</td><td>6</td><td>-</td><td>X<sup>2</sup></td></tr>
                <tr><td>2</td><td>7</td><td>&#215;</td><td>&#8730;X</td></tr>
                <tr><td>3</td><td>8</td><td>&#247;</td><td>1/X</td></tr>
                <tr><td>4</td><td>9</td><td colspan="2">=</td></tr>
            </table>
    </body>

</html>

<html lang="en-GB">

    <head>        
        <title>Simple Calculator</title>
        <style>

           td, th {
                border: 1px solid black;
                text-align: center;
                padding: 10px;
                width: 25%;
                color: white;
                background-color: darkslateblue;
                font-size: large;
                font-family: Arial, Helvetica, sans-serif;
            }

            th{
                text-align: left;
                font-weight: normal;
            }


        </style>
    </head>

    <body>
        <table>
            <tr><th colspan="4">Result:</th></tr>
            <tr><td>,</td><td>Clear Last</td><td>Clear Entry</td><td>Clear All</td></tr>
            <tr><td>0</td><td>5</td><td>+</td><td>%</td></tr>
            <tr><td>1</td><td>6</td><td>-</td><td>X<sup>2</sup></td></tr>
            <tr><td>2</td><td>7</td><td>&#215;</td><td>&#8730;X</td></tr>
            <tr><td>3</td><td>8</td><td>&#247;</td><td>1/X</td></tr>
            <tr><td>4</td><td>9</td><td colspan="2">=</td></tr>
        </table>
    </body>

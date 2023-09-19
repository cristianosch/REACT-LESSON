<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="style.css">
    <title>Document</title>
</head>
<body>
    <h1>Destructing Arrays</h1>
    <p>Here is the old way of assigning array items to a variable:</p>
    <h2 class="red">Example</h2>
    <p class="blue">Before:</p>
    <div class="container">
        <div class="area">
            <p>const vehicles = ['mustang', 'f-150', 'expedition'];</p>

            <p class="blue">// old way</p>
            <p class="space">
            const car = vehicles[0];<br>
            const truck = vehicles[1];<br>
            const suv = vehicles[2];</p>
        </div>
    </div>
    <h2>Here is the new way of assigning array items to a variable:<br>
        <p class="red">Example<p>
    </h2>
    <p>With destructuring:<br><br>
        <div class="container">
            <div class="area">

                const vehicles = ['mustang', 'f-150', 'expedition'];<br>

                const [car, truck, suv] = vehicles;</p>
            </div>
        </div>
        <p><strong>When destructuring arrays, the order that variables are declared is important.</strong></p>

        <p>If we only want the car and suv we can simply leave out the truck but keep the comma:<br>
    <div class="container">
        <div class="area">
            const vehicles = ['mustang', 'f-150', 'expedition'];<br>

            const [car,, suv] = vehicles;</p>
        </div>
    </div>
    <h2 class="red">Example</h2>
    <div class="container">
        <div class="area">
            <p>
                function calculate(a, b) {</p>
                <p class="space">const add = a + b;<br>
                    const subtract = a - b;<br>
                    const multiply = a * b;<br>
                    const divide = a / b;<br>

                    return [add, subtract, multiply, divide];<br>
                }       <br></p>

    </p>const [add, subtract, multiply, divide] = calculate(4, 7);</p>

    <p><strong>Output</strong></p>
  
        <script>
        function calculate(a, b) {
          const add = a + b;
          const subtract = a - b;
          const multiply = a * b;
          const divide = a / b;
        
          return [add, subtract, multiply, divide];
        }

        const [add, subtract, multiply, divide] = calculate(4, 7);

        document.write("<p>Sum: " + add + "</p>");
        document.write("<p>Difference " + subtract + "</p>");
        document.write("<p>Product: " + multiply + "</p>");
        document.write("<p>Quotient " + divide + "</p>");
        </script>
    </div>
</div>

    <h2>Destructuring Objects</h2>
    <h2 class="red">Example</h2>
    <p class="blue">Before:</p>

    <div class="container">
        <div class="area">
            <p>
            const vehicleOne = {<br></p>
            <p class="space">brand: 'Ford',<br>
                model: 'Mustang',<br>
                type: 'car',<br>
                year: 2021, <br>
                color: 'red'<br></p>
            <p> }

            <p> myVehicle(vehicleOne);</p>

            <p class="blue">// old way</p>

            <p>
            function myVehicle(vehicle) {</p>
            <p class="space">const message = 'My ' + vehicle.type + ' is a ' + vehicle.color + ' ' + vehicle.brand + ' ' + vehicle.model + '.';<br></p>
            <p>    }</p>
        </div>
    </div>
    <h2 class="red">Example</h2>
    <h3>With destructuring:</h3>

        <div class="container">
            <div class="area">
                <p>
                    const vehicleOne = {<br>
                        <p class="space">  brand: 'Ford',<br>
                        model: 'Mustang',<br>
                        type: 'car',<br>
                        year: 2021, <br>
                        color: 'red'<br><p>
                        <p>}<br>

                    myVehicle(vehicleOne);<br><br>

                    function myVehicle({type, color, brand, model})</p> {<br>
                    <p class="space">const message = 'My ' + type + ' is a ' + color + ' ' + brand + ' ' + model + '.';<br></p>
                    <p>}<br></p>
                    <p class="blue">Notice that the object properties do not have to be declared in a specific order.<p>  
                    </p>

            <p>Output</p>

    
            <p id="demo"></p>
  
                <script>
                const vehicleOne = {
                    brand: 'Ford',
                    model: 'Mustang',
                    type: 'car',
                    year: 2021, 
                    color: 'red'
                    }

                myVehicle(vehicleOne);

                function myVehicle({type, color, brand, model}) {
                    const message = 'My ' + type + ' is a ' + color + ' ' + brand + ' ' + model + '.';
                    document.getElementById("demo").innerHTML = message;
                    }
                </script>
            </div>
        </div>

        <p>We can even destructure deeply nested objects by referencing the nested object then using a colon and curly braces to again destructure the items needed from the nested object:</p><br>
        <h2 class="red">Example</h2>

        <div class="container">
            <div class="area">
                <p>const vehicleOnee = {</p>  

                    <p class="space"> 
                        brand: 'Ford',<br>
                        model: 'Mustang',<br>
                        type: 'car',<br>
                        year: 2021, <br>
                        color: 'red',<br>
                        registration: {<br>
                        city: 'Houston',<br>
                        state: 'Texas',<br>
                        country: 'USA'<br></p>
                    <p> }<br>
                    }<br>
                myVehicle(vehicleOnee)<br><br>

                function myVehicle({ model, registration: { state } }) {</p>
                <p class="space">
                const message = 'My ' + model + ' is registered in ' + state + '.';</p>
                <p> } </p>

                <p>Output</p>

                <p id="dimo"></p>
  
                <script>
                const vehicleOnee = {
                  brand: 'Ford',
                  model: 'Mustang',
                  type: 'car',
                  year: 2021, 
                  color: 'red',
                  registration: {
                    city: 'Houston',
                    state: 'Texas',
                    country: 'USA'
                  }
                }

                myVehicle(vehicleOnee)

                function myVehicle({ model, registration: { state } }) {
                  const message = 'My ' + model + ' is registered in ' + state + '.';
                
                  document.getElementById("dimo").innerHTML = message;
                }
                </script>
            </div>
        </div>


    </body>
</html>

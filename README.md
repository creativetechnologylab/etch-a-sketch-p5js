# Etch-a-sketch P5.js

This P5.js application is designed to consume values being sent continously over the serial port from an Arduino running this [Gist by @unknowndomain](https://gist.github.com/unknowndomain/598d71fe88f169d44c36). The expectation is that the Arduino is wired with two potentiometers and a button. Every newline value being sent is a string in the following format:

`123, 345, 0`

The 3 values delimited by commas are expected to be two `analogRead()` values (between 0 & 1023) and one boolean (0 or 1).

In the sketch these values are being used to draw on x & y axis and clear the screen:

`x-axis, y-axis, clear`

----

### P5.SerialPort (server)

So that our P5.js application can access the serial port from the browser we need to install and run the [p5.serialport](https://github.com/vanevery/p5.serialport) node server. To do this make sure [NodeJS is installed](https://nodejs.org/en/download/). The install the library using `npm`. The `-g` will make it available globally. 

`sudo npm install -g p5.serialserver`

You will be asked for your password. 

Once this has finished installing you will be able to run node server by entering the following command:

`p5serial`

### P5.SerialPort (client)

The p5.serialport.js client script also needs to be included the the HTML file. [This is already done in this repo](https://github.com/lcc-prototyping-lab/etch-a-sketch-p5js/blob/master/index.html#L4).

<!--remove-start-->

# LED - RGB


Demonstrates use of an RGB LED (common cathode) by setting its color to red ("#ff0000") and making it blink. Requires RGB LED on pins that support PWM (usually denoted by ~).


Run with:
```bash
node eg/led-rgb.js
```

<!--remove-end-->

```javascript
var five = require("johnny-five");


five.Board().on("ready", function() {

  // Initialize the RGB LED
  var led = new five.Led.RGB({
    pins: {
      red: 6,
      green: 5,
      blue: 3
    }
  });

  // RGB LED alternate constructor
  // This will normalize an array of pins in [r, g, b]
  // order to an object (like above) that's shaped like:
  // {
  //   red: r,
  //   green: g,
  //   blue: b
  // }
  //var led = new five.Led.RGB([3,5,6]);

  // Add led to REPL (optional)
  this.repl.inject({
    led: led
  });

  // Turn it on and set the initial color
  led.on();
  led.color("#FF0000");

  led.blink(1000);

});

```


## Illustrations / Photos


### RGB LED. (Arduino UNO)


Basic example with RGB LED connected to pins 6, 5, and 3 for red, green, and blue respectively.


![docs/breadboard/led-rgb.png](breadboard/led-rgb.png)<br>

Fritzing diagram: [docs/breadboard/led-rgb.fzz](breadboard/led-rgb.fzz)

&nbsp;





&nbsp;

<!--remove-start-->

## License
Copyright (c) 2012, 2013, 2014 Rick Waldron <waldron.rick@gmail.com>
Licensed under the MIT license.
Copyright (c) 2014, 2015 The Johnny-Five Contributors
Licensed under the MIT license.

<!--remove-end-->

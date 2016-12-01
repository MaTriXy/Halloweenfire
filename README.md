# Halloweenfire
Arduino sketch for multiple NeoPixels to create spooky 'fire' effect

I have tested this with an [Adafruit Metro Mini 5v](https://www.adafruit.com/product/2590) and an [Adafruit Pro Trinket 3v](https://www.adafruit.com/products/2010) successfully.  You'll also need to get your hands on some [NeoPixels](https://www.adafruit.com/search?q=neopixel&b=1) and the [NeoPixel library](https://github.com/adafruit/Adafruit_NeoPixel).

I recommending powering this with a USB [battery charger](http://www.amazon.com/Anker-Generation-Astro-mini-Lipstick-Sized/dp/B005X1Y7I2).

Remember to indicate what pin you're using and how many NeoPixel LED's are in your chain:
```Arduino
#define PIN 6

// Parameter 1 = number of pixels in strip
// Parameter 2 = Arduino pin number (most are valid)
// Parameter 3 = pixel type flags, add together as needed:
//   NEO_KHZ800  800 KHz bitstream (most NeoPixel products w/WS2812 LEDs)
//   NEO_KHZ400  400 KHz (classic 'v1' (not v2) FLORA pixels, WS2811 drivers)
//   NEO_GRB     Pixels are wired for GRB bitstream (most NeoPixel products)
//   NEO_RGB     Pixels are wired for RGB bitstream (v1 FLORA pixels, not v2)
Adafruit_NeoPixel strip = Adafruit_NeoPixel(4, PIN, NEO_GRB + NEO_KHZ800);
```

You can also adjust some parameters of the sketch to easily tweak the fire effect.  Here, we are using an orange flame effect by default:
```Arduino
RGB flameColors[] = {
  { 226, 121, 35},  // Orange flame
  { 158, 8, 148},   // Purple flame 
  { 74, 150, 12},   // Green flame
  { 226, 15, 30}    // Red flame
  };
```

I also recently tweaked this sketch to make use of a momentary push button.  Pushing the button will cycle to the next item in the color array (effectively changing the color):
```Arduino
//  The button pin
const int buttonPin = 2;
```

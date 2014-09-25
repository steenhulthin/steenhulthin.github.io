---
layout: blogpost
categories: [.net gadgeteer, .net micro framework]
---
Hello LED Strip Gadgeteer module
================================

The day before yesterday [I showed](http://steen.hulthin.dk/blog/hello-gadgeteer-button-module/) how to use the [button module](https://www.ghielectronics.com/catalog/product/274). Today I'll make some LEDs flash. 

The Code
--------

    public partial class Program
    {
        private static readonly int FirstLed = 0;
        private static readonly int LastLed = 6;
        private int _ledNumberToModify = FirstLed;

        // This method is run when the mainboard is powered up or reset.   
        void ProgramStarted()
        {
            Debug.Print("Program Started");
            FlashAllLedsOnce();
            var timer = new GT.Timer(100);
            timer.Tick += timer_Tick;
            timer.Start();
        }

        private void FlashAllLedsOnce()
        {
            led_Strip.TurnAllLedsOff();
            led_Strip.TurnAllLedsOn();
            Thread.Sleep(1000);
            led_Strip.TurnAllLedsOff();
        }

        void timer_Tick(GT.Timer timer)
        {
            led_Strip.TurnLEDOff(_ledNumberToModify);
            if (_ledNumberToModify == LastLed) _ledNumberToModify = FirstLed;
            else _ledNumberToModify++;
            led_Strip.TurnLEDOn(_ledNumberToModify);
        }
    }

All the code is on [github](https://github.com/steenhulthin/HelloLedStripModule), but the code above is where the magic happens. 

I make use of 4 methods of the LED strip module. 

The `led_Strip.TurnAllLedsOff()` and `led_Strip.TurnAllLedsOn()` are convenient ways to turn off and on all the LEDs at once. 

The `TurnLEDOff(int led)` and `TurnLEDOn(int led)` does the same the `TurnAllLedsOff()` and `TurnAllLedsOn()` just for one specified LED (the first being 0 and the last 6.). 

The [API](http://en.wikipedia.org/wiki/Application_programming_interface) is not very consistent (spelling of *LED* is one example), but it can do what you need. Using the `LED_Strip.SetBitmask(uint mask)` method it is also possible to set multiple LEDs at once. However a look at the implementation of `LED_Strip.SetBitmask(uint mask)` reveals the following code:

    /// <summary>
    /// Sets the LEDs on the module to the value passed in.
    /// 
    /// </summary>
    /// <param name="mask">The bit mask to set the LEDs to.</param>
    public void SetBitmask(uint mask)
    {
      if (mask > this.MAX_VALUE)
        throw new ArgumentOutOfRangeException();
      uint num = 1U;
      for (int led = 0; led < 7; ++led)
      {
        if (((int) mask & (int) num) == (int) num)
          this.TurnLEDOn(led);
        else
          this.TurnLEDOff(led);
        num <<= 1;
      }
    }

So we can see that internally `LED_Strip.SetBitmask(uint mask)` is using `TurnLEDOff(int led)` and `TurnLEDOn(int led)`, so again you can do what you need with just those two methods.

The Result
----------

The code flashes all LEDs once and then continues to flash the lights one by one from left to right. 

This is what it looks like in a video:

<iframe width="420" height="315" src="//www.youtube.com/embed/dqrdS6rsC1o" frameborder="0" allowfullscreen></iframe>


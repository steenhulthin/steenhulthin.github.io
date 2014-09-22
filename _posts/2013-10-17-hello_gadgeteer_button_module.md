---
layout: blogpost
categories: [.net gadgeteer, .net micro framework]
---
# Hello Gadgeteer Button Module

[Yesterday I wrote][1] about the series of [github][2] repositories with Gadgeteer "Hello World" application coming.

Today, the [button module repo is done][3] (for now anyway...).

## The Code

    public partial class Program
    {
        void ProgramStarted()
        {
            Debug.Print("Program Started");
            button.ButtonPressed += button_ButtonPressed;
            button.ButtonReleased += button_ButtonReleased;
        }
    
        void button_ButtonReleased(Button sender, Button.ButtonState state)
        {
            button.TurnLEDOff();
        }
    
        void button_ButtonPressed(Button sender, Button.ButtonState state)
        {
            button.TurnLEDOn();
        }
    }
    

The code is fairly straight forward:

1.  React when the button is pressed or released. `ProgramStarted()`
2.  Turn off the LED if the button is released. `button_ButtonReleased(...`
3.  Turn on the LED if the button is pressed. `button_ButtonPressed(...`

## What you get...

<iframe width="420" height="315" src="//www.youtube.com/embed/Zw9b0Mj0qXM" frameborder="0" allowfullscreen></iframe>

 [1]: http://steen.hulthin.dk/blog/hello-net-gadgeteer/
 [2]: http://github.com
 [3]: https://github.com/steenhulthin/HelloButtonModule#hellobuttonmodule
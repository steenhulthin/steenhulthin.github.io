---
layout: blogpost
title: 'Ubuntu: Using the Euro and Dollar Special Keys'
categories: [IT]
---

# Ubuntu: Using the Euro and Dollar Special Keys

# What's the problem 

The Danish version of Acer Travelmate 5515 (5510 series) has the following keyboard layout: 

[<img src="/blog/wp-content/uploads/2012/12/acer_keyboard-1024x463.png" alt="acer 5510 keyboard layout (danish)" title="acer_keyboard" width="584" height="264" class="alignnone size-large wp-image-112" />][1] 

Ignore that it is a Danish keyboard layout and in stead focus on the € and $ keys above the arrow keys. 

[<img src="/blog/wp-content/uploads/2012/12/acer_keyboard_arrows.png" alt="acer arrow keys, € and $ group of keys" title="acer_keyboard_arrows" width="356" height="185" class="alignnone size-full wp-image-113" />][2] 

The € and the $ keys above the left and right arrow key respectively are dead with the standard install of ubuntu 12.04 (with standard Danish keyboard layout).   
I wanted to have [page up] where the € is and [page down] where the $ is. Like this: 

[<img src="/blog/wp-content/uploads/2012/12/fujitsu_keyboard_arrows.png" alt="keyboard layout with page up above the left arrow and page down above right arrow" title="fujitsu_keyboard_arrows" width="315" height="180" class="alignnone size-full wp-image-115" />][3] 

This is a fairly common layout (this is from a Fujitsu Celsius H710 laptop) and I think it makes perfect sense to have all the navigation keys close to each other. 

## How?

To remap your the € and $ keys to [page up] and [page down] on acer add the lines: 

`setkeycodes 0xB3 104`

`setkeycodes 0xB4 109`

to the ` /etc/rc.local ` file (before the `exit 0` line)  Step I did: 

1.  open a terminal window.
2.  execute the command `sudo nano /etc/rc.local` - I like the nano editor, but use what you like.
3.  Add the mentioned lines (`
setkeycodes 0xB3 104
setkeycodes 0xB4 109
`) and save and exit ` ctrl-x -> y ` (for yes to saving) -> `enter` (to save as /etc/rc.local) 

	[<img src="/blog/wp-content/uploads/2013/01/add_setkeycodes_to_rc.local_.png" alt="screenshot of adding setkeycodes to rc.local" title="add_setkeycodes_to_rc.local" width="724" height="463" class="alignnone size-full wp-image-137" />][4] 

4.  reboot
5.  Enjoy the new keybindings

## What's behind the Magic?

The [`setkeycodes`][5] command maps scancodes to keycodes.   

So `setkeycodes 0xB3 104` maps scancode hex B3 (the € key) to keycode decimal 104 (which is [page up])   

But how did I know want scancode and keycode to use. Good question. The short answer is: 

*   **Scancodes**  
    execute the command `/lib/udev/findkeyboards` this should return something like `AT keyboard: input/event4` where the 4 could be another number.   
    Now execute the command `sudo /lib/udev/keymap -i input/event4` (replacing 4 with "input/event[number]" you got from the previous command.). Press the key you want to (re)map and note the scancode. To break the program hit escape. Don't be really sleepy when you do this! :p  
    *One caveat*: if the scancode is above 0xFF you are out of luck due to [this bug][6]. Otherwise go on and find the keycode! 
  
*   **Keycodes**  
    in the file /usr/include/linux/input.h under the section "Keys and buttons" you can see which keys are mapped to what decimal number. Go ahead and find the key you want to map your scancode to. 
	
	[<img src="/blog/wp-content/uploads/2013/01/keys_and_buttons_section_in_input.h.png" alt="screenshot of keys and buttons section in input.h" title="keys_and_buttons_section_in_input.h" width="724" height="463" class="alignnone size-full wp-image-143" />][7]   
    
	[<img src="/blog/wp-content/uploads/2013/01/input.h_key_pageup_binding.png" alt="key_pageup map in the input.h file" title="input.h_key_pageup_binding" width="724" height="463" class="alignnone size-full wp-image-142" />][8] </p> 

## Further reading:

*   On your local file system there is a walkthrough for fixing key problems in the file /usr/share/doc/udev/README.keymap.txt.gz
    *   `sudo gunzip /usr/share/doc/udev/README.keymap.txt.gz` to extract the file.
    *   `nano README.keymap.txt` to read the file.
    *   start reading at the `==fixing broken keys==` section
*   Post which includes solution similar to this: <http://ubuntuforums.org/showthread.php?t=1286534>
*   Other solutions to problems with key on Ubuntu <http://askubuntu.com/questions/133113/emulate-keypad-on-laptop/142339#142339> <http://askubuntu.com/questions/141479/dell-inspiron-n5110-keyboard-touchpad/144207#144207> <http://askubuntu.com/questions/145589/how-to-change-the-functionality-of-keyboard-special-keys>

 [1]: /blog/wp-content/uploads/2012/12/acer_keyboard.png
 [2]: /blog/wp-content/uploads/2012/12/acer_keyboard_arrows.png
 [3]: /blog/wp-content/uploads/2012/12/fujitsu_keyboard_arrows.png
 [4]: /blog/wp-content/uploads/2013/01/add_setkeycodes_to_rc.local_.png
 [5]: http://linux.about.com/library/cmd/blcmdl8_setkeycodes.htm
 [6]: https://bugs.launchpad.net/ubuntu/+source/xorg-server/+bug/313514
 [7]: /blog/wp-content/uploads/2013/01/keys_and_buttons_section_in_input.h.png
 [8]: /blog/wp-content/uploads/2013/01/input.h_key_pageup_binding.png
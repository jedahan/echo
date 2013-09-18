# ♥ Piet

echo.png, in [piet](http://www.dangermouse.net/esoteric/piet.html)

This will echo whatever input string you give it, and exits when there is a '.'

I included a copy of the webpage that describes the language, as piet.html
The only way I have been able to run Piet so far is in the browser, [here](http://www.rapapaing.com/blog/?page_id=6)

Make sure to load the small image, or the large one with a Codel width of 10.

Notes:
The program is greedy, and asks for all input in an infinite loop (which I accidentally made, its feature now!). So let's say I want it to exit when the stack is empty, how can I do that? Well, lets say it tries to chomp a '.', heres how I will check for a period and branch if its there:

### Rotate direction pointer if eq to '.'
dup     # take the newest input
46      #
push    # push a '.'
sub     # subtract '.' from the newest input, push result on stack
not     # if result is anything but 0, push a 1, otherwise keep it as 0
pointer # rotate the direction pointer by 0 or 1
# Offline

## Overview
Offline was supposed to be a desktop application that increased one's productivity by disabling their internet connection for a finite amount of time.

The goal was to improve my understanding of C++, use Qt for C++ and learn how to deal with Windows libraries. Due to time constraints and other commitments, I wasn't able to complete it.

## What I've learned
Despite the fact that this project is unfinished, I've learned a lot through it, more than I expected.

I used Microsoft Visual Studio 2017 for this project. It was my first time using an IDE for C++ that had way more features than CodeBlocks or notepad++. Unlike those other IDEs, it was unintuitive and I had to research really basic things before starting anything. But, it enabled me to focus on the project itself and I didn't have to any hard lifting for installing Qt and the necessary APIs for Windows. For this project, it was my first time using Qt for C++. Previously, in high school, I had done the tutorials but hadn't built anything with my new found knowledge. I had previous experience using PyQt and some of those projects are on Github.

The hardest part about this project was disabling the internet connection. It took me weeks to figure out how to go about doing this. Through reading a lot of documentation, I started learning about COM (Component Object Model) and WMI (Windows Management Instrumentation). Learning COM and WMI has quite a steep learning curve but I still decided to try to use it.

Based on the code given in the example documentation, I tried to disable my network adapters. But, this never worked the way I wanted to as I had to specify the particular adapter. Moreover, it would crash the entire program due to threading issues. I tried putting the code for disabling network adapters into a thread using QThread but the program still crashed. Afterwards, I found a partial solution that worked by releasing the DHCP lease on all my network adapters. If the person using this wasn't quite tech-savvy, they wouldn't notice that I really didn't disable their internet connection. The code for releasing the DHCP lease worked in a separate solution but didn't work when I added it to the Qt project. I tried putting it in a separate thread and the program still crashed.

Finally, I decided to use Active Qt to try the same things I did previously but with the tools Qt provides. This also failed as the code example I used to attempt this was old and I couldn't figure out how to use QVariant appropriately. Given more time, I think this method would have worked the best.

## Improvements
Since the project doesn't work, there a lot of improvements that can be made.

First, the GUI needs a lot of work. It doesn't display the time correctly. Moreover, the positions of the elements in the GUI would change significantly on different screens as I haven't put them in layouts. The timer function needs to be reimplemented because it doesn't quite do what I wanted to do. The code needs to manage memory better as a lot of the errors I got were due to heap corruption or allocation. I also would add threading to try to resolve these issues.

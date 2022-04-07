There were quite a few CWE's I struggled with initially when first learning to code. The worst one of all of them however was probably 
out of bounds write which stumped me a lot my first semester. Out of bounds write occurs when you go over the amount of allocated memory given to a value. 
For example, say I have a String with a certain length and I try to put information outside of that given length I will receive an out of bounds write error. 
One of the example CVE's given on the website was bluetooth implementation with mobile phones and not including the offset value for packet length, leading to
an out of bounds write error.

[See more about CVE here](http://cve.mitre.org/cgi-bin/cvename.cgi?name=CVE-2020-0022)


Looking back, I think the most prominent example of my experience with this CWE is in the case of implementing for loops (string length). I constantly was stepping past a value's size
not under standing why it was happening. My solution to this problem at the time was just to attempt to brute force my way through the problem with trial and error. If
that didn't work it was back to square one and/or time to ask for help.

Knowing what I do now, one of the easiest things I could do would to just checking to make sure my boundaries are as large as specified.
However, I feel like the errors I was having are easily preventable with a few adjustments to my code with the help of extensions that make addresses more unpredictable.
The best advice probably comes from the CWE website when referring to implementation:

**"Consider adhering to the following rules when allocating and managing an application's memory:**

*Double check that the buffer is as large as specified.
When using functions that accept a number of bytes to copy, such as strncpy(), be aware that if the destination buffer size is equal to the source buffer size, it may not NULL-terminate the string.
Check buffer boundaries if accessing the buffer in a loop and make sure there is no danger of writing past the allocated space.
If necessary, truncate all input strings to a reasonable length before passing them to the copy and concatenation functions."*

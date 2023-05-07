Download Link: https://assignmentchef.com/product/solved-embsys110-assignment-2-led-pattern
<br>
The goal of this assignment is to represent a set of LED patterns using object-based techniques. Students will learn how to encapsulate an abstract idea, i.e. an LED pattern, with C++ classes. Students will implement a typical “hello-world” program to display those patterns with a physical LED.

2         Setup

<ol>

 <li><em>Carefully</em> unplug any extension modules from your Nucleo board. They are not required and may hinder your view of the USER LED. Besides, the USER LED pin (PA.5) is shared with the SPI CLK pin of the LCD module, and therefore they cannot be used together.</li>

 <li>Download the compressed project file (platform-stm32f401-nucleo_assignment2.tgz) from the Assignment 2 course site.</li>

</ol>

Place the downloaded tgz file in your VM under <strong>~/Projects/stm32</strong>.

<ol start="3">

 <li>Backup your existing project folder, e.g. mv platform-stm32f401-nucleo platform-stm32f401-nucleo.bak</li>

 <li>Decompress the tgz file with:</li>

</ol>

tar xvzf platform-stm32f401-nucleo_assignment2.tgz

The project folder will be expanded to <strong>~/Projects/stm32/platform-stm32f401-nucleo</strong>.

<ol start="5">

 <li>Launch Eclipse. Hit F5 to refresh the project content.</li>

</ol>

Or you can right-click on the project in Project Explorer and then click “Refresh”.

<ol start="6">

 <li>Clean and rebuild the project. Download it to the board and make sure it runs.</li>

</ol>

In minicom, type the command “<strong>led on 0</strong>” and verify the USER LED blinks twice (with the first one brighter than the second one).

<h1>3         Tasks</h1>

<ol>

 <li>Most to-do tasks are marked with “// UW 2019” in the source code.</li>

 <li>Complete the implementation of the LedPattern and LedPatternSet classes in</li>

</ol>

Copyright (C) 2020 Lawrence Lo. All rights reserved.

<strong>src/UserLed/LedPattern.h</strong>.

Note – These member functions are <em>inline, </em>and therefore implemented in the header file.

<ol start="3">

 <li>Add two new LED patterns to the structure named TEST_LED_PATTERN_SET in <strong>src/UserLed/LedPattern.cpp</strong>.</li>

</ol>

Two samples, patterns 0 and 1, are provided for reference. Do not remove them, and append yours as patterns 2 and 3.

<ol start="4">

 <li>Implement the handlers for the command “led on &lt;index&gt; &lt;repeat&gt;” in <strong>src/UserLed/UserLedCmd.cpp</strong>.</li>

</ol>

This command displays the indexed pattern. If repeat is “0”, it is shown once; otherwise it is shown <strong>5 times</strong>. Handle the case when the index is out of range. As a reminder, the set of LED patterns is defined in the structure TEST_LED_PATTERN_SET.

Please remove or comment the sample code when adding your own code.

<ol start="5">

 <li>Test your code with the console command:</li>

</ol>

<em>led on &lt;pattern index from 0 to 3 &gt; &lt;0 for non-repeating; 1 for repeating&gt;</em>

For example, “led on 3 1” shows pattern 3 for 5 times.)
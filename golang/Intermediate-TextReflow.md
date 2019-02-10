### Description:
Text reflow means to break up lines of text so that they fit within a certain width. It is useful in e.g. mobile browsers. When you zoom in on a web page the lines will become too long to fit the width of the screen, unless the text is broken up into shorter lines.

#### Input:
You will be given a text with a maximum line width of 80 characters.

#### Output:
Produce the same text with a maximum line width of 40 characters

#### Challenge Input:
```
In the beginning God created the heavens and the earth. Now the earth was
formless and empty, darkness was over the surface of the deep, and the Spirit of
God was hovering over the waters.

And God said, "Let there be light," and there was light. God saw that the light
was good, and he separated the light from the darkness. God called the light
"day," and the darkness he called "night." And there was evening, and there was
morning - the first day.
```

#### Challenge Output:

```
In the beginning God created the heavens
and the earth. Now the earth was
formless and empty, darkness was over
the surface of the deep, and the Spirit
of God was hovering over the waters.

And God said, "Let there be light," and
there was light. God saw that the light
was good, and he separated the light
from the darkness. God called the light
"day," and the darkness he called
"night." And there was evening, and
there was morning - the first day.
```

#### Bonus:
Let's get rid of the jagged right margin of the text and make the output prettier. Output the text with full justification; Adjusting the word spacing so that the text is flush against both the left and the right margin.

##### Bonus Output:
```
In the beginning God created the heavens
and   the  earth.   Now  the  earth  was
formless  and empty,  darkness was  over
the  surface of the deep, and the Spirit
of  God was  hovering over  the  waters.

And  God said, "Let there be light," and
there  was light. God saw that the light
was  good, and  he separated  the  light
from  the darkness. God called the light
"day,"   and  the   darkness  he  called
"night."  And  there  was  evening,  and
there  was  morning  -  the  first  day.
```

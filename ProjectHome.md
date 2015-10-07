**Current version is 0.2.1**


---


**Please make sure that every style has properties in the stylesheet.
So if you use a table then add a stylesheet section for the td in the stylesheet
This is especially necessary for elements with text in it. If there's no font defined flash will not be able to render it.**

html:
```
<table><tr><td>TD contents</td></table>
```

stylesheet:
```
td
{
font-family:Arial;
font-size:12px;
}
```


---


17 juli 2008: _I will release an updated version soon with examples for flash and flex, keep you posted_


**What it does?**
HTMLSprite converts HTML to a Actionscript 3 Sprite.

Download the last version and read the Wiki page to get started. http://code.google.com/p/htmlsprite/wiki/Gettingstarted

Ideas, bugs etc, please contact me.
[Kees van Dorp](mailto:keesvandorp@gmail.com)


**Supported**

---

  * External stylesheets in html (

&lt;link&gt;

 tag)
  * Style tag (

&lt;tag style="\*"/&gt;

)
  * Tags: body,table,div,img,span,a
  * colspan in tables
  * Styles: text-align,border,background-color,color,padding,width,height

**Not supported (right now)**

---

  * inline html style section (

&lt;head&gt;



&lt;style&gt;

..

&lt;/style&gt;



&lt;/head&gt;

)
  * basic html attribute (like <img width=''>) use the style variant<br>
<ul><li>relative widths and heights (ie. width:100%)<br>
</li><li>a lot more</li></ul>

There's still a lot of work to do, but it renders fairly right now.<br>
Currently it hasn't been tested with Flex, but i see no reason why it shouldnt work.
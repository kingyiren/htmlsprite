# Getting Started #

Here's a quick way to setup the class
Make sure that you embed the font somewhere in the file
import com.redurban.HTMLSprite

var htmlsprite:HTMLSprite = new HTMLSprite();
//
//static debug mode on/off
HTMLSprite.debug = true;
//
//Use this event when loading both stylesheet and html file
htmlsprite.addEventListener(HTMLSprite.LOADCOMPLETE, LoadComplete);

//
//This event will be dispatched when the rendering is complete
htmlsprite.addEventListener(HTMLSprite.RENDERCOMPLETE, RenderComplete);

//
//Use this event when loading a stylesheet file only
//Will be dispatched when the load is completed.
htmlsprite.addEventListener(HTMLSprite.STYLECOMPLETE, StyleComplete);

//
//Use this event when loading a external html file only, 
//Will be dispatched when the load is completed.
htmlsprite.addEventListener(HTMLSprite.HTMLCOMPLETE, HtmlComplete);

//
//This event will be dispatched when an external link is click
//<a href="event:internalEvent">Example</a>
htmlsprite.addEventListener(HTMLSprite.LINK, Link);
			
// Example html file + css file
// htmlsprite.Load("html/indexwithoutcss.htm", "html/style.css");
			
// Example stylesheet file only
// htmlsprite.LoadStylesheet("html/style.css");
			
// Example html file only
// htmlsprite.Load("html/index.htm");
			
// Example html text + stylesheet text

var stylesheet:StyleSheet = new StyleSheet();
stylesheet.setStyle(".header",{fontFamily:"Arial",color:"#000000"});
stylesheet.setStyle("body",{fontFamily:"Arial"});
stylesheet.setStyle("div",{fontFamily:"Arial",fontSize:"20px",backgroundColor:"#efefef"});

htmlsprite.stylesheet = stylesheet;
htmlsprite.html = "Hello<br/>world!";
htmlsprite.Render();

//
// Link Listener
public function Link(evt:LinkEvent)
{
var linkType:String = evt.data.type;
var linkValue:String = evt.data.value;
var linkTarget:String = evt.data.target;
			
trace("linktype:"+linkType+",linkvalue:"+linkValue+",linktarget:"+linkTarget);
}
//
// Load Complete Listener
// It's important that you render the html after the stylesheet 
// and html file has been loaded
public function LoadComplete(evt:Event)
{
htmlsprite.Render();
}

// Load Stylesheet Complete
// Do not use this listener when you use an external stylesheet AND external HTML.
// You can use then the LoadComplete Example

public function StyleComplete(evt:Event)
{
htmlsprite.html = "hello<br/>world";
htmlsprite.Render();
}

// Load HTML Complete
// Do not use this listener when you use an external stylesheet AND external HTML.
// You can use then the LoadComplete Example
		
public function HtmlComplete(evt:Event)
{
htmlsprite.stylesheet = stylesheet;
htmlsprite.Render();
}
		
// Render complete
// At this point it's safe to determine width and height of the sprite 
// and add it to the displaylist

public function RenderComplete(evt:Event)
{
addChild(htmlsprite);
}```
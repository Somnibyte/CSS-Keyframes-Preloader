The first ever [pure] CSS 'preloader'!

TEXT DEMO: http://jsbin.com/omAWEhO/7/quiet IMAGE DEMO:http://jsbin.com/eMEKiNo/2/quiet

This is how the CSS Keyframe preloader works.

Ideology: Hide the inner content of the body, by using the body element itself to cover the content with whatever background you choose. Once the page loads, there is a keyframe that activates and animates the background to cover the content. Special features may be added, for example text or images.

-Head over to textpreloader.html to see an example of the text preloading animation. -Head over to imagepreloader.html to see an example of the image preloading animation. -Note: NO javascript was used, nor Jquery.

'The Algorithm':

The body is given a key frame of a very dark color to hide the content, here is an example:

@-webkit-keyframes bodyPreloader{ 0%{background:black;}

}

This keyframe makes the body turn black, so that all pieces of content are covered from the screen (This piece of code was taken from the 'textpreloader.css' file.

What I did next was bind the animation to the body like so:

body{ background-color: #3498db;

-webkit-animation: bodyPreloader 3s;

}

One the animation was binded to the element, I needed a way to over the content. So I gave the content an animation to hide itself until the body was done animating using this keyframe:

@-webkit-keyframes content{ 0%{opacity: 0;} }

Then, I binded the animation to the element (NOTE! if you have many elements that make up your content (i.e nav, sidebars, ANY KIND OF CONTENT HOLDING DIV THAT IS NOT PART OF THE PRELOADING PROCESS) must have this animation binded to itself to keep it hidden: Example of ONE element (since this page only has one content div being used):

-webkit-animation: content 1s ease-in; -webkit-animation-duration:2s;

There you have it. Now if you would like to add an image (Like SquareSpace) or welcoming text simply make this animation:

@-webkit-keyframes emblemPreload{ 0%{opacity: 1;} 25%{opacity: 1;} 50%{opacity: 0;] 100%{opacity: 0;} } What this animation does is shows the welcoming emblem (logo, designs, etc..) and later fades that piece of content away.

And bind it to the elment of your choosing:

-webkit-animation: emblemPreload 4s ease-out;

NOTE: This is a prototype as of now. Any ideas are welcomed to improve this prototype of mine. You may modify the code to your liking. Remember to give credit, and give me a shout out. ;)
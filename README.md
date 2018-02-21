# Basil.js workshop

## schedule of our wonderful day together

1. Quick historical introduction to [basil.js](http://basiljs.ch/) & installation for those who didn't manage to it by themselves

2. "Hello World!" with 

   ```javascript
   b.units(b.MM);//b.PX, b.PT set the units of document
   b.rect(x, y, width, height);//draw a rect(x, y, width, height)
   var x = b.random(min, max);//random number between 200 & 300
   b.ellipse(x, 60, 50, 50);//draw a ellipse(x, y, width, height)
   b.fill(r, g, b);//fill with color
   b.stroke(r, g, b);//stroke color
   b.text(String, x, y, width, height)
   ```

3. Working with text

   ```javascript
   var words = b.words(textElement);//returns an array of word objects
   var chars = b.characters(textElement)//same but returning chars objects
   //changing the typography
   for(var i = 0; i < chars.length; i++){
       var c = chars[i];
       b.typo(c, 'underline', true);//sets underline to true
       b.typo(c, 'pointSize', 50);//sets character size to 50
       b.typo(c, 'someTypo', true || value);
   }
   for(var i = 0; i < words.length; i++){
       var word = words[i];
       var wordBound = b.bounds(word);//returns the bounds of a text element and it's position on the canvas
       word.contents();//returns the content of the text element as a string
   }
   ```

4. ​
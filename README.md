# Basil.js workshop

## schedule of our wonderful day together

1. Quick historical introduction to [basil.js](http://basiljs.ch/) & [installation](http://basiljs.ch/tutorials/installation-and-getting-started/) for those who didn't manage to do it by themselves

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

4. Vector exercise

   ```javascript
   function Vector(x, y){
       this.x = x;
       this.y = y;

       this.sub = function(v1, v2){
           var result = new Vector(0, 0);
           result.x = v1.x - v2.x;
           result.y = v1.y - v2.y;
           return result;
       }

       this.add = function(x, y){
           this.x += x;
           this.y += y;
       }

       this.heading = function(){
           return -Math.atan2(-this.y, this.x);
       }
   }
   ```

5. Parsing JSON from the [INTERNET](http://internet.net/)

   ```javascript
   var searchURL = "https://en.wikipedia.org/w/api.php?action=opensearch&format=json&search="
   var word = 'any word found in our indesign file'
   var url = b.loadString(searchURL + word);
   var json = b.JSON.decode(url);
   b.text(json[2][0], 22, 69, 130, 150);
   ```
5.5. [SORT!](https://developer.mozilla.org/it/docs/Web/JavaScript/Reference/Global_Objects/Array/sort)
```javascript
var myWords = words.contents.split(/\W+/)
myWords.sort(myFunction);
function myFunction (a, b){
return a.length - b.length;
}
```

## REFERENCES

* Basics [cheatsheet](http://basiljs.ch/wp-content/uploads/2012/11/basiljs-cheatsheet.pdf)
* Typo [cheatsheet](http://basiljs.ch/wp-content/uploads/2013/03/basiljs_b_typo_cheatsheet_v0_2.pdf)
* [InDesign Object Model](http://basiljs.ch/wp-content/uploads/2012/11/basiljs-IOM-0.2.pdf)

Thanks to  [Ted Davis](http://www.teddavis.org/) for the cheatsheets!

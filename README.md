# Curly HTML Elements

Mini tool to arranging HTML elements along ellipse subset shapes. Using curly-html-elements you can layout child items of an 
element along a circle, semicircle, ellipse or any subset shape of it without encounter math formula and complex concepts.

It’s only 2KB and easy to use.

**😎😎 [Online Demo](https://behnamazimi.github.io/curly-html-elements/)**

### Installation

Using npm:
```
npm install curly-html-elements
```

Using yarn:
```
yarn add curly-html-elements  
```

Using unpkg CDN
```
<script src="http://unpkg.com/curly-html-elements/lib/curly-html-elements.min.js"></script>
```

### Usage
First, import `curly-html-elements` to your project. You can do it by adding the script tag that mentioned above, or you can
 import it as a module like this.
```javascript
import CurlyElements from "curly-html-elements";
``` 
 
After adding the library to your project, you can call it like this.
```javascript
const myEllipse = new CurlyElements(htmlElement, options)
``` 

There are two arguments that you should pass to the `CurlyElements`:
* **htmlElement:** the target element that you want to ellipse its child
* **options:** properties to shape your ellipse. You can see all in below table. 

#### Options

Property | Value | Default | Description
--- | --- | --- | ---
type | `equal`/`compact` | `equal` | Layout type of the ellipse. there are two types, equal and compact. The distance between items will be equal in "equal" mode. 
size | [0, 1] | 0.5 | Size of ellipse. Its a number between 0 and 1. if you want a entire ellipse it must be 1.
rotate | [0, 360] | 0 | Use this property to rotate ellipse. It could be a number between 0 and 360.  
reflection | [-1, +1] | 1 | Use this to mirroring the ellipse. its standard value is a number in range of [-1,+1] but you can set any numbers. for example, value 2 means two times height for the ellipse.   
shiftX | number | 0 | To shift whole layout to **right** or **left**. The value could be both positive and negative.
shiftY | number | 0 | To shift whole layout to **up** or **down**. The value could be both positive and negative.   

You can arrange your elements in any subset shape of an ellipse and put it in any position of your parent element with changing the options.

#### Render with new options
To update initial options you can use `.update(newOptions)` API. this method merges new options with the previous object 
and rerender the ellipse.   

### Example
```javascript
const elm = document.getElementById("demo");
const options = {
    type: "equal",  // compact, equal
    size: .5,       // 0, 1
    rotate: 5,      // 0, 360
    reflection: 1,  // 0, 1, only in compact layout
    reverse: false, 
    shiftX: 0,      // any number
    shiftY: 0,      // any number
}
const myEllipse = new CurlyElements(elm, options)

// to update options and rerender the ellipse
myEllipse.update({type: "compact", size: 1})
``` 

### Sample Layouts
![Ellipsis elements samples](./demo/samples.jpg)

### Contributing
I would be grateful to those who helped me make the project truly perfect. So, feel free to contribute to the project. 
Also, if you encounter any problem bring it up as an [issue](https://github.com/behnamazimi/curly-html-elements/issues/new).  

### License

[MIT](https://github.com/behnamazimi/curly-html-elements/blob/master/LICENSE)

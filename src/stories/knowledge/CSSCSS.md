# CSSCSS Framework
## Cheat Sheet Strategy for Cascading Style Sheets



### Create
#### Object creating and location classes
This section contains a variety of styles related to the creational stage of elements within a webpage. The code is divided into three main sections: "POSITION", "SIZE" and "INDEX".
Classes    
Under the "POSITION" module, there are several classes related to positioning. These classes include:
```
.pos-rel{position: relative}
.pos-abs{position: absolute}.pos-fixed{position: fixed}.pos-fix{position: fixed}
```
Additionally, there are several classes related to edge alignment, which set the position of an element based on its distance from the top, left, right, or bottom edges of its parent element. These classes include:
```
.top-0{top: 0}.left-0{left: 0}.right-0{right: 0}.bottom-0{bottom: 0}
.top-20p{top: 20%}.left-20p{left: 20%}.right-20p{right: 20%}.bottom-20p{bottom: 20%}
. . .
```
Finally, there are several classes related to z-index and translation. These classes include:
```
/* Z-INDEX */
.z-1{z-index: 1}.z-2{z-index: 2}.z-3{z-index: 3}.z-5{z-index: 5}.z-8{z-index: 8}
.z-10{z-index: 10}.z-20{z-index: 20}.z-30{z-index: 30}.z-50{z-index: 50}
. . .
/* TRANSLATE */
.translate-x--25 {transform: translateX(-25%)}.translate-x-25 {transform: translateX(25%)}
.translate-x--50 {transform: translateX(-50%)}.translate-x-50 {transform: translateX(50%)}
. . .
```



### Structure
#### Structural and text related classes
This section contains a variety of styles related to the structural stage of elements within a webpage. The code is divided into three main sections: "SPACING", "DISPLAY" and "TEXT".
Classes​
Under the "SPACING" module, there are several classes related to the space around an element's content. These classes include:
```
/* PADDING */
.pa-0{padding: 0}.pa-1{padding: 5px}.pa-2{padding: 10px}.pa-3{padding: 15px}
.pa-4{padding: 20px}.pa-5{padding: 25px}.pa-6{padding: 30px}.pa-7{padding: 35px}
. . .
/* MARGIN */
.ma-0{margin: 0}.ma-1{margin: 5px}.ma-2{margin: 10px}.ma-3{margin: 15px}
.ma-4{margin: 20px}.ma-5{margin: 25px}.ma-6{margin: 30px}.ma-7{margin: 35px}
. . .
```
Additionally, there are several classes related to visibility and structure, which set the layout of the children of an element. These classes include:
```
/* DISPLAY */
.invisible{visibility: hidden}.hidden{visibility: hidden}.block{display: block}.none{display: none}
.noverflow{overflow: hidden}.noverflow-x{overflow-x: hidden}.noverflow-y{overflow-y: hidden}
. . .
/* FLEX */
.flex{display: flex }
.flex-1{flex: 1 }.flex-2{flex: 2 }.flex-3{flex: 3 }
.flex-center{display: flex; justify-content: center; align-items: center }
.flex-row{display: flex; flex-direction: row; justify-content: center; align-items: center }
.flex-center{display: flex; justify-content: center; align-items: center }
.flex-col{display: flex; flex-direction: column; justify-content: center; align-items: center }
. . .
/* FLEX GAP */
.gap-1{gap: 5px }.gap-2{gap: 10px }.gap-3{gap: 15px }.gap-4{gap: 20px }.gap-5{gap: 25px }
. . .
```
Finally, there are classes related the most common font style properties. These classes include:
```
/* FAMILY */
.tx-sans {font-family: 'Open Sans', sans-serif}.tx-roman {font-family: 'Times New Roman', Times, serif}
/* SIZE */
.tx-xxs {font-size: 0.35rem}.tx-xs {font-size: 0.55rem}.tx-xsm {font-size: 0.725rem}.tx-sm {font-size: 0.845rem}
. . .
```



### Update
#### Restructuring and visibility classes
This section contains a variety of styles related to the restructuring stage of elements within a webpage. The code is divided into three main sections: "BACKGROUND", "OPACITY" and "FILTER".
Classes​
Under the "Background" module, there are several classes related to background properties. These classes include:
```
/* DEBUG */
._ddr{background: red}._ddg{background: green}._ddb{background: blue}
/* COLOR */
.bg-trans {background: transparent}
.bg-red-25{background: #ff000044}.bg-green-25{background: #00FF0044}.bg-blue-25{background: #0000ff44}
.bg-red-50{background: #ff000077}.bg-green-50{background: #00FF0077}.bg-blue-50{background: #0000ff77}
. . .
/* GLASS-MORPHISM */
.bg-glass-1 {backdrop-filter: blur(1px);-webkit-backdrop-filter: blur(1px)}
.bg-glass-2 {backdrop-filter: blur(2px);-webkit-backdrop-filter: blur(2px)}
. . .
```
Additionally, there are several classes related to opacity and hover states. These classes include:
```
.opaci-0 {opacity: 0 }.opaci-5 {opacity: 0.05}.opaci-10 {opacity: 0.10}
.opaci-20 {opacity: 0.2 }
.opaci-15 {opacity: 0.15}.opaci-25 {opacity: 0.25}.opaci-50 {opacity: 0.5}
. . .
```
Finally, there are several classes related to filter and transform properties. These classes include:
```
.invert{filter: invert(1)}.bright-1000{filter: brightness(10)}
.blur-1 {filter: blur(1px)}.blur-2 {filter: blur(2px)}.blur-3 {filter: blur(3px)}.blur-4 {filter: blur(4px)}
.blur-5 {filter: blur(5px)}.blur-6 {filter: blur(6px)}.blur-7 {filter: blur(7px)}.blur-8 {filter: blur(8px)}
. . .
.rot-250{transform: rotate(250)}
.rot-270{transform: rotate(270)}
...
```



### Behave
#### Behavioral Classes
This section contains a variety of styles related to behavioral stage of elements within a webpage. The code is divided into three main sections: "CURSOR", "MEDIA QUERY", "ANIMATION" and "EXTRA".
Classes​
Under the "CURSOR" module, there are several classes related to the cursor pointer design and interaction. These classes include:
```
.cursor {cursor: default}.pointer {cursor: pointer}
.clickble {cursor: pointer}.grab {cursor: grab}.grabble {cursor: grab}
.stopcursor {cursor: not-allowed !important}.waitcursor {cursor: wait}
...
```
Additionally, there are several classes related to mobile responsiveness, which set the position and display of an element based on the user's device. These classes include:
```
@media only screen and (max-width: 600px)
{
	.Q_xs_pa-0{padding: 0}.Q_xs_pa-1{padding: 5px}.Q_xs_pa-2{padding: 10px}.Q_xs_pa-3{padding: 15px}
...
/* Only Extra Small */
@media (min-width: 0601px){.Q_xs{display: none } }
/* Only Small */
@media (min-width: 0901px) , (max-width: 0600px){.Q_sm{display: none } }
...
```
Furthermore, there are multiple animation classes related to simple translation movements and opacity transitions. These classes include:
```
.scale-outin-once-1{animation: scaleoutin 0.5s}
.appear-once-1{animation: fadeinout 1s}
.appear-once-2{animation: fadeinout 2s}
...
.shake-1{animation: shake 1s;  animation-iteration-count: infinite }
.shake-2{animation: shake 2s;  animation-iteration-count: infinite }
.shakefull-1{animation: shakefull 0.1s;  animation-iteration-count: infinite }
...
```
Finally, there are several classes related to site-specific theme color, font families and more. These classes include:
```
@import url('https://fonts.googleapis.com/css2?family=Inter:wght@100;200;300;400;500;600;700;800;900&display=swap');
​
body { font-family: "Inter"; }
​
:root {
  --color-blue: #0074D9;
  --color-blue-dark: #004267;
  --color-blue-sat: #1193E8;
  --color-blue-desat: #9CBEDB;
  --color-blue-light: #E8F3FF;
  
  ...
}​
​
:root {  
  --primary-dark: var(--color-emerson-dark);
  --primary-sat: var(--color-emerson-sat);
  --primary:  var(--color-emerson);
  --primary-desat: var(--color-emerson-desat);
  --primary-light: var(--color-emerson-light);
  
  ...
  
  --bg-main: #ffffff;
  --bg-muted: #F9FAFB;
  --bg-faded: #F5F7F6;
​
  --tx-main: #101828;
  --tx-muted: #344054;
  --tx-faded: #667085;
​
  --tx-error: #B91C1C;
  --tx-link: #026AA2;
​
  --border-faded: #D0D5DD;
}
​
.bg-primary {
	background: var(--primary);
}
.bg-main { background: var(--bg-main); }
...
```
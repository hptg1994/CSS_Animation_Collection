## Transitions - From A to B

The `transition` property is made up of four parts. 

```css
transition: transform 2s ease-out 1s;
```

What this transition means is "when any animatable property changes, wait for one second, then transition to the new style over a duration of 2 seconds". We'll go into timing functions in greater depth later.

The `ease-out` part of the definition, in this case, means to start fast and then gradually decelerate toward the end of the 2 seconds.

Example:
<center>
	<img src="./Resources/trasition.gif" width="70%" />
</center>

Code that do this:

```css
/* the blue container */
.demo-letter {
  left: 50%; 
  position: absolute; // A B这两个字母是absolute的位置
  top: 50%;
  // transition property and we want to affect the transform property
  transition: transform .4s ease-out; // 动画的启动对象
}

/* Container A */
.demo-letter1 {
  // 因为上面absolute x 的50%的位置过头了，所以要回来-50%
  -webkit-transform: translate(-50%, -50%); 
          transform: translate(-50%, -50%);  
}

/* Container B */
.demo-letter2 {
  -webkit-transform: translate(-50%, 200%); // B字母的y轴则在初始状态200%向上让他消失
          transform: translate(-50%, 200%);
}

/* Container A behavior when hover*/
.demo:hover .demo-letter1 {
  -webkit-transform: translate(-50%, -200%);
          transform: translate(-50%, -200%);
}

/* Container B behavior when hover*/
.demo:hover .demo-letter2 {
  -webkit-transform: translate(-50%, -50%);
          transform: translate(-50%, -50%);
}
```


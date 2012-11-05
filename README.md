jQuery Burn: Text flame effect
====
[http://sinetheta.github.com/burn/](http://sinetheta.github.com/burn/)

jQuery Burn applies a simple flame effect to text using the css text-shadow property. As such it currently does not work in IE http://caniuse.com/css-textshadow

Usage
---

	<script>
	(function(){
		$(document).ready(function() {
			$(target).burn();
		});
	})(jQuery);
	</script>

To turn off effect `$(target).burn(false);`

To get a single option, set a single option, or set multiple options:

    $(target).burn('wind'); // returns 1
    $(target).burn('diffusion', 2); // doubles the flame size
    $(target).burn({
      k: 10,
      w: 10
    }); // waves half as long and twice as fast

Options
---

	var options = {
		//Amplitude
	    a : .3,
	    //Wave Number
	    k : .05,
	    //Angular Frequency
	    w : 10,
	    //Skew
	    wind: 1,
	    //Animation speed
	    interval: 100,
	    //Each of these objects represents a shadow
	    flames : [{
	    		//Start displacement
                x: 0,
                //Color of the shadow
                hsla: [58, 96, 89, 1],
                //height above the letter in em
                y: 0,
                //Size/clarity of the shadow
                blur: .1
            },
            {
                x: 0,
                hsla: [51, 98, 76, 1],
                y: .02,
                blur: .15
            },
            {
                x: 0,
                hsla: [36, 100, 60, 1],
                y: .04,
                blur: .2
            },
            {
                x: 0,
                hsla: [28, 91, 49, 1],
                y: .08,
                blur: .25
            },
            {
                x: 0,
                hsla: [19, 94, 41, 1],
                y: .15,
                blur: .3
            },
            {
                x: 0,
                hsla: [15, 75, 34, 1],
                y: .2,
                blur: .4
            },
            {
                x: 0,
                hsla: [14, 66, 16, 1],
                y: .5,
                blur: .5
        }]
	};
	$(target).burn(options);

<table>
    <caption>Options</caption>
    <thead>
        <tr>
            <th>Option</th>
            <th>Default</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>a</td>
            <td>0.3</td>
            <td>Amplitude of wave motion. A larger value leads to more pronounced oscillation.</td>
        </tr>
        <tr>
            <td>k</td>
            <td>0.05</td>
            <td>Wave Number. A larger value leads to more oscillations per unit length, or a more wrinkled flame.</td>
        </tr>
        <tr>
            <td>w</td>
            <td>10</td>
            <td>Angular Frequency. A larger value leads to quicker oscillations, or a higher frequency.</td>
        </tr>
        <tr>
            <td>wind</td>
            <td>1</td>
            <td>Skew. A negative value for "wind" would make a vertical flame lean to the left. A value of 0 would make it perfectly vertical. A positive value makes it lean to the right. The larger the value, the greater the lean.</td>
        </tr>
            <tr>
            <tr>
            <td>diffusion</td>
            <td>1</td>
            <td>A scale factor for both horizontal and vertical offset as well as shadow blur. A larger number leads to a flame which appears larger, though less intense.</td>
        </tr>
            <td>interval</td>
            <td>100</td>
            <td>Animation interval in milliseconds <a href="#request-animation-frame">†</a>. A larger value would lead to choppier animation, but demand less performance from a visitor's computer.</td>
        </tr>
        <tr>
            <td>flames</td>
            <td>array</td>
            <td>Array of shadows. The option "flames" can be set to a custom array, each element of which must be an object with strict properties as defined below. This allows for complete customisation of the effect. See <a href="#advanced-usage">advanced usage</a> for more details.</td>
        </tr>
    </tbody>
</table>
<table>
    <caption>Flame Object</caption>
    <thead>
        <tr>
            <th>Option</th>
            <th>Default</th>
            <th>Description</th>
        </tr>
    </thead>
    <tbody>
        <tr>
            <td>x</td>
            <td>0</td>
            <td>Start displacement. This value has little long term impact and is best left as 0. It represents the initial horizontal offset of a particular flame and as is used internally to store the position of that flame.</td>
        </tr>
        <tr>
            <td>hsla</td>
            <td>[58, 96, 89, 1]</td>
            <td>Colour of the shadow in <a href="http://css-tricks.com/yay-for-hsla/">HSLA</a>.</td>
        </tr>
        <tr>
            <td>y</td>
            <td>0</td>
            <td>Height vertical offset in em. It is best to pair increasing values of <code>y</code> with "<a href="http://en.wikipedia.org/wiki/Color_temperature">hotter</a>" colours.</td>
        </tr>
        <tr>
            <td>blur</td>
            <td>0.1</td>
            <td>Size/clarity of the shadow. Larger value leads to a bigger and less sharply defined shadow.</td>
        </tr>
    </tbody>
</table>

License
---
Copyright (c) 2012 Kevin Attfield
Dual licensed under the MIT and GPL licenses.
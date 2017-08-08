# Canvas2APNG

Canvas2APNG lets you make APNG animations with pure Javascript.
One JS file is needed to create animations of your changing canvas.
You can play the animation directly on your page or save it as a local
file (extension .png).  <br/>
For more info about APNG see: https://en.wikipedia.org/wiki/APNG

# Demo
Animation examples generated by Canvas2APNG.

![Basic animation.](Demo/demo_animation_basics.png)&nbsp;&nbsp;&nbsp;&nbsp;![Clock animation.](Demo/demo_animation_clock.png)

# Basic Usage

1. First you need to include the JS file in your html: <br/>
      *<script type="text/javascript" src="canvas2apng.js">  </script>*

2. To create an APNG animation you need a canvas element in your html: <br/>
      *<canvas id="myCanvas" >  </canvas>*
   In your script define: <br/>
      *var canvas = document.getElementById("myCanvas");*

3. Create an encoder object in your script (often a global var is useful): <br/>
      *window.encoder = new APNGencoder(canvas);*

4. The main structure of your script should be: <br/>
      Set encoder in start modus: **encoder.start();** 
      For each change of the canvas: **encoder.addFrame();**  
      Stop encoder, animation ready: **encoder.finish();** 

5. While writing your canvas changes you specify moments to write the canvas data to the encoder 
   with the command **encoder.addFrame();**.  <br/>
   Each time you add a frame to the encoder, the canvas image will be added to the animation.

6. After finishing the encoder you can save the animation data to an image element.  <br/>
   Or you can download the animation as a local file (extension .png).  <br/>
   See the demo application how to do that.

   **encoder.start();**  | // Encoder in start modus  
      **frames();**         | // Function with the js code of your canvas changes  
      **encoder.finish();** | // Encoder ready to give the animation result  

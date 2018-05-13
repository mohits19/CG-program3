# Computer Graphics (CSC 561)
### Program 3: Texture and Transparency

#### _Part 1_ (Textures)
This is achieved by sending corresponding texture coordinates for each vertex to the fragement shader. A new function called `setupTextures()` is added to setup the corresponding textures for each model. In the fragmetn shader, `texture2D` is used to obtain the required texture color to draw.

References:
1. http://learningwebgl.com/blog/?p=507
2. https://www.youtube.com/watch?v=hpnd11doMgc

#### _Part 2_ (Lighting)
A new uniform is defined in the fragment shader that represents one of three lighting modes according to which a different lighting formula is used. One of three possible values that can be sent to fragment shader is toggled when "B" is pressed. 

References:
1. http://www.glprogramming.com/red/chapter09.html

#### _Part 3_ (Transparency)
Another uniform is defined in the fragment shader that represents the alpha value of the material. This is used while setting `gl_FragColor` according to the currently set lighting mode. In `renderModels()`, the opaque models (alpha == 1.0) are rendered first and then the transparent models.

#### _Part 4_ (Depth Sorting) [Model by Model]
In `renderModels()`, all the opaque models are rendered as before. Then, all transparent models (triangles and ellipsoids) are sorted by z-value and rendered in order.
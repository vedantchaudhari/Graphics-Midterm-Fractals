# EGP-300 Inter Graphics & Animation Programming Midterm: Fractals
### Team Members
    * Vedant Chaudhari  
      Contributions: Mandelbrot Fractal and Newton Fractal (with Julia Set)
    * Aaron Hamilton
      Contributions: Mengersponge Fractal
##### Repository Link: <https://github.com/vedantchaudhari/Graphics-Midterm-Fractal.git>
##### UML Link: <https://drive.google.com/file/d/1CDbDxGHCubsT0LwMnzMnEV2BGgdXEHPn/view?usp=sharing>
##### Use master branch, most recent commit  

Licensed under the Apache License, Version 2.0 (the "License");
	you may not use this file except in compliance with the License.
	You may obtain a copy of the License at

		http://www.apache.org/licenses/LICENSE-2.0

	Unless required by applicable law or agreed to in writing, software
	distributed under the License is distributed on an "AS IS" BASIS,
	WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
	See the License for the specific language governing permissions and
	limitations under the License.

***
## Project Description
For our midterm project we developed shaders for three fractals: **The Mandelbrot Fractal**, **The Newton Fractal** and **The Mengersponge Fractal** as immediate real-time effects. Our goal for the project was to make the Mandelbrot fractal and the Mengersponge interactive by allowing the user to increase or decrease the amount of iterations used by the algorithm. For the Newton fractal our goal was to use a Julia set and generate the fractal colors using a color ramp, then we use the generated fractal to texture models.  

### Mandelbrot Fractal
![alt text](https://i.imgur.com/WSWJ6fy.png?1 "Mandelbrot Fractal")
Mandelbrot is a set of complex numbers for which the function does not diverge when iterated from the defined bounds i.e. x = 0. The fractal image is generated by sampling the complex number and testing each pixel for whether the sequence goes to infinity. If the sequence passes a predetermined threshold then it is colored black, otherwise it is colored using a standard coloring algorithm in HSV color space which is later converted to RGB.

### Newton Fractal
![alt text](https://i.imgur.com/GLaRPNt.png?1 "Newton Fractal")
The Newton fractal is a boundary set in the complex plane characterized by applying Newton's method to a fixed polynomial. In this implementation we used a Julia set, which works by dividing the plane into complex regions associated with the root of the polynomial. Furthermore the associated root is mapped to a color ramp in order to generate the required color for that pixel.

### Mengersponge Fractal
![alt text](https://i.imgur.com/QbaCP95.png "MengerSponge Fractal")
The Menger algorithm recursively divids each face of a cube into 9 squares. We have what is called the Mengersponge, which is the limit of this process after an infinite number of iterations. The Mengersponge will change with the viewport, taking into account distance and angle of the camera from the objects in the scene that have the Mengersponge effect on them. These 3D objects are the plane, a torus, a sphere and a cylinder.  

Our Project fits into the fractal category because it generates three unique fractal effects, one as a 2D texture and the other two as textures for 3D models. Furthermore, two shaders have a controllable number of iterations and the other uses a color ramp. We think our added functionality meets the project requirements.

##### Pertinent Code
* drawJulia_fs4x.glsl
* drawMandlebrot_fs4x.glsl
* drawMenger_fs4x.glsl
* passJulia_vs4x.glsl
* passMandlebrotComponents_transform_vs4x.glsl
* passMenger_vs4x.glsl
* a3_DemoState.c
* a3_demo_callbacks.c
* a3_DemoState.h
* a3_DemoShaderProgram.h

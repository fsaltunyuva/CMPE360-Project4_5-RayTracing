# CMPE360 Computer Graphics

## Project 4 & 5 - Ray Tracing

![Figure 2](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/Figure2.png)

We will create a ray tracer using Python in Blender. The scene is created in Blender, and we will use scripts to get information 
from the scene through Blender's Python API, and create our own routine for bouncing lights in the scene to get rendered images. The 
image above shows the two main steps to our final image. For shading, we will adopt a popular shading model called Blinn-Phong. It is a 
simple but sufficient (at least for this simple ray tracer) approximation of how light interacts with objects, and is adopted by OpenGL and 
Direct3D as the default-shading model. Read more [here](https://learnopengl.com/Advanced-Lighting/Advanced-Lighting).

> [!TIP]
> For Python development in Blender, it is easier to use the console/terminal since the Blender output will be there, making it easier for us to print 
debug information.

There are three main sections: 
1. Left: Text Editor. This is where we edit and run the code. 
2. Top right: 3D viewport. We can manipulate and preview the scene in this area. 
3. Bottom right: Image Editor. We will view our rendering results here.

To check if everything is working: 
From the Properties Editor, switch the Render Engine to SimpleRT. This is the new render engine that we just added to Blender 
by running the script. We will work on this render engine in this homework. The UI in Properties Editor should be refreshed. 
You should be able to see the "SimpleRT Render Settings" panel in the Render tab, and the "SimpleRT Dimensions" panel in the Output 
tab. If you still see the UI panels from other render engines, press F3 with your cursor in 3D Viewport, and type reload script and Enter to 
reload all the plugins.


Now your task is to edit the simpleRT_plugin to finish all the TODOs. 

In the code, we mostly use the data types that come with Blender. mathutils.Vector is the one we use to represent location, direction, and 
color. See basic usage here. The most common functions are:  
- vec.normalized() to return a normalized copy of vec 
- vec1.dot(vec2) to take the dot product of two vectors 
- vec.length_squared to get the squared vector length

To perform element-wise vector multiplication, the best way would be to convert the vectors to numpy arrays using arr = np.array(vec) , 
then use arr1 * arr2 to get the result. 

All the TODOs are listed as comments in the Python scripts. Please read them to get started. Here we will provide general guidelines and 
checkpoint images you can compare with. 

The ray-object intersection will be taken care of by the scene.ray_cast function from Blender. Our focus will be on how to use the 
intersection point and surface normal to figure out color calculations and light bouncing. 

## Shadow Ray
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/shadow-ray.png)

## Blinn-Phong Model (Diffuse and Specular Shading)
### Diffuse Shading
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/diffuse-shading.png)

### Diffuse Shading + Specular Shading
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/specular-shading.png)

## Ambient Light
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/ambient-light.png)

## Reflection 
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/reflection.png)

## Fresnel 
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/fresnel.png)

## Transmission 
![](https://github.com/fsaltunyuva/CMPE360-Project4_5-RayTracing/blob/main/README%20Figures/References/transmission.png)

Chapter4: Ray Tracing
=====================
_object rendering_: each object is considered in turn
_image-order rendering_: each pixel is considered in turn
> Ray Tracing is an image-order algorithm for making renderings of 3D scenes

## 4.1 The Basic Ray-Tracing Algorithm
a basic ray tracer have 3 parts:
- **ray generation** 
    which computes the origin and direction of each pixel's viwing ray based on the camera geometry
- **ray intersection** 
    find the cloeset object intersecting the viewing ray
- **shading**
    computes the pixel color based on the results of ray intersection
```python
for each pixel do
    computing viewing ray
    ray, surface norm n -> first object hit
    light, hit point, n -> pxiel color
```
-------------------
## 4.2 Perspective
**linear perspective** 
- **parallel projection**
    _orthographic_ _oblique_
- **perspective projection**
--------------------
## 4.3 Computing Viewing Rays
A ray is really just an origin point and a propogation direction,a 3D parametric line is ideal for this
$p(\mathbf{t}) = \mathbf{s} + t\mathbf{(e-s)}$
## 4.3.1 Orthographic Views
the pixel at position (i,j) in the raster images has the position
$u=l+(r-l)(i+0.5)/n_x$
$v=b+(t-b)(j+0.5)/n_y$
where $(u,v)$ are the coordinates of the pixel's position on the image plane
## 4.3.2 Perspective Views
all the rays have same origin

compute $\mathbf{w}$ and $\mathbf{w}$
ray.direction $\leftarrow -d\mathbf{w} + u\mathbf{u} + v\mathbf{v}$
ray.origin $\leftarrow e$

----------------------------
## 4.4 Ray-Object Intersection
### 4.4.1 Ray-Sphere Intersection
$\mathbf{p} =  \mathbf{e} + t\mathbf{d}$
$\mathbf{c} = (x_c, y_c, z_c)$
$\mathbf{(p-c)\cdot(p-c)} - R^2 = 0$
this is a classic quadratic equation in t
$discriminant < 0$ line and sphere do not intersect
$discriminant > 0$ line enter and leave the sphere
$discriminant = 0$ ray graze the sphere
### Ray-Triangle Intersection
the vertices of the triangle is in 3D space
$\mathbf{e} + t\mathbf{d} = \mathbf{a} + \beta \mathbf{(b-a)} + \gamma \mathbf{(c-a)}$
$\beta > 0 \quad \gamma > 0 \quad \beta + \gamma < 1$ intersection is inside the triangle, otherwise the ray hit the plane outside of the triangle.
if no solution, either the traingle is degenerate or the ray is paralled to the plane containing the traingle
### 4.4.3 Ray-Polygon Intersection
### 4.4.4 Intersecting a Group of Objects
----------------------------
## 4.5 Shading
### 4.5.1 Lambertian Shading
a surface facing directly toward the light receives maximum illumination
a surface tangent to tht light direction recevies no illumination
$L = k_dImax(0, \mathbf{n\cdot l} )$
$L:$ pixel color $k_d$ diffuse coefficient 
$I$ intensity of the light source
**this equation applies separately to the three color channels**
### 4.5.2 Blinn-Phong Shading
Lambertian Shading is _view independent_
the color of a surface does not depend on the direction from which you look


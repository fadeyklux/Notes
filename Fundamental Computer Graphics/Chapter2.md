Chapter2 Miscellaneous Math
=============================
## 2.5 Curves and Surfaces
### 2.5.1 2D Implicit Curves
_implicit equation_ $f(x,y)=0$
### 2.5.2 The 2D Gradient
$\nabla f(x,y)=(\frac{\partial f}{\partial x},\frac{\partial f}{\partial y})$
_normal vector_: vector perpendicular to the tangent vector of the curve at that point
gradient points indicate the direction of the f(x,y) > 0 region
- **implicit 2D lines**
- **implicit Quadric Curves**
$Ax^2+Bxy+Cy^2+Dx+Ey+F$
### 2.5.3 3D Implicit Surfaces
$f(x,y,z)=0$ 
### 2.5.4 Surface Normal to an Implicit Surface
A **surface normal** is a vector perpendicular to the surface.
Each point on the surface may havee a different normal vector
$\vec n = \nabla f(\vec p) = (\frac{\partial f(\vec p)}{\partial x},
\frac{\partial f(\vec p)}{\partial x}, 
\frac{\partial f(\vec p)}{\partial x})$

### 2.5.5 Implicit Planes
$(\vec p- \vec a) \cdot \vec n = 0 $
$\vec n = (\vec b - \vec a)\times(\vec c - \vec a)$
- **3D Quadric Surfaces**
- **3D Curves from Implicit Surfaces**
    A 3D curve can be constructed from the intersection of two simultaneous implicit equation
### 2.5.6 Parametric Curves
$\begin{bmatrix} x\\y \end{bmatrix} = \begin{bmatrix} g(t)\\h(t) \end{bmatrix}$ or $\vec p = f(t)$
- **2D Parametric Lines**
    $\begin{bmatrix} x\\y \end{bmatrix} = \begin{bmatrix} x_0+t(x_1-x_0)\\y_0+t(y_1 - y_0) \end{bmatrix}$
- **2D Parametric Circles**
    $\begin{bmatrix} x\\y \end{bmatrix} = \begin{bmatrix} x_c+r\cos\phi\\y_c+r\sin\phi \end{bmatrix}$

### 2.5.7 3D Parametric Curves
a spiral aroung the z-axis:
$ x=cost $
$ y=sint $
$ z=t $
- 3D Parametric Lines
    $ \vec p = \vec o + t\vec d$ 
### 2.5.8 3D Parametric Surfaces
$ x = f(u,v) $
$ y = g(u,v) $
$ z = h(u,v) $
- spherical coordinate system
    $ x = r\cos\phi sin\theta $
    $ y = r\sin\phi sin\theta $
    $ z = r\cos\theta $
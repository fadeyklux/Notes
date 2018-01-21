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
### 2.5.9 Summary of Curves and Surfaces
- **implicit curves in 2D / surfaces in 3D**
    scalar valued functions: $f: \mathbb{R}^2 \to \mathbb{R}$ or $f: \mathbb{R}^3 \to \mathbb{R}$
    $S = \{\mathbf{p} | f(\mathbf{p}) = 0 \}$
- **Parametric curves in 2D / 3D**
    vector valued functions of one variable $\mathbf{p}: D \subset \mathbb{R} \to \mathbb{R^2}$ or $\mathbf{p}: D \subset \mathbb{R} \to \mathbb{R^3}$
    $S = \{ \mathbf{p}(t) | t \in D \}$
- **Parametric surfaces in 3D**
    vecotr valued functions of two variables
    $\mathbf{p}: \subset \mathbb{R^2} \to \mathbb{R^3}$
    $S = \{ \mathbf{p}(t) | (u,v) \in D \}$
---------------------------
## 2.6 Linear Interpolation
points are connected by straight line segments
$f(x) = y_{i+1} + \frac{x-x_i}{x_{i+1}-x_i}(y_{i+1}-y_i)$
$(1-t)A+B$

----------------------------
## 2.7 Triangles
### 2.7.1 2D Traingles
area=$\frac{1}{2} \begin{vmatrix} x_b-x_a & x_c - x_a \\ y_b-y_a&y_c-y_a \end{vmatrix}$
> This area will have a positive sign if points a,b,c are in counterclockwise order and a negative sign,otherwise

- **barycentric coordinate**
$\mathbf{p} = \mathbf{a} + \beta(\mathbf{b}-\mathbf{a}) + \gamma(\mathbf{c} - \mathbf{a}) $
$\mathbf{p} = (1-\beta-\gamma)\mathbf{a} + \beta \mathbf{b} + \gamma \mathbf{c} $
$\mathbf{p} = \alpha \mathbf{a} + \beta \mathbf{b} + \gamma \mathbf{c}$ $\alpha+\beta+\gamma=1$
> A particular nice feature of barycentric coordinates is that a point p is insde the triangle formed by a,b,c if and only if
$0 < \alpha < 1$
$0 < \beta < 1$
$0 < \gamma < 1$
> if one of the coordinates is zero and the other two are between zero and one, then you are on an edge, If two of the coordinate are zeor, then the other is one, and you are at a vertex

- **how to compute?**
$\begin{bmatrix} x_b-x_a&x_c-x_a \\ y_b-y_a&y_c-y_a\end{bmatrix} \begin{bmatrix}\beta\\\gamma\end{bmatrix}=\begin{bmatrix}x_p-x_a \\ y_p-y_a\end{bmatrix}$
$\beta = \frac{f_{ac}(x,y)}{f_ac{x_b,y_b}}$
$\beta = \frac{(y_a-y_b)x + (x_b-x_a)y + x_ay_b - x_by_a}{(y_a-y_b)x_c + (x_b-x_a)y_c + x_ay_b - x_by_a}$
$A=A_a+A_b+A_c$ is the area of the traingle
$\alpha=A_a/A$
$\beta=A_b/A$
$\gamma=A_c/A$
> This rule still holds for points outside the triangle if the areas are allowed to be signed. note that these are signed areas and will be computed correctly as long as the same signed area computation is used for both A and subtriangles

## 2.7.2 3D Triangles
$\mathbf{p} = (1-\beta-\gamma)\mathbf{a} + \beta\mathbf{b} + \gamma\mathbf{c}$
$\mathbf{n=(b-a)\times(c-a)}$
$area=\mathbf{\frac{1}{2}\|(b-a)\times(c-a)\|}$
$\alpha=\mathbf{ \frac{n \cdot n_a}{\|n\|^2}}$
$\beta=\mathbf{ \frac{n \cdot n_b}{\|n\|^2}}$
$\gamma=\mathbf{ \frac{n \cdot n_c}{\|n\|^2}}$
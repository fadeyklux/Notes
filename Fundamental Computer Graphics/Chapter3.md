Chapter3 Raster Image
========================
_Pixel_ is short for picture element
A raster images is simply a 2D array that stores the pixel value for each pixel
image pixels != display pixel
## 3.1 Raster Devices
- Output
    - Display
        - Transmissive: liquid crystal display LCD
        - Emissive: light-emitting diode LED display
    - Hardcopy
        - Binary: link-jet printer
        - Continuous tone: dye sublimation printer
        _thermal dye transfer_ _donor ribbon_ _continous tone_
        _ppi:_ pixel per inch
        _dpi:_ dots per inch
        stair stepping
- input
    - 2D array sensor: digital camera
        _CCD_: charge-coupled devices
        _CMONS_: complimentary metal-oxide-semiconductor
    - 1D array sensor: flatbed scanner
------------------
## 3.2 Images, Pixels, Geometry
$I(x,y): R \to V$
$R \subset \mathbb{R^2}$ is a rectangular area and $V$ is the set of possible pixel values
### 3.2.2 Monitor intensities and Gamma
- monitors are nonlinear with respect to input
    displayed intensity = (maximum intensity)$a^\gamma$
    a in the input pixel value between 1 and 0
    describing a display's nonlinearity using $\gamma$ is only an **approximation**
## 3.3 RGB Color
```python
black = (0, 0, 0)
red = (1, 0, 0)
green = (0, 1, 0)
blue = (0, 0, 1)
yellow = (1, 1, 0)
magenta = (1, 0, 1)
cyan = (0, 1, 1)
white = (1, 1, 1)
```
## 3.4 Alpha Compositing
**pixel coverage** $\alpha$ fraction of pixel covered by the foreground layer
$c = \alpha c_f + (1-\alpha)c_b$
_alpha mask_ _alpha channel_
- Image Storage
    jpeg: lossy
    tiff: lossless
    ppm: lossless
    png: lossless
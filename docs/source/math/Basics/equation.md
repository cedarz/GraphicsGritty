# 计算

## 计算polygon（共面或者近似共面）的法线

VTK中计算polygon时候，如果遇到concave的多边形，可能会得到反向的法线，参考vtkPolygon::ComputeNormal计算问题[^1]，给出了来自Graphics Gems III的解决方法，Nevell's方法[^2]













[^1]: [vtkPolygon::ComputeNormal returns wrong directed normal if polygon has more concave than convex vertices](https://gitlab.kitware.com/vtk/vtk/-/issues/11988).
[^2]: [Graphics Gems III，V.5](https://theswissbay.ch/pdf/Gentoomen%20Library/Game%20Development/Programming/Graphics%20Gems%203.pdf)
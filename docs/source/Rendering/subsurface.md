# Subsurface Scattering

## 理论
- SIGGRAPH'2001 [A Practical Model for Subsurface Light Transport](https://graphics.stanford.edu/papers/bssrdf/bssrdf.pdf)
  - [bssrdf 效果](http://graphics.ucsd.edu/~henrik/images/subsurf.html)
- Normalized Diffusion [Approximate Reflectance Profiles for Efficient Subsurface Scattering](https://graphics.pixar.com/library/ApproxBSSRDF/)
- Random walk SSS [Path Traced Subsurface Scattering using Anisotropic Phase Functions and Non-Exponential Free Flights](https://graphics.pixar.com/library/PathTracedSubsurface/)
  - [brute-force-SSS](https://github.com/sakanaman/brute-force-SSS)
  - [volpt](https://github.com/yumcyaWiz/volpt)
  - [volppm](https://github.com/yumcyaWiz/volppm)
- SIGGRAPH 2016[Practical and controllable subsurface scattering for production path tracing](https://media.disneyanimation.com/uploads/production/publication_asset/153/asset/siggraph2016SSS.pdf)
  - [pbrlab](https://github.com/lighttransport/pbrlab)

## RTR
- SSSSS: [Screen-Space Subsurface Scattering](https://www.iryoku.com/sssss/)
- SSS: [Separable Subsurface Scattering](https://www.iryoku.com/separable-sss/)
- [Pre-Integrated Skin Shading](http://simonstechblog.blogspot.com/2015/02/pre-integrated-skin-shading.html)
- [](https://advances.realtimerendering.com/s2018/Efficient%20screen%20space%20subsurface%20scattering%20Siggraph%202018.pdf)

## PBR
- BSSRDF Importance Sampling [kulla](https://fpsunflower.github.io/ckulla/data/bssrdf.pdf), [imageworks](https://www.imageworks.com/sites/default/files/2023-10/BSSRDF-importance-sampling-imageworks-library-BSSRDF-sampling.pdf), [talks](https://blogs.autodesk.com/media-and-entertainment/wp-content/uploads/sites/162/s2013_bssrdf_slides.pdf)

## 实例
- blender（**EEVEE does not support the Random Walk methods**）
  - [cycles](https://docs.blender.org/manual/en/latest/render/shader_nodes/shader/sss.html)
    - Christensen-Burley:
    An approximation to physically-based volume scattering. This method is less accurate than Random Walk however, in some situations this method will resolve noise faster.

    - Random Walk (Fixed Radius):
    Provides accurate results for thin and curved objects. Random Walk uses true volumetric scattering inside the mesh, which means that it works best for closed meshes. Overlapping faces and holes in the mesh can cause problems.

    - Random Walk:
    Behaves similarly to Random Walk (Fixed Radius) but modulates the Radius based on the Color, Anisotropy, and IOR. This method thereby attempts to retain greater surface detail and color than Random Walk (Fixed Radius).

    - [Cubic and Gaussian subsurface scattering **Removed from 3.0**](https://developer.blender.org/docs/release_notes/3.0/cycles/)

## blog
- [基于物理着色（四）- 次表面散射-文刀秋二](https://zhuanlan.zhihu.com/p/21247702)
- [描述次表面散射（Subsurface Scattering）：BSSRDF 简介-zhiwei](https://zhuanlan.zhihu.com/p/508588218?utm_campaign=shareopn&utm_medium=social&utm_psn=1829436706396450816)
- [An Introduction To Real-Time Subsurface Scattering-therealmjp](https://therealmjp.github.io/posts/sss-intro/)

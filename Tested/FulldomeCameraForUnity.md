## 🎥 [FulldomeCameraForUnity](https://github.com/rsodre/FulldomeCameraForUnity)

A Unity tool for fulldome rendering, compatible with **HDRP** and Unity versions **2019.2+**.

### 🧰 Features

1. **Fulldome Camera**  
   - Renders the active camera as a 360° panorama using an internal **cubemap**.
   - Outputs a **Domemaster** (circular fisheye) projection.

2. **VFX Graph Support (Experimental)**  
   - Uses custom VFX blocks to distort particles around the camera like a fisheye lens.  
   - No reliance on camera tricks.

3. **Shader Graph Support (Experimental)**  
   - Distorts mesh vertices around the camera using custom Shader Graph nodes.  
   - Simulates fisheye lens effects at the shader level.

---

### ⚠️ Known Issues During Testing

- The generated output is a **square texture** (e.g., 4096×4096), regardless of whether it's rendered for 180° or 360°.
- This texture is **not equirectangular** and therefore **not directly compatible with sphere-based viewers**.
- The texture consists of:
  - An **inner fisheye circle** (usable for 180° dome projection from the top view).
  - An **outer ring of stretched content** representing the bottom half (not usable in standard full-sphere projections).
- This format may work for top-down hemispherical domes but fails for full-sphere or planetarium-style viewing without additional conversion or remapping.

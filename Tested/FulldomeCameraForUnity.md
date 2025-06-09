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

- 💬 [Unity Discussion Thread](https://discussions.unity.com/t/fulldome-camera-for-unity/712999)

---

### ⚠️ Known Issues During Testing

- The generated output is a **square texture** (e.g., 4096×4096), regardless of whether it's rendered for 180° or 360°.
- This texture is **not equirectangular** and therefore **not directly compatible with sphere-based viewers**.
- The texture consists of:
  - An **inner fisheye circle** (usable for 180° dome projection from the top view).
  - An **outer ring of stretched content** representing the bottom half (not usable in standard full-sphere projections).
- This format may work for top-down hemispherical domes but fails for full-sphere or planetarium-style viewing without additional conversion or remapping.

### ✅ Updated Testing Notes (09/06/25)

- Confirmed to work in **Unity 2022.3 (LTS)** — project can be exported and used without breaking.
- New setup tested using **two separate cameras**:
  - **One pointing upward**, and  
  - **One pointing downward**  
- Each camera renders to a **separate RenderTexture** rather than outputting a combined 360° view.
- This method works reliably and is **usable for fulldome rendering**, especially when targeting hemispherical domes.
- Avoids the previously unusable bottom-half distortion seen in the default single-texture setup.
- Offers flexibility for post-processing or custom dome mapping workflows.

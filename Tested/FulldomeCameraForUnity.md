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

### 🧪 Usage Methods

#### 🔁 Method 1: Default Domemaster Output
- Renders a **single square texture** (e.g., 4096×4096) with:
  - An **inner fisheye circle** (usable for 180° top-down dome projection).
  - An **outer ring of stretched bottom content** (not ideal for full-sphere use).
- This format is **not equirectangular** and is **not directly usable with spherical or planetarium viewers**.
- Best suited for **top-down hemispherical domes**, but **not recommended for full 360° immersive domes** without post-processing remapping.

#### 🌀 Method 2: Cubemap to Equirectangular Shader (Recommended)
- Includes a **custom shader** that converts a rendered **cubemap** to an **equirectangular** texture.
- This method produces output that is **compatible with full-dome projection systems** and **sphere-based viewers**.
- Does not require camera angle splitting or remapping workarounds.
- Suitable for planetariums, immersive spheres, and general dome workflows.

### ✅ Updated Testing Notes (09/06/25)


- Shader-based equirectangular conversion tested and confirmed **usable in Unity 2022.3 (LTS)**.
- ⚠️ **Performance Note:** Running in Unity 2022 may cause noticeable FPS drops due to **HDRP overhead** and **multiple render passes**, especially on mid-range systems.
- Recommended to optimize camera settings and consider lower texture resolutions for real-time playback.

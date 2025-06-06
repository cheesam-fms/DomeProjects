## 🔧 [DomeTools](https://github.com/prefrontalcortex/DomeTools)

A powerful Unity plugin for creating immersive dome experiences, supporting Built-in Render Pipeline, URP, and HDRP.

### 🎨 Dome Creator

Provide two rendering techniques:

#### 1. **Dome Warp** ⚡ – *Single-View, Dome-Invariant Rendering*
A novel and highly optimized approach for real-time dome content.

- Much faster (renders from a single camera view)
- Compatible with post-processing and volumetric effects (no visible seams)
- Ideal for real-time applications and spatial content (content surrounding the viewer)
- Limited to a 180° view angle
- Allows creative control over perceived scene depth

#### 2. **Traditional Cubemap-Based Rendering** 🔮
Classic method using multiple camera views.

- Slower (renders 5 or 6 views depending on configuration)
- Post-processing artifacts may appear at seams
- Best for horizontal/horizon-based content (e.g., streets, landscapes)
- Fixed dome center viewpoint
- Flexible view angles (up to 360°)

#### Additional Features:
- ✨ Supports NDI sender for live preview in a connected dome viewer

---

### 🕶️ Dome Viewer

A standalone virtual dome viewer application.

- Simulates dome environments in VR and desktop
- Compatible with **Windows**, **Meta Quest 2**, and **Meta Quest 3**

---

### ⚠️ Known Issues During Testing

- **360° Fulldome Rendering Limitation (Dome Warp Method)**  
  Attempting to use two vertically placed cameras (top and bottom) with Dome Warp does **not** produce a full 360° dome image. Dome Warp is currently limited to hemispherical (180°) views only.

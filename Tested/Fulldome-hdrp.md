[fulldome-hdrp](https://github.com/thebelin/fulldome-hdrp)

An open-source **HDRP-compatible** camera system for rendering fulldome content in Unity.

### 🧰 Features

- Built using Unity’s **Scriptable Render Pipeline (SRP)** with **HDRP support**
- Supports multiple dome projections:
  - **180°**
  - **220°**
  - **EAC (Equal-Angle Circular)**
- Developed for use in **Dome Lab** projects
- Usable with a setup of **six cameras** to render cube faces for dome warping

### ⚠️ Performance Note

- In some setups, an **additional two cameras** (pointing up and down) are used to output the render result.
- While this provides flexible control for dome projection output, the **combination of eight active cameras** (6 for cubemap + 2 for output) can **significantly impact performance**, especially when rendering to **RenderTextures** or in real-time environments.

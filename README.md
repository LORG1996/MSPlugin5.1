<img width="486" height="440" alt="image" src="https://github.com/user-attachments/assets/56ed9dc4-0afd-482b-a5ab-b52ac9011f26" />

# 🌿 Quixel Megascans LiveLink for Blender 5.1+

This is a refactored and optimized version of the Quixel Bridge Livelink plugin, specifically rebuilt to support **Blender 4.2, 5.0, and 5.1+ (EEVEE Next)**.

## 🚀 Why this version?

Original plugins often fail in modern Blender versions due to major changes in the rendering engine. This fix addresses:

* **EEVEE Next Compatibility:** Fixed `AttributeError` by removing deprecated `blend_method`. It now uses the modern **Dithered** transparency system. 💎
* **The "Lambert" Fix:** Automatically clears the default `lambert` material and ensures the imported Megascans material is correctly assigned. 🛠️
* **Advanced Foliage Shading:** A custom node setup using `Mix Shader` + `Translucent BSDF` with a dedicated **Normal Map** input for realistic light scattering through leaves. 🍃
* **Smart Slot Assignment:** * If you import a new asset (like a grass pack), it assigns materials to all new objects.
    * If you have an object selected, it smartly replaces the material in the **active slot**. 🧠

---

## 🛠️ Installation

1.  **Download** the [MSPlugin5.zip](https://github.com/user-attachments/files/26677225/MSPlugin5.zip) archive.
2.  Open **Blender 5.1**.
3.  Go to `Edit` > `Preferences` > `Add-ons`.
4.  Click **Install...** and select the downloaded archive.
5.  Enable **Import-Export: Megascans Plugin**. ✅
6.  Press `N` in the 3D Viewport to find the **Megascans** tab and click **Start Megascans Link**. 🔌

---

## 📖 How to Use

### 1. Importing Assets 📦
* Simply hit **Export** in Bridge. 
* The plugin will build the node network, connect textures, and set up the transparency automatically.

### 2. Smart Material Replacement 🎯
* To update a specific part of your model:
    1.  Select your object in Blender.
    2.  Highlight the **Material Slot** you want to change.
    3.  Hit **Export** in Bridge.
    4.  The plugin will replace only the active slot! 🦄

### 3. Adjusting Translucency 💡
* In the **Shader Editor**, you will find a **"Translucency Strength"** (Value node).
* Adjust this slider to control how much light passes through the surface (perfect for vegetation).

---

## 🧪 Technical Node Setup
The plugin automatically generates a clean, organized node tree:
* **Albedo + AO**: Mixed via Multiply.
* **Normal Map**: Correctly linked to both *Principled* and *Translucent* shaders.
* **Roughness & Opacity**: Auto-connected with correct Color Space.
* **Displacement**: Configured for 'Both' (Bump + Displacement) for Cycles.
* **Mix Shader Logic**: Blends the main shader with Translucency for high-end archviz results.

---

**Happy Rendering!** 🎨✨




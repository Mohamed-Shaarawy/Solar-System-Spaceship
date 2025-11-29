# Solar System Spaceship

A 3D **OpenGL-powered space exploration game** where players pilot a spaceship through a vast, procedurally generated solar system. With realistic physics and immersive visuals, the player navigates the endless expanse of space.

---

## ✨ Features

- **Immersive 3D Space Exploration**
  - First/third-person spaceship camera
  - Smooth ship controls (thrust, pitch, yaw, roll)

- **Procedurally Generated Solar System**
  - Multiple planets and moons with varying sizes and orbits
  - Configurable parameters for number of bodies, distances, and variation

- **Realistic (or Stylized) Physics**
  - Thrust and damping for ship movement
  - Collision checks with planets / obstacles

- **OpenGL Rendering**
  - 3D rendering with perspective projection
  - Lighting, shading, and basic materials
  - Skybox / background stars
  - Textured planets
---

## 🧱 Project Structure

The project is organized primarily at the repository root, with source files, headers, shaders, textures, and Visual Studio project files side by side.

```text
Solar-System-Spaceship/
├─ .gitattributes
├─ .gitignore
├─ .idea/                         
├─ Debug/                         # Debug build artifacts (Visual Studio)
├─ x64/                           # Platform-specific build artifacts
├─ Lab6.sln                       # Visual Studio project
├─ Lab6.vcxproj                  
├─ Lab6.vcxproj.filters
├─ Lab6.vcxproj.user
│
├─ GLFW_Version.cpp               # Main entry point (run this)
├─ InitShader.cpp                 # Shader initialization utilities
├─ LoadTwoModelscpp.cpp           # Example/model loading code (extra)
├─ glad.c                         # GLAD OpenGL loader implementation
│
├─ Camera.h                       # Camera handling (view/projection, movement)
├─ Mesh.h                         # Mesh abstraction (geometry)
├─ Model.h                        # Model abstraction, possibly multiple meshes
├─ Shader.h                       # Shader program wrapper
├─ Sphere.cpp                     # Sphere geometry (planets)
├─ Sphere.h
├─ stb_image.h                    # Image loading (textures)
│
├─ include/                       # Additional headers / third-party includes
├─ barrels/                       # Barrel model and resources
├─ futuristic-spaceship/          # Spaceship model and resources
├─ kurt/                          # Additional assets/models
│
├─ fshader.glsl                   # Fragment shader
├─ vshader.glsl                   # Vertex shader
├─ fshader22.glsl                 # Alternative fragment shader
├─ vshader22.glsl                 # Alternative vertex shader
├─ skybox_fshader.glsl            # Skybox fragment shader
├─ skybox_vshader.glsl            # Skybox vertex shader
│
├─ model_1.txt                    # Geometry / model data
├─ model_2.txt
│
├─ 2k_neptune.jpg                 # Planet textures
├─ 2k_uranus.jpg
├─ 8k_earth_daymap.jpg
├─ 8k_jupiter.jpg
├─ 8k_mars.jpg
├─ 8k_mercury.jpg
├─ 8k_moon.jpg
├─ 8k_saturn.jpg
├─ 8k_saturn_ring_alpha.png
├─ 8k_sun.jpg
├─ 8k_venus_surface.jpg
├─ astroidsTex.jpg
├─ barreltex.png
├─ dark-blue-water.jpg
├─ earth2048.bmp
├─ fueltankTex.jpg
├─ rock.png
│
├─ bkg1_back.png                  # Skybox / background textures
├─ bkg1_bot.png
├─ bkg1_front.png
├─ bkg1_left.png
├─ bkg1_right.png
├─ bkg1_top.png
├─ space_bk.png
├─ space_dn.png
├─ space_ft.png
├─ space_lf.png
├─ space_rt.png
├─ space_up.png
│
├─ Diffuse maps.png               # Reference image for textures
├─ README.md             
```


### Main Components

- **`GLFW_Version.cpp`**
  - Entry point of the application
  - Creates the window & OpenGL context (via GLFW + GLAD)
  - Initializes shaders, loads models/textures, and runs the main loop

- **Core / Rendering**
  - `Shader.h` – loads, compiles, and links GLSL shaders (`vshader*.glsl`, `fshader*.glsl`, skybox shaders)
  - `Camera.h` – manages view and projection matrices, handles movement and mouse look
  - `Mesh.h` – represents raw geometry (vertices, indices, buffers)
  - `Model.h` – higher-level wrapper around one or more meshes and textures
  - `Sphere.cpp` / `Sphere.h` – generates sphere geometry for planets and possibly the sun

- **OpenGL / Platform**
  - `glad.c` – GLAD loader implementation used to access modern OpenGL functions
  - `InitShader.cpp` – helper for compiling/linking shaders and returning program IDs

- **Assets & Models**
  - `futuristic-spaceship/` – 3D spaceship model and textures
  - `barrels/`, `kurt/` – additional models / sample assets
  - `model_1.txt`, `model_2.txt` – custom model geometry in text format
  - Planet textures like `8k_earth_daymap.jpg`, `8k_mars.jpg`, etc.
  - Skybox textures like `space_*.png`, `bkg1_*.png`

---

## 🛠️ Technologies & Dependencies

- **Graphics / Windowing**
  - OpenGL 3.x/4.x core profile
  - GLFW (for window + input)
  - GLAD (OpenGL function loader, via `glad.c` + headers)
- **Math / Utilities**
  - GLM (for vectors, matrices, and transforms) – headers typically under `include/`
- **Assets**
  - `stb_image.h` (texture loading)

All required libraries are bundled in the project tree (e.g., `include/`, `glad.c`, `stb_image.h`), so you don’t need to install them separately if you build with the provided Visual Studio solution.

---

## 🚀 Getting Started

### Prerequisites

- **C++ compiler**
  - C++17 support
- **OpenGL-capable GPU & drivers**
- **Visual Studio** (recommended, since the repo includes `.sln` / `.vcxproj`)
  - Alternatively, another IDE/toolchain if you set up your own project and include the same sources.

All the dependencies you need are included in the repository.

### Clone the Repository

```bash
git clone https://github.com/Mohamed-Shaarawy/Solar-System-Spaceship.git
cd Solar-System-Spaceship
```

---

## 🧩 Building the Project

### Visual Studio (recommended)

1. Open `Lab6.sln` in Visual Studio.
2. Make sure the configuration is set to **Debug** or **Release**, and the platform to **x64** (to match the provided folders).
3. Build the solution.
4. Set `GLFW_Version.cpp` (or its generated target) as the startup project if needed.
5. Run the project from Visual Studio.

On success, you should get an executable similar to:

```powershell
.\Debug\Solar-System-Spaceship.exe
```

(Exact name/path may differ depending on your configuration.)

---

## 🎮 Controls & Gameplay

Update to reflect your real key bindings and gameplay behavior.

### Default Controls (Example)

- **Movement**
  - `W` / `S` – Thrust forward / backward
  - `A` / `D` – Yaw left / right
  - `Q` / `E` – Roll left / right

- **Camera**
  - Mouse move – Look around

- **Misc**
  - `Esc` – Quit

### Gameplay Loop

1. **Launch the game**  
   Run the built executable. A window should appear with the spaceship and the solar system.

2. **Explore the solar system**
   - Use the movement controls to navigate around planets and other celestial bodies.
   - Approach planets to see them up close; fly outwards to appreciate the scale.

---

## 📦 Assets

- **Textures** – planet textures (Earth, Mars, Jupiter, etc.) and sun/skybox textures (NASA or other open sources).
- **Models** – spaceship and other 3D models under `futuristic-spaceship/`, `barrels/`, `kurt/`, and in `model_*.txt`.

---

## 🗺️ Roadmap / Future Work

Ideas for extending the project:

- Mission system (delivery, exploration, scanning objectives)
- Detailed planetary surfaces and landing
- Advanced physics: orbital mechanics, gravity slingshots
- AI ships and traffic
- Multiplayer (co-op exploration)
- In-game photo mode / cinematic camera
- Save/load system for player progress and discovered systems

---

## 📝 License

This project is for educational purposes only.

```text
MIT License
Copyright (c) 2025 Mohamed Shaarawy
```

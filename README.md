# OpenGL Still-Life Scene

**CS-330: Computational Graphics and Visualization**

An interactive 3D still-life scene created in C++ using OpenGL.

The project recreates a collection of real-world objects by combining basic 3D meshes, transformations, textures, materials, lighting, and an interactive camera system.

![Rendered OpenGL Scene](Source/scene_image_model.png)

## Technologies

- C++
- OpenGL
- GLFW
- GLEW
- GLM
- GLSL
- stb_image
- Visual Studio

## Scene Overview

The scene is constructed from reusable primitive meshes rather than imported 3D models.

Objects include:

- Ceramic-style vase
- Water jug
- Trash can
- Dumbbell / hand weight
- Handheld 3DS-style game console
- Textured ground surface

Each object is assembled from combinations of primitive geometry such as:

- Boxes
- Cylinders
- Tapered cylinders
- Spheres
- Toruses
- Prisms
- Planes

Scaling, rotation, and translation are used to position the individual meshes and combine them into more complex objects.

## Textures and Materials

The scene uses multiple image textures to give objects distinct surface appearances.

Texture loading includes:

- Image loading through `stb_image`
- OpenGL texture creation
- Texture wrapping
- Linear filtering
- Mipmap generation
- Texture-slot binding

Different material definitions are also used to control how surfaces react to light.

The project defines material types with varying:

- Ambient strength
- Diffuse color
- Specular color
- Shininess

These range from highly reflective surfaces to dull or non-reflective materials.

## Lighting

The scene contains multiple configurable light sources positioned around the environment.

Lighting properties include:

- Position
- Ambient color
- Diffuse color
- Specular color
- Focal strength
- Specular intensity

The different lights are used to control how textures and materials appear across the scene and to create depth between the modeled objects.

## Camera Controls

The scene includes an interactive 3D camera.

### Movement

- `W` — Move forward
- `S` — Move backward
- `A` — Move left
- `D` — Move right
- `Q` — Move up
- `E` — Move down

### View Controls

- Mouse movement — Rotate the camera
- Mouse wheel — Adjust camera movement/zoom behavior
- `P` — Perspective projection
- `O` — Orthographic projection
- `Esc` — Close the application

The application supports switching between perspective and orthographic views while the scene is running.

## Scene Rendering

The rendering process separates several responsibilities:

- Window and OpenGL initialization
- Shader management
- Camera and view management
- Scene preparation
- Texture loading
- Material configuration
- Lighting configuration
- Object transformations
- Mesh rendering

Each frame updates the view and projection data before rendering the composed scene.

## Project Structure

### `Source/MainCode.cpp`

Initializes GLFW and GLEW, loads shaders, prepares the scene, and runs the main rendering loop.

### `Source/SceneManager.cpp`

Handles scene-specific rendering including:

- Object transformations
- Textures
- Materials
- Lighting
- Mesh composition
- Scene rendering

### `Source/ViewManager.cpp`

Handles:

- Camera movement
- Mouse input
- Keyboard input
- View matrices
- Perspective projection
- Orthographic projection

### `Source/scene_image_model.png`

Image of the completed rendered scene.

### `Source/scene_image_original.png`

Reference image used during the scene-design process.

## Development Approach

The project was developed incrementally by breaking the reference scene into smaller objects and then breaking each object into primitive shapes.

The general workflow was:

1. Identify the major objects in the reference scene.
2. Determine which primitive meshes could represent each component.
3. Scale, rotate, and position those meshes.
4. Apply appropriate textures and materials.
5. Configure scene lighting.
6. Test camera movement and viewing angles.
7. Iterate on object proportions, placement, textures, and lighting.

This approach allowed complex objects to be constructed from reusable components while keeping the rendering logic organized.

## Course Framework

This project was built using the OpenGL framework supplied for the course.

The provided framework includes supporting graphics infrastructure such as shader and mesh management. The scene-specific work builds on that framework by configuring and composing the objects, transformations, textures, materials, lighting, and final scene presentation.

## Skills Demonstrated

- C++
- OpenGL
- 3D Transformations
- Texture Mapping
- Material Properties
- Lighting
- Camera Systems
- Perspective Projection
- Orthographic Projection
- Primitive Mesh Composition
- Interactive Graphics
- Computational Graphics

## Course Context

This project was completed for **CS-330: Computational Graphics and Visualization** at Southern New Hampshire University.

The project focused on translating a 2D reference image into an interactive 3D scene while applying concepts in modeling, transformations, textures, lighting, camera movement, and rendering.

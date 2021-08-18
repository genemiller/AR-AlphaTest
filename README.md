# AR-AlphaTest

Unity Project containing several of Darcy Gerbarg’s artworks for the AR Installation Alpha Test.
NOTE: See bottom of this README for initial Release (6/15/2021).

---
# 2nd Release - 6 Animated Paintings
- 8/17/2021
- Gene Miller


The 6 painting are named:
1. Assignment
2. Celebration
3. Forgetting
4. Incurred
5. Manic improv
6. Trope

## Discussion of what each of the 6 AR objects should look like
Each object consists of two instance of a framed painting.
Each instance consist of a two sided painting, a title/signature cutout applied to each side of the painting, and a frame.
One of the the two instance is rotated 90 around its center Y axis so that the object appears as a cross when viewed from above.
Each object is animated to rotate around its center Y axis, with a 360 degree rotation every 30 seconds.
Each object is scaled and positioned with its bottom 1 ft above ground and its mid point at eye level (5.5 ft)
The top of each object is 10 ft above the ground.
The total height, width, and depth of each object is 9 ft.


## Discussion of FBX files
To build an AR object for each of the 6 paintings, you will probably want to use the 6 FBX files and corresponding textures contained in the Assets folder.

The folder Assets/FBXTestOutput contains 6 FBX files, one for each of the 6 animated painting (see FBXTestOutput list below)
Each FBX file contains animation, geometry and material properties for the painting assemblage.
Each assemblage contains a painting a frame, and titles/signatures.
The folder Assets/DGPaintings/2021PaintingTexturess contain the jpg image for each of the 6 animated paintings.

## Discussion of material property issues
Two Material Properties in Unity were not properly exported to the FBX files

1. The Unity *Emission* material property does not seem seem to be present in the FBX files.
	- Consequently the paintings appear too dim.
2. The *Cutout* Rendering Mode in Unity does not seem to be present in the FBX files.
	- Consequently the title/signature overlays are not rendered correctly.

If the AR framework supports these material properties, then they should be added manually.

## Asset folders and files added since Release 1

#### Scenes:
Scenes for object development and testing
- AR_Assets.unity
	- To illustrate the 6 animated paintings 
- FBXTest.unity
	- To compare the 6 FBX output files to the 6 original paintings

#### Animation:
- PaintGateDay2021.anim
	- Unity animation file
- PaintGateDay2021.controller
	- Unity animation controller

#### DGPaintings
- 2021Meshes
	- Mesh template
- 2021PaintingMaterials
	- Materials for 6 paintings
- 2021PaintingTexturess
	- Textures for 6 paintings
- 2021Prefabs
	- Double Sided Framed Painting Prefab
- 2021SignatureMaterials
	- Signature Materials for 6 paintings
- 2021SignatureTextures
	- Title and Signature Textures for 6 paintings
- DG-Pale-Frame.mat
	- Material for frames

#### FBXTestOutput
6 Exported FBX Files
- DG-Assignment.fbx
- DG-Celebration.fbx
- DG-Forgetting.fbx
- DG-Incurred.fbx
- DG-Manic Improv.fbx
- DG-Trope.fbx

#### FPC
First Person controller for testing

#### Player.prefab
First Person camera for testing


#### ProjectSettings
- FbxExportSettings.asset
	FBX Export Package


#### TL15_11.fbx
- 3DVR Painting artwork geometry in FBX format - same geometry as GLB file without images



---

# Inital Relase - 2 Animated Paintings and 1 3DVR sculpture
- Initial release 6/15/2021
- Gene Miller

The artworks are named:
1.	Violet Brush (animated framed painting)
2.	Party (animated framed painting)
3.	TL15_11 (3D Painting)

## Assumptions and questions

- Assumption 1. Darcy Gerbarg and the Alpha Test team will decide locations, orientations, and scales for each of the three artworks.
  - Each artwork is currently prepared with bottoms near ground level, and tops about double the height of a person (e.g. 3 to 4 meters)

- Assumption 2. The Alpha Test team will be using a Game Engine (such as Unity3D.)
  - NOTE: The models are currently packaged as a Unity3D Project – Version  2019.4.
  - Does Alpha Test team prefer a different Game Engine? (e.g. Unreal)

- Assumption 3. The Alpha Test team will be using an AR SDK (such as Google ARCore)
  - NOTE: An AR SDK has NOT yet been integrated with the Unity3D Project 
  - Does the Alpha Test team plan to integrate the AR SDK?
  - Or should Gene Miller integrate the AR SDK? (which one?)


## Asset folders and files

#### Scenes: (scenes for each of three artworks)
- VioletBrush.unity
    - VioletBrush is enabled, other two objects are disabled
- Party.unity
    - Party object is enabled, other two objects are disabled
- TL15.unity
    - TL15 object is enabled, other two objects are disabled

#### Texture: (textures for two paintings)
- Violet Brush-Brighter 32x18 75dpi.jpg
- DG-Party+TL220180509-181050D1C2 54x54 75dpi 2018.jpg
- Darcy Gerbarg 2021 sig.png

#### Materials: (materials for two paintings)
- VioletBright.mat
- DG-Party.mat
- DG-Wood-Frame.mat
- Signature-Black.mat
- Signature-White.mat

#### Animation:   (animation for two paintings)
- Pivot.controller
- PivotCamera.anim

#### Ciconia Studio Shaders: (Double-sided emissive shader for two paintings)
- Double Sided Emissive Diffuse.shader

#### TL15_11.glb (3D Painting artwork; materials and textures included in GLB file)

#### TiltBrush: (Tiltbrush shaders required for TL15_11.glb)

#### ThirdParty: (Required for TiltBrush)


## Operational Steps (based on Assumptions listed above)
1. Download this GitHub repository (https://github.com/genemiller/AR-AlphaTest)

2.  Open the Unity Project AR-AlphaTest (Note: this Project was tested with Unity Version 2019.4.2f1)

3. Integrate with AR toolkit (E.g. Google AR-Core)

4. For each of the three scenes:
        1. VioletBrush
        2. Party
        3. TL15
   1. Load the scene
   2. Unload the other two scenes
   3. Build for target platform(s) (e.g. Android)
   4. Deploy the build file(s) (e.g., APK) to target platform (e.g. Android)

5. Review the results (consult with Gene Miller if there are bugs)

6. Provide build files (or AR Package integration) to Darcy Gerbarg and Gene Miller (who will also review the results)

8. Discuss possible changes, e.g.,
   - Scale, height, orientation
   - Timing and degree of animation
   - Whether colors and shading look right

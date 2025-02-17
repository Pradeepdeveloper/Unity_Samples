# Changes in Fbx Exporter



## [2.0.2-preview.1] - 2019-06-20

NEW FEATURES

* It is no longer necessary to manually create Prefab Variants for FBX files. 
* Added **Convert to FBX Linked Prefab** menu item for creating FBX Linked Prefabs. FBX Linked Prefabs are Prefab Variants of the exported FBX's Model Prefab.
* Updated the documentation.

FIXES
* Fixed error when exporting selected Timeline Clip

## [2.0.1-preview.11] - 2019-04-10

CHANGES
* Fixed ExportTimelineClipTest failing in unit tests.

## [2.0.1-preview.10] - 2019-04-01
FIXES
* Fixed the integration files that were still missing. These were ignored by ``.npmignore` (created when running Package Validation).

## [2.0.1-preview.9] - 2019-04-01
FIXES
* Fixed the missing integration files in the previous release.

## [2.0.1-preview.8] - 2019-03-29
FIXES
* Fixed the `FbxExportSettings` compile error on 2018.3.

## [2.0.1-preview.7] - 2019-03-22
FIXES
* Fixed the issue where the Autodesk® 3ds Max® 2020 integration was hanging during installation.
* Fixed the duplicate DCCs showing in the integration install dropdown menu if `MAYA_LOCATION` was set.

## [2.0.1-preview.6] - 2019-02-08
CHANGES
* Updated the `package.json` manifest file.
* Reverted the change to the Runtime asmdef file.
* Fixed the non-deterministic behavior in tests.
* Updated the dependence on **com.autodesk.fbx** to version **2.0.0-preview.7**.

## [2.0.1-preview.5] - 2019-02-01

CHANGES
* Updated the dependence on **com.autodesk.fbx** to version **2.0.0-preview.6**.
* Updated the asmdef files to only include Editor platforms.

## [2.0.1-preview.4] - 2019-01-31
CHANGES
* Updated the **unityRelease** version in the `package.json` manifest file.

## [2.0.1-preview.3] - 2019-01-24
CHANGES
* Moved tests to a separate `.tests` package
* Added a dependency on Timeline.
* Export of blendshapes is experimental, YMMV.

## [2.0.1-preview.2] - 2018-12-05

CHANGES
* Updated the dependence on **com.autodesk.fbx** to version **2.0.0-preview.4**.

## [2.0.1-preview.1] - 2018-12-04
CHANGES
* Updated the dependence on **com.autodesk.fbx** to version **2.0.0-preview.3**.

## [2.0.1-preview] - 2018-11-13
NEW FEATURES
* For Unity 2018.3 and later, Prefab Variants replaced Linked Prefabs. Linked Prefabs were created by adding an `FbxPrefab` component to a Regular Prefab in order to connect it to an FBX file.
* The **Convert To Linked Prefab** menu items have been removed.
* Updated the documentation.

FIXES
* Fixed the error when exporting SkinnedMesh with bones that are not descendants of the root bone.
* Fixed an issue where animation-only exporting was not actually exporting animation in v2.0.0.
* Fixed calculating the center of root objects when exporting "Local Pivot"/"Local Centered".

KNOWN ISSUES
* In Unity 2018.3, exported blendshape normals may not match the original blendshape normals.

## [2.0.0] - 2018-06-22
NEW FEATURES
* The FBX Exporter is now distributed via the Package Manager.
* Added support for Physical Cameras
* The FBX Exporter is now compatible with Unity 2018.2.
* Roundtripping Assets can now be started from Autodesk® Maya® with Assets that have not been exported from Unity.
* The DCC integration plug-in sources have been removed from the packages folder. You can still find them in the zip file.
* The FBX Exporter now uses the FBX SDK version 2018.1.
* Conformed to Unity's API guidelines.
* Added support for exporting constraints (Rotation, Aim, Position, Scale, and Parent).
* ConvertToPrefab: Add the ability to convert an FBX file or a Prefab Asset from the Project view.
  * Right-click on an FBX file in the Project view and then select **Convert to Linked Prefab** to create a Linked Prefab Asset for the FBX file. It will not create an instance in the Scene.
  * Right-click on a Prefab in the Project view and select **Convert to Linked Prefab** to export the Prefab to an FBX file and link the existing Prefab to the newly created FBX file.

FIXES
* Fixed skinned mesh bone update when the number of bones changes between updates.
* Keyframes were sometimes missing when exporting animation curves.
* Fixed the visibility of the file name fields in the FBX Export dialog in Unity Pro's dark theme.

KNOWN ISSUES
* ConvertToPrefab: the UI doesn't provide feedback about whether it will convert an existing file or create new files.
  * When converting an existing FBX file, the FBX filename and FBX Export options are ignored (but not greyed out).
  * When converting an existing Prefab, the Prefab filename is ignored (but not greyed out)

## [1.7.0] - 2018-06-01

FIXES

* Fixed violations of the C# Framework Design Guidelines (FDG).
* Fixed errors reported while running the Package Validation Suite.

## [1.6.0] - 2018-05-29

NEW FEATURES

* Added support for Physical Cameras.

FIXES

* Fixed skinned mesh bone updates.

## [1.5.0]

NEW FEATURES

* Roundtripping Assets can now be started from Maya using Assets that have not been exported from Unity.
* DCC integration plug-in sources have been moved out of the package.
* The Windows version is now using the FBX SDK version 2018.1.1.
* Streamlined public interface for the `ModelExporter` class.

FIXES:

* The DCC integration plug-ins now work with the Package Manager.

## [1.4.0]

NEW FEATURES

* The FBX Exporter is now distributed via the Package Manager.
* The FBX Exporter now exports Unity constraints to FBX.
* The FBX Exporter now adds the ability to convert an FBX or Prefab Asset from the Project view.

FIXES:

* The FBX Exporter is now compatible with Unity 2018.2.0b3.
* Fixed an issue where the last frame was sometimes not exported.
* Fixed an issue where the FBX export dialog was hard to read in Unity Pro's dark theme.

KNOWN ISSUES

* The UI doesn't provide feedback about whether it will be converting an existing file or creating new files with ConvertToPrefab.
* When converting an existing FBX file, the FBX Filename and FBX Export options are ignored (but not greyed out).
* When converting an existing Prefab, the Prefab Filename is ignored (but not greyed out).

## [1.3.0f1] - 2018-04-17
NEW FEATURES
* `Unity3dsMaxIntegration`: 
	* Allows multiple file import.
	* Allows multiple file export by scene selection.
* `FbxExporter`: Export animation clips from Timeline
* `FbxExportSettings`: 
	* Added new UI to set export settings.
	* Added option to transfer transform animation on export.
	* Added option to export model only.
	* Added option to export animation only.
	* Added option not to export animation on skinned meshes.
	* Added option to export meshes without renderers.
	* Added LOD export option.
* `UnityMayaIntegration`: 
	* Allows multiple file import.
	* Allows multiple file export by scene selection.
* `FbxPrefabAutoUpdater`: Added new UI to help manage name changes.
* `FbxExporter`: 
	* Added support for exporting Blendshapes.
	* Added support for exporting SkinnedMeshes with legacy and generic animation.
	* Added support for exporting Lights with animatable properties (Intensity, Spot Angle, Color).
	* Added support for exporting Cameras with animatable properties (Field of View).
	* Added ability to export animation on transforms.
* Added one-button import and export for Autodesk® Maya®, Autodesk® Maya® LT, and Autodesk® 3ds Max®.
* Added Camera export support.
* Added the ability to export FBX files from Unity.
* Added a linked Prefab converter to create a Prefab that auto-updates with the linked FBX file.

FIXES
* `ConvertToPrefab`: 
	* Fixed an issue where the Mesh Collider was not pointing to the exported Mesh after conversion.
	* Now no longer re-exports FBX Model instances.
* `FbxExporter`: 
	* Fixed an issue where Compatible Naming doesn't modify the Scene while exporting.
	* Now links Materials to objects connected to Mesh instances.
	* Now exports Meshes in Model Prefab instances as Mesh instances in the FBX file.
	* Fixed an issue where animating spot angle in Unity was failing to animate the cone angle in Autodesk® Maya® (not the penumbra).
	* Now exports the correct rotation order (xyz) for euler rotation animations (previously would export as zxy).
* `FbxExportSettings`: Fixed the console error on Mac when clicking **Install Unity Integration**.
* Fixed Universal Windows Platform build errors caused by `UnityFbxSdk.dll` being set as compatible with any platform instead of the Editor only.
* Fixed an issue where Object references were lost when using **Convert to Linked Prefab Instance**.
* Fixed an issue with Autodesk® Maya® Integration dropdown not appearing in the FBX Export options.

KNOWN ISSUES
* Cannot export animation only from Autodesk® 3ds Max®.
* `FbxExporter`: 
	* Animated skinned Meshes must be in the bind pose on export (that is, not being previewed in the Animation or Timeline windows, and the original rig's FBX must not contain animation).
	* Animated Meshes in bone hierarchy are not supported.
	* For skinned Meshes, all bones must be descendants of the root bone.
* `3DIntegration`: FBX files containing rigs must have file units in centimeters in order to properly apply animation exported from Unity.
* `ConvertToPrefab`: Converting Model instances that have been modified in the Scene won't re-export the FBX file.
* Requires Unity 2018.1.0.
* When exporting with an animated transform for a Camera or a Light, the resulting rotation does not take the forward direction into account and is off by 90 degrees.
* The FBX Exporter does not export key tangents and the default key tangent setting is different between Unity, the FBX SDK and Autodesk® Maya®. This causes the curve shape to change between Unity and Autodesk® Maya®.
* The FBX Exporter does not maintain animated continuous rotations.
* The FBX Exporter does not convert animated rotations with Euler Angles (Quaternion) or Quaternion interpolation, to the correct Euler equivalent.

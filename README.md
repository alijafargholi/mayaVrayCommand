![alt vray_logo_image](http://www.software3d.de/media/wysiwyg/Vray_3dsmax_3/V-Ray_h-logo_color.jpg =200x)
# Vray Commands in Maya :punch:
 

:mega: Note: Following examples are using *PyMel*. Please make sure you've imported the **pymel.core**

 ```python
    import pymel.core as pm
  ```

 ----

### getRequiredAttrs 
 > **Description:** Gets the required vray attributes of a node.

 > `Usage: vray getRequiredAttrs <NODE NAME - STRING>`
 
  ___

### getOptionalAttrs 
 Gets the optional vray attributes of a node.
 > **Description:** Gets the optional vray attributes of a node.

 > ` Usage: vray getOptionalAttrs <NODE NAME - STRING>`
 
##### Example 
 ```python
    foo = pm.polyCube()
    pm.vray("getOptionalAttrs", foo)
  ```
 ___
 
### getRenderElements
 > **Description:** Prints all render elements.

##### Example
 ```python
    pm.vray("getRenderElements")
  ```
 ___
 
### getRenderElementsInScene
 > **Description:** Returns the render elements in the current scene. Pass 0|1 to include render elements from referenced scenes.
 
 > `Usage: vray getRenderElementsInScene [1|0] ` 
 
##### Example
 ```python
    pm.vray("getRenderElementsInScene", 1)
  ```
 ____

### getGUIHint
 > **Description:** Gets a GUI hint about a vray attribute of a node
 
 > `Usage: vray getGUIHint <NODE NAME - STRING> <ATTRIBUTE NAME - STRING> <HINT NAME - STRING>`
 ___
 
### getAHint
 > **Description:** A more general version of getGUIHint. Instead of node, it accepts classType and determines where to take the classes from.
 
 > `Usage: vray getAHint <CLASS TYPE - STRING> <CLASS NAME - STRING> <HINT NAME - STRING`

##### Example
 ```python
    renderElementName =  pm.vray("getRenderElements")[0]
    pm.vray("getAHint", "RenderElement", renderElementName, "label")
    # Result: [u'Atmospheric Effects'] #
  ```
 ___

### addAttr 
 Dynamically adds a vray attribute to a node.
 ___

### updateGLSLAttr 
 Updates GLSL attributes of a VRayTexGLSL node.
 ___

### updateOSLAttr 
 Updates OSL attributes of a VRayTexOSL node.
 ___

### saveCompiledGLSLShader
 Saves a compiled GLSL shader.
 ___

### saveCompiledOSLShader 
 Saves a compiled OSL shader.
 ___

### createAEMenu 
 Creates the VRay AE menu for a given node.
 ___

### addAttributesFromGroup 
 Adds all the vray attributes from a group to the given node. Remove if executed twice (toggling on/off).
 ___

### listLoadedPlugins
 Lists all loaded plugins. Used for creating a VRayPluginNode.
 ___

### addAttributesFromDll
 Adds all the attributes for a specific vray plugin. The plugin is read from a file and the name of the class is known.
 ___

### restoreMesh
 Restore the mesh from a proxy.
 ___

### clearProxyPreviewCache
 Clears the proxy preview cache for all meshes or a particular one (name as parameter).
 ___

### clearGeomCache
 Clears all cached geometry plugins.
 ___

### clearBitmapCache 
 Clears all cached bitmaps.
 ___

### showVFB
 Shows the vfb window.
 ___

### addVFBToPanel  
 Adds the vfb to a panel.
 ___
 
### removeVFBFromPanel
 Removes the vfb from panels.
 ___

### physicalCameraFOV
 Syncs FOV and other viewport related attributes of one or all vray physical cameras to maya cameras so they match.
 ___

### physicalCameraAutoShift
 Calculates a vertical shift for a physical camera so that the objects in the scene are straightened-up.
 ___

### clearSwatchCache 
 Clears the swatch image cache. Generally this should be called when loading a new scene.
 ___

### setSSSPreset 
 Sets the SSS preset.
 ___

### setHair3Preset 
 Sets a node's hair3 preset to a new one by index.
 ___

### objectProperties 
 Gets properties about an object of a given type.
 ___

### getBlackBodyColor 
 Gets the color of a black body for a given temperature.
 ___

### getConfValue 
 Load the value of a configuration option and return it.
 ___

### setConfValue 
 Set the value of a configuration option.
 ___

### saveConfFile 
 Saves the data from the XML parser to the VRay configuration settings file.
 ___

### closeConfFile 
 Delete the XML parser without saving the data to the settings file.
 ___

### giMaps 
 This is used to save/reset the different GI maps.
 ___

### resolveServers 
 Command to resolve a list of network names to IP addresses.
 ___

### isVRmatEditorEnabled 
 If the VRmat editor is enabled.
 ___

### getVRmatList 
 Gets a VRmat material list.
 ___

### vfbControl 
 Control command for the vfb.
 ___

### loadFromFile 
 Loads materials from vrscene file.
 ___

### getMtlsList 
 Creates a list of plugins for all materials in the specified file.
 ___

### loadFromFileInit 
 Initializes vrscene file material importing.
 ___

### loadFromFileEnd
 Finalizes vrscene file material importing.
 ___

### exportLightmeterToCSV
 Exports lightmeter data to a .csv file.
 ___

### getLightmeterMaxValue
 Returns the maximum value of a lightmeter (for Direct/GI/Total light).
 ___

### version 
 Prints the version.
 ___

### build
 Prints the build number.
 ___
![alt vray_logo_image](http://www.software3d.de/media/wysiwyg/Vray_3dsmax_3/V-Ray_h-logo_color.jpg)
# Vray Commands in Maya :punch:
 

:mega: **Note:** Following examples are using *PyMel*. Please make sure you've imported the **pymel.core**

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
    # Create a Cube
    foo = pm.polyCube()
    # Print out the optional attribute of the Cube 
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
 > **Description:** Dynamically adds a vray attribute to a node.

 > `Usage: vray addAttr <NODE NAME - STRING> <ATTRIBUTE NAME - STRING>`

##### Example
 ```python
    # Create a Cube
    foo = pm.polyCube()
    # Assign the vray object ID to the cube's transform node. 
    pm.vray("addAttr", foo[0].name(), "vrayObjectID")
  ```
 ___

### updateGLSLAttr 
 > **Description:** Updates GLSL attributes of a VRayTexGLSL node.
 
 > `Usage: vray updateGLSLAttr <NODE NAME - STRING>`
 ___

### updateOSLAttr 
 > **Description:** Updates OSL attributes of a VRayTexOSL/VRayMtlOSL node.
 
 > `Usage: vray updateOSLAttr <NODE NAME - STRING>`
 ___

### saveCompiledGLSLShader
 > **Description:** Saves a compiled GLSL shader.
 
 > `Usage: vray saveCompiledGLSLShader <IN FILE NAME - STRING> <OUT FILE NAME - STRING>`
 ___

### saveCompiledOSLShader 
 > **Description:** Saves a compiled OSL shader.

 > `Usage: vray saveCompiledOSLShader <IN FILE NAME - STRING> <OUT FILE NAME - STRING>`
 ___

### createAEMenu 
 > **Description:** Creates the VRay AE menu for a given node.

 > `Usage: vray createAEMenu <NODE NAME - STRING>Creates the VRay AE menu for a given node.`
 ___

### addAttributesFromGroup 
 > **Description:** Adds all the vray attributes from a group to the given node. Remove if executed twice (toggling on/off).

 > `Usage: vray addAttributesFromGroup <NODE NAME - STRING> <GROUP INDEX - STRING> <SHOULD ADD - BOOLEAN>   Where <BOOLEAN> is one of: 0|1`
 
##### Example
 ```python
    # Create a Cube and get its Shape node
    foo = pm.polyCube()[0].getShape()
    # Assign the Vray Round Edges attributes to the shape node
    pm.vray("addAttributesFromGroup", foo, "vray_roundedges", 1)
  ```
 ___

### listLoadedPlugins
 > **Description:** Lists all loaded vray plugins from a given type.

 > `Usage: vray listLoadedPlugins [texture|light|volume|brdf|material]`
 
##### Example
 ```python
    pm.vray("listLoadedPlugins", "light")
    # Result: [u'LightAmbientMax',
     u'LightDirectMax',
     u'LightSpotMax',
     u'LightOmniMax',
     u'SunLight',
     u'LightDirectModo',
     u'LightDirect',
     u'LightAmbient',
     u'LightOmni',
     u'LightSphere',
     u'LightSpot',
     u'MayaLightDirect',
     u'LightRectangle',
     u'LightMesh',
     u'LightIESMax',
     u'LightIES',
     u'LightDome'] #
  ```
 ___

### addAttributesFromDll
 > **Description:** Adds all the attributes for a specific vray plugin. The plugin is read from a file and the name of the class is known.
 
 > `Usage: vray addAttributesFromDll <NODE NAME - STRING> [texture|brdf|material|light|volume] <PLUGIN NAME - STRING>`
 ___

### restoreMesh
 > **Description:** Restore the mesh from a proxy.

 > `Usage: vray restoreMesh <NODE NAME - STRING`
 ___

### clearProxyPreviewCache
 > **Description:** Clears the proxy preview cache for all meshes or a particular one (name as parameter).
 ___

### clearGeomCache
 > **Description:** Clears all cached geometry plugins.
 ___

### clearBitmapCache 
 > **Description:** Clears all cached bitmaps.
 ___

### showVFB
 > **Description:** Shows the vfb window.
 ___

### addVFBToPanel  
 > **Description:** Adds the vfb to a panel.
 ___
 
### removeVFBFromPanel
 > **Description:** Removes the vfb from panels.
 ___

### physicalCameraFOV
 > **Description:** Syncs FOV and other viewport related attributes of one or all vray physical cameras to maya cameras so they match.
 ___

### physicalCameraAutoShift
 > **Description:** Calculates a vertical shift for a physical camera so that the objects in the scene are straightened-up.
 ___

### clearSwatchCache 
 > **Description:** Clears the swatch image cache. Generally this should be called when loading a new scene.
 ___

### setSSSPreset 
 > **Description:** Sets the SSS preset.
 ___

### setHair3Preset 
 > **Description:** Sets a node's hair3 preset to a new one by index.
 ___

### objectProperties 
 > **Description:** Gets properties about an object of a given type.
 ___

### getBlackBodyColor 
 > **Description:** Gets the color of a black body for a given temperature.
 ___

### getConfValue 
 > **Description:** Load the value of a configuration option and return it.
 ___

### setConfValue 
 > **Description:** Set the value of a configuration option.
 ___

### saveConfFile 
 > **Description:** Saves the data from the XML parser to the VRay configuration settings file.
 ___

### closeConfFile 
 > **Description:** Delete the XML parser without saving the data to the settings file.
 ___

### giMaps 
 This is used to save/reset the different GI maps.
 > **Description:** This is used to save/reset the different GI maps.

 > Usage: 

* vray giMaps [save|info|load|mapinmemory] [irradiance|lightcache|globalphoton|causticsphoton]
* vray giMaps reset [irradiance|lightcache|photon]
 ___

### resolveServers 
 Command to resolve a list of network names to IP addresses.
 > **Description:** Command to resolve a list of network names to IP addresses.

 > `Usage: vray resolveServers <SERVER NAME 1 - STRING> <SERVER NAME 2 - STRING> ... <SERVER NAME N - STRING>   Where N >= 1`
 
 ___

### isVRmatEditorEnabled 
 > **Description:** If the VRmat editor is enabled.
 ___

### getVRmatList 
 > **Description:** Gets a VRmat material list.

 > `Usage: vray getVRmatList <MATERIAL NAME - STRING`
 ___

### vfbControl 
 > **Description:** Control command for the vfb.
 ___

### loadFromFile 
 > **Description:** Loads materials from vrscene file.
 ___

### getMtlsList 
 > **Description:** Creates a list of plugins for all materials in the specified file.
 ___

### loadFromFileInit 
 > **Description:** Initializes importing from vrscene file.
 > `Usage: vray loadFromFileInit <FILE NAME - STRING>`
 ___

### loadFromFileEnd
 > **Description:** Finalizes vrscene file material importing.
 ___

### exportLightmeterToCSV
 > **Description:** Exports lightmeter data to a .csv file.

 > `Usage: vray exportLightmeterToCSV <NODE NAME - STRING> <FILE NAME - STRING>`

 ```python
    pm.vray("exportLightmeterToCSV",  "VRayLightMeter1", r"PATH\foo.csv")
 ```
 ___

### getLightmeterMaxValue
 > Description: Returns the maximum value of a lightmeter (for Direct/GI/Total light).

 > `Usage: vray getLightmeterMaxValue <NODE NAME - STRING> [direct|gi|total]`

##### Example
  ```python
    pm.vray("getLightmeterMaxValue", "VRayLightMeter1", "total")
  ``` 
 ___

### version 
 > **Description:** Prints the version.

##### Example
  ```python
    pm.vray("version")
    # Result: u'3.40.01' #
  ```
 ___

### build
 > **Description:** Prints the build number.
 ___
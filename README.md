# Smart-Condo-Annotations-Project

**The Smart Condo**
===================

The Smart Condo is a research facility located in the Edmonton Clinic Health Academy. It is used to simulate home visits, allowing healthcare professionals to increase their understanding of assisted living devices. The condo features intelligent technologies, such as sensors and smart appliances, providing opportunities for researchers and practitioners to learn how to communicate and collaborate with patients living in 'intelligent' homes. (http://www.hserc.ualberta.ca/Resources/Spaces/SmartCondo.aspx)


**Project Purpose**
===================

This project's goal was to develop a code that provides users a method to add and retrieve different annotations in order to enhance the exploration of the Smart Condo's virtual 3D model. The keyboard's arrow keys are utilized to move the first-person controller while the mouse's cursor rotates the camera's direction of view. 


**Opening & Running Project File**
==================================

The Smart Condo Annotations is a Unity Project file. Upon opening the file in Unity, open the scene named "Condo". The way that the components of the annotation window are positioned, the Game window must be full-screen horizontally. After pressing play, position your mouse cursor to the slight left of the centre of the Game window in order to rotate the camera's view effectively. Hovering the cursor over an object in the model will bring up its annotations. Moving the mouse to point at different objects switches the annotations to the object that is currently being looked at. Use the arrow keys to position the first-person controller and the mouse together to explore the condo in this way.


**Scripts**
===========

**_camMouseLook.cs_**

This script is attached to the main camera of the scene which is also parented under the first-person controller.  It enables the camera to rotate up, down, right and left. By using linear interpolation, the script makes the camera movements smooth. 

**_CharacterController.cs_**

This script is attached to the capsule named "FPC" in the hierarchy and enables the controller to move forward, back, left and right. 

**_ReadAnnotationName.cs & ReadAnnotationInfo.cs_**

These scripts are attached to the UI text elements of the annotation window. The code creates a list that Unity can access. After looping through each set of nodes by tag names within the XML, this data is stored inside the list, "ListofAnnotations". The code then calls for the function "getAnnotations" within the "AnnotationsInfoObject" script in order to retrieve this data (text) as needed by the Update function. 

The Update function declares string variables in order to instantiate the text for the annotations on the window. By using a 3D object's name (displayed in the hierarchy), the corresponding list element number and the tag name of the node, the name or information about the object can be displayed on the annotation window. 

The raycast originates from the camera and its direction is dependent on the position of the mouse cursor. Upon hitting a collider (that is attached to a certain gameObject), the ray will return the gameObject's name as it is displayed in the hierarchy. Utlizing this name within the code, the correct name/information of that object can be found within the xml and then displayed. The code lines "annotation.text" instruct the code to instantiate this text while annotation1, annotation2, etc. pertain to the specific segment of the XML that has the corresponding name/information of the object the raycast has hit during runtime.

The reason for having two scripts for both names and information of the gameObjects is for the purpose of being able to format the two different parts of the annotation differently. Thus, the name text is larger and bold while the information text is smaller and not bolded. Otherwise, formatting is unavailable. 

**_AnnotationsInfoObject.cs_**

This script grabs the string text within the XML file when its function, getAnnotations, is called by ReadAnnotationName.cs and ReadAnnotationInfo.cs.

**How to Add New Annotations**
==============================

**_Adding new furniture/devices/objects into model_**

The Smart Condo model was completed before the annotation project. Please contact for more help and guidance.

**_Adding new box colliders_**
In order for the annotations to be displayed, the GameObject must have a collider on it that the raycast can hit

**Deleting Annotations**
========================

**Editing Annotation Information**
==================================

**Current List of Objects with Annotations**
============================================

Below are the names of the objects within the model that currently have annotations. These names appear as is within Unity's hiearachy as well as the scripts, ReadAnnotationName.cs and ReadAnnotationInfo.cs. However, any bullets with brackets beside them do not have the same name as the annotation window displays. Due to unsuccessful attempts to place a collider over the entire object, colliders have only been placed on certain components, thus the names of these components (that are displayed in the hierarchy) are used in the script to retrieve the entire object's annotations from the XML. Despite this, the general name of the object is displayed by the annotation window as it is stored within the XML file.

**_Bedroom_**
* BED
* BEDROOM TV (TV)
* BACK DOOR

**_Kitchen_**
* KITCHEN ISLAND
* AUTOPANTRY
* KITCHEN SINK
* TOASTER
* DISHWASHER (Component#2_001 && Component#1_001)
* KITCHEN OUTLET
* STOVE
* RANGE HOOD
* MICROWAVE (Group_001)
* OVEN 
* FRIDGE

**_Bathroom_**
* BATHTUB
* TOILET
* BATHROOM SINK
* SOAP DISPENSER
* BATHROOM OUTLET

**_Dining Room_**
* DINING TABLE

**_Foyer_**
* FRONT DOOR

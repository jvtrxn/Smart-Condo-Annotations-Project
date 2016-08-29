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

**camMouseLook.cs**

This script is attached to the main camera of the scene which is also parented under the first-person controller.  It enables the camera to rotate up, down, right and left. By using linear interpolation, the script makes the camera movements smooth. 

**CharacterController.cs**

This script is attached to the capsule named "FPC" in the hierarchy and enables the controller to move forward, back, left and right. 

**ReadAnnotationName.cs**

This script is attached to the first UI text element placed onto the plane of the annotation window. The code creates a list that Unity can access after calling the set/get function from the AnnotationsInfoObject script that stores data from the AnnotationsInfo.xml file. 

**How to Add New Annotations**
==============================

**Adding new furniture/devices/objects into model**

**Adding new box colliders**

**Deleting Annotations**
========================

**Editing Annotation Information**
==================================

**Current List of Objects with Annotations**
============================================

**Contacts**
============

Julia Tran - jt7@ualberta.ca

Aishwarya Venkitachalam - avenkita@ualberta.ca

Victor Fernandez - vf@ualberta.ca

Eleni Stroulia - stroulia@ualberta.ca


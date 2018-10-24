# cvprintmonitor
Uses Computer Vision to validate that your 3d print is going smoothly.

Goal
====
Use a web camera and 3D model renderer to compare physical state to
intended state. Specifically, to determine if a 3D print has failed.

Process
===
1. Render 3D object to buffer - Should be post-slicing stage so we have knowledge of the orienation of the object in the build workspace.
2. Calibrate camera by capturing image of build workspace with markers to determine camera's POV.
3. Compose projected view of object based on orientation and camera POV infomation
4. Iteratively track image of current build and compare to expected image.
5. If image does not match, escalate.

Considerations
===
- Do we need to know the progress of the print to make an accurate comparison? This would require feedback from the printer.
- Do we need to do the in-memory render as a ray-trace to make sure we only capture the POV of the camera?
- How do we ignore 'in progress' surfaces?

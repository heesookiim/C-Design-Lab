# C-Design-Lab
## Summary
### 2/8/2023 
- Developed functionality for creating recursive folders, such as TASK_1 -> SUBJECT_1 -> OBJECT_1.
- Implemented error handling code to address existing folders using FileExistsError.
### 2/9/2023 
- Configured camera position settings to move closer to the object.
### 2/13/2023 
- Debugged calibration.py for Mac and Linux operating systems.
- Confirmation of calibration is currently pending.
### 2/14/2023 
- Finalized the environment to ensure accurate calibration
- Executed the calibration process
- Collaborated on generating ideas for complex tasks
- Created 3D models by filming various objects
### 2/16/2023 
- Help debugging get_parameter.py
- studied detectron
### 2/24/2023 
- Capture images of an object and created a 3D model of it out
- Reconstructed the texture of the object using Mashlab
- green and red electric drills, and a hammer have been constructed so far
![image](https://user-images.githubusercontent.com/32153697/221323443-deaa1d35-e5ad-498f-ad8f-0dcf1bfff5d7.png)
![image](https://user-images.githubusercontent.com/32153697/221323671-bb81fe07-9664-4c70-bfd9-83d54307d36d.png)
![image](https://user-images.githubusercontent.com/32153697/221324178-e98dcd31-78cf-4b0a-99d9-048dc1011e48.png)
![texture_hammer](https://user-images.githubusercontent.com/32153697/221324385-38a43fa4-5ee8-46bf-9a50-c28a863ee95f.png)
### 3/8/2023 
- Collabroated with Dizhi Ma's work 
- Understood code from ArUCo for Pose estimation
- https://github.com/GSNCodes/ArUCo-Markers-Pose-Estimation-Generation-Python
![image](https://user-images.githubusercontent.com/107389219/223874390-a39afb5a-766f-4a43-826a-2414be4d61bd.png)
### 3/9/2023
- Obtained object pose with respect to camera using PnP 
- Constructed 3D axes of object based on the pose

![image](https://user-images.githubusercontent.com/107389219/224432695-2fbe2518-7611-46ab-b706-9a7f4e02a875.png)
![image](https://user-images.githubusercontent.com/107389219/224432710-b4a4f9a2-2f45-4a81-a07c-0348e8e58e6d.png)
![image](https://user-images.githubusercontent.com/107389219/224432935-6569458a-789e-4630-bb85-6f90cee04caa.png)
### 3/27/2023
- Started to annotate keypoints on the pingpong paddle using 'labelme'(ex. top, middle_right, bottom_right ..)
- Went over 'mmpose' documentation (https://mmpose.readthedocs.io/en/latest/)
- update: should try to use detectron2 (https://www.youtube.com/watch?v=xX9fPmclEHY&t=553s) 
### 3/29/2023
- https://www.youtube.com/watch?v=thHifm9cv8M
### 3/30/2023
- ![image](https://user-images.githubusercontent.com/107389219/228973954-eb699bff-5ae3-46bc-b3b2-453343a64f5e.png)
### 3/31/2023
Goal: 
Given data for jason file, come up with a code that converts json file into coco format. 

Q. Does detectron have specific coco format?

coco format == coco_format.json. , 
Use the structre of json file to come up with coco format:

To test the code:
Run the file trhough Detectron2 and check if the annotation looks good 
### 4/4/2023
- built code that annotated paddle from an image (annotation.py)
- built code that converts the annotation data into COCO dataformat (updated annotation.py) 
![image](https://user-images.githubusercontent.com/107389219/230163572-2168e6af-5d1e-4e3d-923e-44fbdf1d1426.png)

### 4/5/2023
- 

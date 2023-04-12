# C-Design-Lab
## To-do list
- [ ] Try to get bbox first then the key points
- [ ] Triangulate to get the depth
- [ ] Penalize the model for the points being to far from each other
## Summary
## ICCV2023 Preparation
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
## Project Paddle with Dizhi
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

### 4/3/2023
- Created annotation.py, which gives image information, keypoints, and rectangle box.
<img width="588" alt="Screenshot 2023-04-04 at 3 13 27 PM" src="https://user-images.githubusercontent.com/67416712/229896484-c5959053-e006-4548-9e3e-81553c785abc.png">
<img width="702" alt="Screenshot 2023-04-04 at 3 13 52 PM" src="https://user-images.githubusercontent.com/67416712/229896581-1feab710-19b1-4c23-b076-cfa6a090efd2.png">

### 4/7/2023
![image](https://user-images.githubusercontent.com/107389219/230676115-8e771ac1-19ef-4097-b9b1-fff162b0d72e.png)
![image](https://user-images.githubusercontent.com/107389219/230676138-85a21f60-e86e-40df-bda4-66a5d7ef4c98.png)
![image](https://user-images.githubusercontent.com/107389219/230676146-cc905528-59c6-4101-b481-5f6db326290c.png)
![image](https://user-images.githubusercontent.com/107389219/230676164-c0cb136a-9e13-466e-8a88-9fad9aa8c064.png)
![image](https://user-images.githubusercontent.com/107389219/230676177-c4749bc0-495f-4199-8dfa-798bf98159e8.png)
- performed object detection and key point detection using the COCO dataset
- COCO dataset was provided by annotation.py code that was created in 4/3

### 4/11/2023
- trained total 61 annotated images to rcnn model through Detectron2
- Tested the model using random images from train dataset
![image](https://user-images.githubusercontent.com/107389219/231313474-c8e79042-708d-4597-8b24-e9c55561168f.png)
![image](https://user-images.githubusercontent.com/107389219/231313495-f9fda910-3516-4606-b684-e7fbdb73a4a6.png)
![image](https://user-images.githubusercontent.com/107389219/231313508-8bbb25ac-e627-4e27-b89e-1de8b4986b4a.png)
![image](https://user-images.githubusercontent.com/107389219/231313516-3c866e6b-e9d5-49e6-96ca-583bd28bfd4a.png)
- Tested the model using one image outside of train dataset
![image](https://user-images.githubusercontent.com/107389219/231313460-a6fe79e2-3973-42bd-bb42-c1268e1423d1.png)
- Overall: based on the images after training, the model seems to be overtrained. 
- Next Goal:
- [ ] Try to get bbox first then the key points
- [ ] Triangulate to get the depth
- [ ] Penalize the model for the points being to far from each other

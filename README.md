# C-Design-Lab

## To-do List
- [ ] Try to get bbox first then the key points
- [ ] Triangulate to get the depth
- [ ] Penalize the model for the points being too far from each other
- [ ] implement a code for evaluation
- [ ] retrain the model with total 200 epochs  

## ICCV2023 Preparation
### 1/24/2023
- Brainstormed for tasks
https://docs.google.com/document/d/1PJAIQMMVx-8K0MvQrfuXwWGvp-2LW5I3v94bGQELx88/edit

### 2/8/2023 
- Developed functionality for creating recursive folders, such as `TASK_1 -> SUBJECT_1 -> OBJECT_1`.
- Implemented error handling code to address existing folders using `FileExistsError`.

### 2/9/2023 
- Configured camera position settings to move closer to the object.

### 2/13/2023 
- Debugged 'calibration.py' for Mac and Linux operating systems.
- Confirmation of calibration is currently pending.

### 2/14/2023 
- Finalized the environment to ensure accurate calibration
- Executed the calibration process
- Collaborated on generating ideas for complex tasks
- Created 3D models by filming various objects

### 2/16/2023 
- Help debugging 'get_parameter.py'
- studied 'Detectron'

### 2/24/2023 
- Capture images of an object and created a 3D model of it out
- Reconstructed the texture of the object using 'Mashlab'
- green and red electric drills, and a hammer have been constructed so far
![image](https://user-images.githubusercontent.com/32153697/221323443-deaa1d35-e5ad-498f-ad8f-0dcf1bfff5d7.png)
![image](https://user-images.githubusercontent.com/32153697/221323671-bb81fe07-9664-4c70-bfd9-83d54307d36d.png)
![image](https://user-images.githubusercontent.com/32153697/221324178-e98dcd31-78cf-4b0a-99d9-048dc1011e48.png)
![texture_hammer](https://user-images.githubusercontent.com/32153697/221324385-38a43fa4-5ee8-46bf-9a50-c28a863ee95f.png)


## Project Paddle with Dizhi
### 3/8/2023
- Collaborated with Dizhi Ma to better understand the Pose estimation code from ArUCo.
- Reviewed the ArUCo-Markers-Pose-Estimation-Generation-Python repository, available at https://github.com/GSNCodes/ArUCo-Markers-Pose-Estimation-Generation-Python. 
![ArUCo Markers Pose Estimation Output](https://user-images.githubusercontent.com/107389219/223874390-a39afb5a-766f-4a43-826a-2414be4d61bd.png)



### 3/9/2023
- Obtained object pose with respect to camera using PnP 
- Constructed 3D axes of object based on the pose

![image](https://user-images.githubusercontent.com/107389219/224432695-2fbe2518-7611-46ab-b706-9a7f4e02a875.png)
![image](https://user-images.githubusercontent.com/107389219/224432710-b4a4f9a2-2f45-4a81-a07c-0348e8e58e6d.png)
![image](https://user-images.githubusercontent.com/107389219/224432935-6569458a-789e-4630-bb85-6f90cee04caa.png)

### 3/27/2023
- Started to annotate keypoints on the pingpong paddle using 'labelme'(ex. top, middle_right, bottom_right ..)
- Reviewed the 'mmpose' documentation for further insights into the topic. (https://mmpose.readthedocs.io/en/latest/)
Update: Decided to explore using the Detectron2 framework for key point detection, following a tutorial available at https://www.youtube.com/watch?v=xX9fPmclEHY&t=553s.

### 3/29/2023
- https://www.youtube.com/watch?v=thHifm9cv8M

### 3/30/2023
- ![image](https://user-images.githubusercontent.com/107389219/228973954-eb699bff-5ae3-46bc-b3b2-453343a64f5e.png)

### 3/31/2023
Objective:
- Develop a code that can transform a given json file into the coco format.

Q: Is there a specific coco format that 'Detectron' uses?

A: Yes, the format is referred to as coco_format.json. However, we can utilize the structure of the provided json file to develop a corresponding coco format.

- To validate the code's accuracy, we can run the generated file through Detectron2 and examine the annotation's quality.

### 4/3/2023
- Created 'annotation.py', which gives image information, keypoints, and rectangle box.
<img width="702" alt="Screenshot 2023-04-04 at 3 13 52 PM" src="https://user-images.githubusercontent.com/67416712/229896581-1feab710-19b1-4c23-b076-cfa6a090efd2.png">

### 4/7/2023
- Utilized the COCO dataset to execute object detection and key point detection.
- Acquired the COCO dataset from the annotation.py code developed on April 3rd.

### 4/11/2023
- Trained the rcnn model with a total of 61 annotated images, utilizing 'Detectron2'.
- Tested the model's efficacy with a selection of random images from the training dataset.
- Tested the model using one image outside of train dataset
![image](https://user-images.githubusercontent.com/107389219/231313460-a6fe79e2-3973-42bd-bb42-c1268e1423d1.png)
- In general, the model yields satisfactory bbox output, but its key points detection is unsatisfactory after training.
- The next objective is to:
- [ ] First attempt to obtain the bbox, followed by the key points.
- [ ] Employ triangulation to obtain the depth.
- [ ] Enforce a penalty if the points are too distant from one another.

### 4/12/2023
Rough draft:
1. Model training -> do it through Google Colab
2. Import the trained model from Google Drive to local device
3. Implement 'get_keypoints.py' 
- performs evaluation of the detected keypoints
- send the keypoint data to 'get_pnp.py'
- condition:
	-> if there are 5 keypoints in bbox range, then it's valid
	-> set bbox threshold to 96% // in Detectron2 Tutorial, there was an image that detects a baby's head as a balloon with 95% accuracy in bbox

Ideas for improvements:
- More data

Overall plan:
- Friday 4/14: get more data
- Monday 4/17: start to implement 'get_keypoints.py'

### 4/13/2023
- Re-trained the rcnn model with an additional 2000 iterations, totaling 5000 iterations.
![eval1 (1)](https://user-images.githubusercontent.com/107389219/231896973-1155f23a-505e-4901-b4f8-f812588be1e0.jpg)
- In general, the model yields better bbox output, but its key points detection is still unsatisfactory. There still is one less key point on the paddle. 
- Captured 12 videos to increase the number of images available for annotation and training.
- Extracted each frame from the videos and selected the unblurred images.
- Organized the selected images into the 'frame_pre_annotated' folder.  
![image](https://user-images.githubusercontent.com/107389219/231892593-ce0d5069-a658-4fc7-ab00-a2602eec9099.png)

### 4/17/2023
- Annotated 250 images more by using `annotation.py` created in April 3rd
- Re-trained the pre-trained rcnn model with updated images. Total 40 epochs
- Created testdataset from unused images based on three categories: Clear, Blurry, Missing Keypoints
![eval2](https://user-images.githubusercontent.com/107389219/232642555-65c14425-a29f-4914-b4e1-0a804f988db7.jpg)
![eval1](https://user-images.githubusercontent.com/107389219/232642559-a615b193-8547-4cd8-aa7c-9db4e04e2c59.jpg)
- In most cases, bounding box detection is accurate but keypoint detection has not been as accurate as that of bbox
- Next Goal: 
- [ ] implement a code for evaluation
- [ ] retrain the model with total 200 epochs  

### 4/18/2023 
#### Done:
- [x] implement a code for evaluation
- [x] retrain the model with total 200 epochs  
![image](https://user-images.githubusercontent.com/107389219/232918778-45610d56-c442-4df4-8cfe-ac5c867c3823.png)

#### Next Goal:
- [ ] Create evaluation dataset and run COCOevaluator to get some metrics
- [ ] Make sure the performance is reasonable. -> this is for key point detection
- [ ] Look at different paper to check the performance on popular dataset to improve your model to be better than theirs

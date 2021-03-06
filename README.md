# Task: Image-stitching-for-vehicle

## Task Description:
We use deep learning to identify which type of vehicle is entering a parking lot or crossing a toll and charge based on that. Often the camera is too close to vehicle to get a full picture of the vehicle in single shot, especially for large trucks. From a video of vehicle passing, use image stitching techniques to extract and stitch portions from video to construct full image of vehicle.

## Procedure :
1. Splited the video into images frame by frame. (In this step I got 3600 images)

2. Took the images in which the truck was moving. (Images from 950 to 1200)

3. Took two images in which the truck was moving. (I took 1040th and 1070th picture)
<img src="Images/1040.jpg" alt="1040th" width="400"/>  <img src="Images/1070.jpg" alt="1070th" width="400"/>

4. Applied Feature Matching Technique by OpenCV on these two images. (In this step I found that most of the matched features were of the stationary background as can be seen in image with name "original_image_drawMatches")
 <img src="original_image_1_keypoints.jpg" alt="original_image_1_keypoints" width="400"/>  <img src="original_image_2_keypoints.jpg" alt="original_image_2_keypoints" width="400"/>
<img src="original_image_drawMatches.jpg" alt="original_image_drawMatches" width="800"/> 

5. Applied OpenCv's optical flow algorithm to mask the moving truck only. (In this step I was not able to perfectly mask the movement of the truck as can be seen in the images in the "Masked_image_of_moving_vehicle" folder)
<img src="Masked_image_of_moving_vehicle/30.jpg" alt="Masked_image_of_moving_vehicle" width="800"/> 

6. Manually masked 21 images from 1000 to 1200 with an interval of 10.
<img src="Img/1070.jpg" alt="Manually_Masked_image_of_moving_vehicle" width="800"/> 

7. Applied the feature matching Technique (used in step 4) on these two images. (In this step I was succesfully able to match the features of the moving truck as can be seen in image with name "masked_image_drawMatches")
<img src="masked_image_1_keypoints.jpg" alt="masked_image_1_keypoints" width="400"/>  <img src="masked_image_2_keypoints.jpg" alt="masked_image_2_keypoints" width="400"/>
<img src="masked_image_drawMatches.jpg" alt="masked_image_drawMatches" width="800"/> 

8. Applied Opencv's stiching algorithm on all possible continous combinations of these 21 images. (These images can be found in the "Output" folder)
<img src="Output/7_12.jpg" alt="Output" width="800"/> 

9. Cropped and resize the images.
<img src="Clean_output_images/6_12.jpg" alt="Clean_output_images" width="800"/> 

10. After this step some of the images showed Good results. (These images can be found in the "Clean_output_images" folder)


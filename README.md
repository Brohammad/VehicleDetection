# VehicleDetection
Here we use YOLOv3 (You Only Look Once) and OpenCV to detect vehicles in a parking lot and determine the availability of parking spaces. It processes a video feed, identifies vehicles using YOLOv3, and checks the occupancy of predefined parking slots.

Features
Vehicle Detection:

Uses YOLOv3 to detect vehicles in the video feed.

Draws bounding boxes around detected vehicles.

Parking Space Occupancy Detection:

Predefined parking slots are loaded from a file.

Uses image processing techniques (thresholding, blurring, etc.) to determine if a parking space is occupied or free.

Real-Time Visualization:

Displays the video feed with parking slot overlays.

Highlights free parking spaces in green and occupied spaces in red.

Frame Skipping:

Processes every nth frame to improve performance.

Requirements
To run this project, you need the following:

Python Libraries:

opencv-python-headless

cvzone

numpy

pickle

os

time

Files:

YOLOv3 configuration file (yolov3.cfg)

YOLOv3 weights file (yolov3.weights)

COCO class labels file (coco.names)

Parking slot positions file (CarParkPos)

Video file of the parking lot (carPark.mp4)

Google Colab:

The project is designed to run in Google Colab, but it can be adapted for local environments.

Setup Instructions
Install Required Libraries:
Run the following command in Google Colab to install the required libraries:

bash
Copy
!pip install opencv-python-headless cvzone
Upload Files:

Upload the following files to your Google Colab environment:

yolov3.cfg

yolov3.weights

coco.names

CarParkPos

carPark.mp4

Update File Paths:

Update the file paths in the code to match the locations of the uploaded files:

python
Copy
cfg_path = '/content/yolov3.cfg'
weights_path = '/content/yolov3.weights'
with open("/content/coco.names", "r") as f:
with open('/content/CarParkPos', 'rb') as f:
cap = cv2.VideoCapture('/content/carPark.mp4')
Run the Code:

Execute the code in Google Colab to start processing the video feed.

How It Works
YOLOv3 Model:

The YOLOv3 model is loaded using the configuration and weights files.

The model detects vehicles in the video feed and draws bounding boxes around them.

Parking Slot Detection:

Parking slot positions are loaded from the CarParkPos file.

Image processing techniques (thresholding, blurring, etc.) are applied to determine if a parking space is occupied or free.

Visualization:

The video feed is displayed with parking slot overlays.

Free parking spaces are highlighted in green, and occupied spaces are highlighted in red.

Frame Skipping:

To improve performance, the code processes every nth frame (default: every 5th frame).

Code Structure
YOLOv3 Model Loading:

The YOLOv3 model is loaded using cv2.dnn.readNetFromDarknet.

Vehicle Detection:

The detect_vehicles function processes each frame to detect vehicles using YOLOv3.

Parking Space Occupancy Detection:

The checkParkingSpace function checks the occupancy of each parking slot using image processing.

Video Processing:

The video feed is processed frame by frame, and the results are displayed.

Example Output
Free Parking Spaces:

Highlighted in green with the count of free spaces displayed on the screen.

Occupied Parking Spaces:

Highlighted in red.

Detected Vehicles:

Bounding boxes are drawn around detected vehicles, and the class label (e.g., "car") is displayed.

Customization
Parking Slot Positions:

Update the CarParkPos file to define the positions of parking slots in your video.

Threshold Values:

Adjust the threshold values in the checkParkingSpace function to fine-tune the occupancy detection.

Frame Skipping:

Modify the frame_skip variable to control how many frames are skipped between processing.

Limitations
Performance:

The YOLOv3 model is computationally expensive. Frame skipping is used to improve performance, but this may reduce accuracy.

Parking Slot Definition:

The parking slot positions must be manually defined in the CarParkPos file.

Lighting Conditions:

The occupancy detection may be affected by changes in lighting conditions.

Future Improvements
Real-Time Processing:

Optimize the code for real-time processing on high-performance hardware.

Dynamic Parking Slot Detection:

Use machine learning to automatically detect parking slot positions.

Improved Occupancy Detection:

Use deep learning models to improve the accuracy of occupancy detection.

License
This project is licensed under the MIT License. See the LICENSE file for details.

Contact
For questions or feedback, please contact:

Aabid Mohamed A

Email: aabidmohamed2003@gmail.com

LinkedIn: Aabid Mohamed A

GitHub: Brohammad


 Gradiant Project

 Overview

This project focuses on automatic scoring for multiple-choice questions (MCQs) using computer vision and OpenCV. The system processes answer sheets with a grid of options and detects the selected answers based on image recognition. This is ideal for automating the evaluation of tests where users mark answers on printed sheets.

 Features

- Image Stacking Utility: Combines multiple images into one view for comparison or visualization.
- Contour Detection: Identifies the answer boxes and isolates each one for processing.
- Answer Detection: Splits the grid into individual boxes and determines which answer is selected for each question.
- Answer Grading: Compares detected answers with the correct answers and displays correct/incorrect feedback visually.
- Grid Drawing: Draws the answer grid onto the image for verification purposes.

 Requirements

The project is built using Python and OpenCV, and it requires the following libraries:

- numpy
- opencv-python

You can install the required libraries using:

pip install numpy opencv-python
 How It Works

1. Image Preprocessing: The scanned answer sheet image is preprocessed to enhance contours and detect the grid layout.
2. Contour Detection: The contours (outlines) of the answer sheet are found using cv2.findContours(). The largest rectangular contour is identified as the area where the answers are marked.
3. Grid Splitting: The answer grid is split into individual boxes using np.vsplit() and np.hsplit().
4. Answer Recognition: The program checks each box to determine if it is marked. This is done by analyzing the pixel intensity inside each box.
5. Answer Comparison and Grading: The detected answers are compared to the correct answers, and feedback is shown on the image. Correct answers are marked in green, and incorrect answers in red.
6. Result Visualization: The results are displayed on the processed image, including the correct answers for each question.

 Code Overview

 Main Functions

1. stackImages(imgArray, scale, labels=[]):
   - This function stacks multiple images into a single window. It resizes the images to the same scale and creates a grid view.
   
2. reorder(myPoints):
   - Reorders the detected corner points to standardize the perspective transformation.
   
3. rectContour(contours):
   - Filters out the rectangular contours based on their area and shape.
   
4. getCornerPoints(cont):
   - Identifies the corner points of a rectangular contour, used for perspective transformation.
   
5. splitBoxes(img):
   - Splits the input image into a grid of answer boxes. Each box represents one possible answer.
   
6. drawGrid(img, questions=5, choices=5):
   - Draws a grid over the input image, dividing it into rows and columns for question choices.
   
7. showAnswers(img, myIndex, grading, ans, questions=5, choices=5):
   - Displays the selected answers on the image. Correct answers are marked with green circles, and incorrect ones with red circles.

 Usage

To run the project:

1. Clone the repository:
    bash
    git clone https://github.com/CHARINDU15/Gradiant.git
    

2. Navigate to the project directory:
    bash
    cd Gradiant
    

3. Run the main Python script:
    bash
    python main.py
   

4. Ensure that the images used for grading are in the correct format (scanned answer sheets with clear markings).

 Example

The following is an example of how the system detects and grades answers:

1. Input: A scanned MCQ answer sheet image.
2. Output: The processed image with correct answers marked in green and incorrect answers in red.

 Future Improvements

- Advanced Grid Detection: Enhance the flexibility of the system to handle different grid formats.
- Answer Sheet Layout Customization: Support for various question formats and answer layouts.
- Improved Accuracy: Utilize machine learning to improve detection accuracy for poorly marked answers.


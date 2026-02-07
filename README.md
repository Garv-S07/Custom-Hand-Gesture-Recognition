# Custom-Hand-Gesture-Recognition

This project is a real-time AI application that combines Face Identification with Custom Hand Gesture Recognition. It recognizes who is in front of the camera and automatically loads their personalized gesture recognition model. Users can define and train their own custom hand gestures on the fly.

### Features
1. Multi-User Support: Automatically identifies users using Face Embeddings.

2. Dynamic Profile Switching: Instantly swaps gesture models when a different user is detected.

3. Custom Gesture Training: Users can record and train new gestures in real-time (Support Vector Machine).

4. Data Augmentation: Automatically generates variations (rotation/scaling) of recorded gestures to improve accuracy.

5. Coordinate Normalization: Gestures are recognized regardless of hand position or distance from the camera.

6. Persistence: Saves face data and gesture models so they persist after restarting the app.

### Workflow (Step-by-Step)
1. Enroll a New User
* Press e.
* Type your name in the console and press Enter.
* Look at the camera and move your head slowly (left, right, up, down) to capture different angles.
* Press s to save your face profile.

2. Train Your First Gestures
* The model needs at least two classes to work (e.g., "Hand doing nothing" vs. "Hand doing something").
* Record "Neutral" (The Baseline):
* Press r.
* Type Neutral in the console.
* Hold your hand up naturally without making a specific sign.
* Press s. (Note: Training will skip here because only 1 class exists).
* Record Your Custom Gesture:
* Press r.
* Type a name (e.g., Peace).
* Hold the "Peace" sign and rotate your hand slightly to capture variations.
* Press s.
* Success! The model will now train and save as {User}_model.pkl.

### File Structure
1. main.py: The core application code.

2. user_db.json: Database of saved face embeddings.

3. {User}_data.csv: Raw landmark data for a specific user's gestures.

4. {User}_model.pkl: The trained SVM model for that user.

### Prerequisites

You need to have Python installed. The code requires the following libraries:

* pandas
* numpy
* opencv
* scikit-learn
* mediapipe
* scipy

```bash
pip install opencv-python mediapipe numpy pandas scikit-learn scipy
```

### Required Models

To run this project, you must also download the following MediaPipe models and place them in the same directory as your script:

Hand Landmarker: hand_landmarker.task

Face Detector: blaze_face_short_range.tflite

Image Embedder: mobilenet_v3_small.tflite(rename as "face_embedder.tflite")

Rename them exactly as listed above if the downloaded files have different names.

### How to use this:
1. Just clone the repo and try it out after installing the prerequisites and models.


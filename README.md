# SnakeGame
🐍 Gesture Controlled Snake Game

Python • OpenCV • MediaPipe • Pygame

A modern take on the classic Nokia Snake game, where the snake is controlled using hand gestures captured through a webcam. Instead of using arrow keys, the game detects your hand movements in real time and converts them into directions for the snake.

This project was built while exploring the MediaPipe Python module and experimenting with computer vision–based interaction.

Project Overview

The goal of this project was to combine a simple arcade game with real-time gesture recognition.

Using MediaPipe hand tracking and OpenCV video processing, the system detects hand landmarks from a webcam feed and translates gestures into movement commands for the snake.

The result is a nostalgic game experience with a modern, touchless control system.

Key Features
Classic Snake Gameplay

Traditional grid-based snake movement

Snake grows after eating food

Score tracking system

Game ends when the snake hits the wall or itself

Smooth movement and animations

Gesture-Based Controls

Real-time hand tracking using MediaPipe

Swipe gestures control snake direction

Pinch gesture activates speed boost

Hand landmark visualization for feedback

Dual Window Display

The game runs using two windows:

Game Window

Displays the Snake gameplay

Shows score and game state

Camera Window

Displays webcam feed

Shows hand detection and gesture tracking

Getting Started
1. Clone the Repository
git clone https://github.com/yourusername/gesture-snake-game.git
cd gesture-snake-game
2. Install Required Libraries
pip install -r requirements.txt
3. Start the Game
python main.py
System Requirements

Python 3.7 or higher

Working webcam

Recommended lighting for accurate gesture detection

Python Libraries

opencv-python

mediapipe

numpy

pygame

How the Controls Work
Gesture Controls
Gesture	Function
Hand movement upward	Move snake up
Hand movement downward	Move snake down
Hand movement left	Move snake left
Hand movement right	Move snake right
Pinch (thumb + index finger)	Speed boost
Keyboard Controls
Key	Action
ESC	Exit the game
Q	Quit gesture window
Up gesture after game over	Restart game
Gameplay Mechanics
Snake Movement

The snake continuously moves in the last detected direction.

Direct reverse movement is disabled to prevent instant collision.

Scoring

Eating food increases the score.

Each fruit gives 10 points.

Game Over Conditions

The game ends when:

The snake hits a wall

The snake collides with itself

After the game ends, performing the Up gesture restarts the game.

Project Structure
gesture-snake-game
│
├── main.py                # Runs the application
├── snake_game.py          # Game logic and rendering
├── gesture_controller.py  # Gesture detection system
├── requirements.txt       # Project dependencies
└── README.md              # Project documentation
Implementation Details
Game Engine

The game interface is built using Pygame, which manages rendering, movement updates, and game state.

Computer Vision Pipeline

The gesture system uses:

OpenCV for webcam capture and frame processing

MediaPipe Hands for detecting hand landmarks

Gesture analysis based on movement thresholds

Design Approach

The project follows a modular structure, separating:

game mechanics

gesture detection

application control

This makes the project easier to maintain and extend.

Troubleshooting
Webcam Not Detected

If the webcam does not start:

Ensure the camera is connected

Check if another application is using it

Try changing the camera index in the code

Example:

cv2.VideoCapture(0)

Try replacing 0 with 1 or 2.

Gesture Detection Problems

If gestures are not detected properly:

Improve lighting conditions

Ensure your full hand is visible

Avoid cluttered backgrounds

Low Performance

If the game runs slowly:

Close other applications using the webcam

Reduce camera resolution in the code

Ensure GPU drivers are updated

Customization
Change Gesture Sensitivity

Inside gesture_controller.py you can adjust detection sensitivity:

gesture_threshold = 0.05

Lower values make gestures more sensitive.

Modify Game Speed

Inside snake_game.py you can adjust snake speed:

base_speed = 8
boost_speed = 15
Edit Game Colors

You can modify the color scheme in the game configuration:

snake_color = (155,188,15)
snake_head = (204,255,51)
Future Improvements

Possible features that can be added:

Multiplayer mode

Additional gestures

Difficulty levels

Mobile camera support

AI-based gesture recognition

License

This project is released under the MIT License.

Author

Yash Shah

Built as part of a Python module exploration project using MediaPipe.

Acknowledgements

MediaPipe for real-time hand tracking

OpenCV for computer vision tools

Pygame for game development framework

Inspired by the classic Nokia Snake game

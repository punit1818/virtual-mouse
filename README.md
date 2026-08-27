# Virtual Mouse

A hands-free virtual mouse for Windows that uses a webcam and MediaPipe hand tracking to control the cursor, mouse buttons, scrolling, screen brightness, and system volume.

## Features

- Move the cursor with a two-finger V gesture
- Left-click with the middle-finger gesture
- Right-click with the index-finger gesture
- Double-click with two closed fingers
- Drag with a fist
- Scroll vertically or horizontally with a minor-hand pinch
- Adjust brightness or volume with a major-hand pinch
- View detected hand landmarks in the OpenCV camera window

## Requirements

- Windows
- Python 3.9 or newer
- A working webcam
- A display with brightness control support
- A microphone is not required

The project uses these Python packages:

- `opencv-python`
- `mediapipe`
- `pyautogui`
- `math` (Python standard library)
- `enum34` is not required; `enum.IntEnum` is included with Python
- `comtypes`
- `pycaw`
- `screen-brightness-control`
- `protobuf`

## Installation

Create and activate a virtual environment, then install the dependencies:

```powershell
python -m venv .venv
.\.venv\Scripts\Activate.ps1
python -m pip install --upgrade pip
python -m pip install opencv-python mediapipe pyautogui comtypes pycaw screen-brightness-control protobuf
```

If PowerShell blocks script activation, run this once for the current user:

```powershell
Set-ExecutionPolicy -Scope CurrentUser RemoteSigned
```

## Usage

Run the program from the project directory:

```powershell
python .\virtual-mouse-main.py
```

A window named **Gesture Controller** opens and shows the webcam feed with hand landmarks. Press `q`, or close that window, to stop the program.

## Gesture Controls

| Gesture | Action |
| --- | --- |
| V gesture | Enable cursor movement with the dominant hand |
| Middle-finger gesture | Left click after cursor movement is enabled |
| Index-finger gesture | Right click after cursor movement is enabled |
| Two-finger closed gesture | Double click after cursor movement is enabled |
| Fist | Hold the left mouse button and drag |
| Minor-hand pinch, horizontal movement | Horizontal scroll |
| Minor-hand pinch, vertical movement | Vertical scroll |
| Major-hand pinch, horizontal movement | Change system brightness |
| Major-hand pinch, vertical movement | Change system volume |

The script treats the right hand as the dominant hand by default. The dominant-hand setting is defined by `GestureController.dom_hand` in the Python file.

## Notes and Troubleshooting

- Give the application permission to use the webcam.
- Keep your hand visible and reasonably well lit.
- Close other applications that may be using the webcam.
- The brightness feature depends on Windows and display hardware support.
- The volume feature controls the default Windows audio output device.
- `pyautogui.FAILSAFE` is disabled by the script, so use `q` or close the camera window to exit.

## License

No license has been specified for this project yet.

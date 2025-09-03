# EnvironmentMusic Project Aria Proof of Concept

## Getting Started
This is a proof of concept of using Project Aria glasses to calculate a live 'traffic score' by using real-time YOLO (You Only Look Once) object detection.
The YOLO model used is a standard model trained on the COCO (common objects in contex) image dataset.

Every frame, the script prints:
- A live count of the number of people/vehicles currently seen by the RGB camera
- A lagged count that lags behind the live count whenever the live count decreases, smoothly decreasing to the live count level over 2 seconds - this is to prevent scores jumping wildly and to try and account for surrounding traffic that has briefly disappeared from immediate view.

Aria streaming code from https://facebookresearch.github.io/projectaria_tools/docs/ARK/sdk/concepts/streaming_internals and https://github.com/EdoWhite/ARIA_YOLO

### Prerequisites
- Python 3.9-3.11
- OpenCV (cv2)
- NumPy
- Aria SDK (only built for Mac or some x64 Linux distributions)
- Project Aria Mobile Companion App
It's suggested that you use a virtual Python environment for the Aria SDK and other Aria tools.

## Setup
F#ollow these instructions to pair the glasses with your computer: https://facebookresearch.github.io/projectaria_tools/docs/ARK/sdk/setup

## Usage

Run using the following commands, depending on your choice of interface (USB or WiFi):
- For USB use:
```bash
python realtimeYOLO.py --interface usb
```
- For WiFi use (replace glasses_ip with the ip of the Project Aria glasses):
```bash
python realtimeYOLO.py --interface wifi --device_ip {glasses_ip}
```

Press `escape` or `q` to quit.


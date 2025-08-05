# Face detection

## Example
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/facedetect/ex.svg">

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
from MCLab.ai_tools import *


screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)


label0 = MCLabel('label0', x=125, y=100, color=0x000, font=FONT_MONT_14, parent=None)

while True:
  if (face_detect.get_face_number()) >= 1:
    label0.set_text('Hello!')
  else:
    label0.set_text('Scanning...')
  wait_ms(2)
```

## API

- Initialize the face detection module
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/1.svg">
```python
face_detect.init()
```

-Returns the number of faces currently detected in the frame.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/facedetect/2.svg">

```python
face_detect.get_face_number()
```

- Get details of each detected face
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/facedetect/3.svg">

  - x: X-coordinate of the bounding box
  
  - y: Y-coordinate of the bounding box
  
  - w: Width of the bounding box
  
  - h: Height of the bounding box
  
  - value: Confidence score of the detection
  

```python
face_detect.get_face_detials()
```

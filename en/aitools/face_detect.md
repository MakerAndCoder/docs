-Initialize the face detection module
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/1.svg">
```python
face_detect.init()
```

-Returns the number of faces currently detected in the frame.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/2.svg">

```python
face_detect.get_face_number()
```

-Get details of each detected face
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/aitools/3.svg">

  -x: X-coordinate of the bounding box
  -y: Y-coordinate of the bounding box
  -w: Width of the bounding box
  -h: Height of the bounding box
  -value: Confidence score of the detection

```python
face_detect.get_face_detials()
```

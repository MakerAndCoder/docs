# List

## Example

Array processing is used with array functions

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_Example.svg">

```python
from m5stack import *
from m5ui import *
from uiflow import *

list01 = None
list02 = None

def first_index(my_list, elem):
  try: index = my_list.index(elem) + 1
  except: index = 0
  return index

list01 = []
list02 = [1, 2, 3, [4, 5, 6]]
print(len(list02))
print(not len(list01))
print(list02[1])
print(first_index(list02, 1))
print(list02[2 : 4])
print(list(reversed(list02)))

list02[-1] = 9
print(list02)

list01 = [2] * 2
print(list01)

print('1,2,3,4'.split(','))
```

## API
- Create a custom empty list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_create_empty.svg">

```python
list01 = []
```

<br><br>
- Build a list using elements repeated a certain number of times
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_create_with.svg">

```python
list02 = [1, 2, 3, [4, 5, 6]]
```

<br><br>
- Get the value of an element at a specific index in the list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_getIndex.svg">

```python
print(list02[1])
```

<br><br>
- Slice elements from the list to create a new list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_getSublist.svg">

```python
print(list02[2 : 4])
```

<br><br>
- Access an element in the list by index, either in forward or reverse order
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_indexOf.svg">

```python
print(first_index(list02, 1))
```

<br><br>
- Check if a list is empty, returning True if it is, and False otherwise
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_isEmpty.svg">

```python
print(not len(list01))
```

<br><br>
- Measure the length of the list (i.e., the number of elements in the list)
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_length.svg">

```python
print(len(list02))
```

<br><br>
- (Note: This is a duplicate of the previous functionality) Build a list using elements repeated a certain number of times
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_repeat.svg">

```python
list01 = [2] * 2
print(list01)
```

<br><br>
- Reverse the order of elements in the list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_reverse.svg">

```python
print(list(reversed(list02)))
```

<br><br>
- Set a specific value at a given index in the list
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_setIndex.svg">

```python
list02[-1] = 9
print(list02)
```

<br><br>
- Create a list from text, using a delimiter
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/Lists/uiflow_block_lists_split.svg">

```python
print('1,2,3,4'.split(','))
```



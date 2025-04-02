# Math

## Example

Simple logical operations and variable assignment

<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_example.svg" >

```python
from MakerAndCoder import *
from MakerAndCoder_ui import *
from uiflow import *
import math

screen = MCScreen()
screen.clean_screen()
screen.set_screen_bg_color(0xFFFFFF)

date = None
list1 = None

import math
import random

date = 10
date = 11 + 12
date = 13 + 4 - 8 % 2 - 7
date = 5 & 6
date = math.pi
date = 9 % 2
date = 8 % 2 == 0
list1 = [5, 4, 3]
date = sum(list1)
date = random.random()
date = random.randint(0, 10)
date = min(max(50, 1), 100)
date = math.remap(0, 0, 1023, 0, 255)
date = round(2.4)
date = math.sqrt(0)
date = math.sin(10 / 180.0 * math.pi)
date = int('8')
date = float('0.8')
date = ((10 >> 0) & 0x01)
date = (10 | (0x01 << 0))
date = (10 & (~ (0x01 << 0)))
date = (10 ^ (0x01 << 0))
date = int.from_bytes(10, 'big')
```
## API
- Add a constant
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_number.svg" >

```python
date = 10
```

<br><br>
- Perform `addition`/`subtraction`/`multiplication`/`division`/`modulus`/`exponentiation` operations on both sides of the equation
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_arithmetic.svg" >

```python
date = 11 + 12
```

<br><br>
- Perform `addition`/`subtraction`/`multiplication`/`division`/`modulus`/`exponentiation` operations on two or more values
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_arithmetic_arr.svg" >

```python
date = 13 + 4 - 8 % 2 - 7
```

<br><br>
- Bitwise operation
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_bit_operation.svg" >

```python
date = 5 & 6
```

<br><br>
- Assign the constant value of π
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_constant.svg" >

```python
date = math.pi
```

<br><br>
- Modulus operation
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_modulo.svg" >

```python
date = 9 % 2
```

<br><br>
- Detect a data value. `even`/`old`/`prime`/`whole`/`positive`/`negative`/`divisible by`
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_number_property.svg" >

```python
date = 8 % 2 == 0
```

<br><br>
- Array operation function
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_on_list.svg" >

```python
date = sum(list1)
```

<br><br>
- Output a random floating-point number between 0 and 1
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_random_float.svg" >

```python
date = random.random()
```

<br><br>
- Output a random number within a specific range
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_random_int.svg" >

```python
date = random.randint(0, 10)
```

<br><br>
- Limit the range of a data value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_constrain.svg" >

```python
date = min(max(50, 1), 100)
```

<br><br>
- Value mapping
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_remap.svg" >

```python
date = math.remap(0, 0, 1023, 0, 255)
```

<br><br>
- Round a number using the round() function
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_round.svg" >

```python
date = round(2.4)
```

<br><br>
- Apply mathematical functions to a numeric value. `sqrt()`/`log()`/`log10()`/`exp()`/`pow()`
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_single.svg" >

```python
date = math.sqrt(0)
```

<br><br>
- Trigonometric functions. `sin()`/`cos()`/`tan()`/`asin()`/`acos()`/`atan()`
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_trig.svg" >

```python
date = math.sin(10 / 180.0 * math.pi)
```

<br><br>
- Convert the data type to int
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_convent_int.svg" >

```python
date = int('8')
```

<br><br>
- Convert the data type to float
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_convent_float.svg" >

```python
date = float('0.8')
```

<br><br>
- Clear a specific bit in a data value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_clear_bit.svg" >

```python
date = ((10 >> 0) & 0x01)
```

<br><br>
- Get a specific bit in a data value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_get_bit.svg" >

```python
date = (10 | (0x01 << 0))
```

<br><br>
- Modify a specific bit in a data value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_set_bit.svg" >

```python
date = (10 & (~ (0x01 << 0)))
```

<br><br>
- Flip the least significant bit of a given value
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_int_from_bytes.svg" >

```python
date = int.from_bytes(10, 'big')
```

<br><br>
- Convert a byte sequence to an integer
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/generic/math/uiflow_block_math_reverse_bit.svg" >

```python
date = (10 ^ (0x01 << 0))
```



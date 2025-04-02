# Module LoRaWAN P2P

## API
- uiflow_block_lorawan_data
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lorawan_p2p/uiflow_block_lorawan_data.svg">

```python

```

<br><br>
- uiflow_block_lorawan_initp2p
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lorawan_p2p/uiflow_block_lorawan_initp2p.svg">

```python

lorawan0 = module.get(module.LORAWAN)

lorawan0.initP2PMode(1)
```


<br><br>
- uiflow_block_lorawan_initrx
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lorawan_p2p/uiflow_block_lorawan_initrx.svg">

```python
lorawan0 = module.get(module.LORAWAN)

def lorawan0_cb(data):
  global wdt
  pass
lorawan0.initRxMode(lorawan0_cb)


```


<br><br>
- uiflow_block_lorawan_txt
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/lorawan_p2p/uiflow_block_lorawan_txt.svg">

```python
lorawan0 = module.get(module.LORAWAN)

lorawan0.txStr('')
```




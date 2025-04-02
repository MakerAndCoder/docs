## coming soon

# Azure IoT


## API
- uiflow_block_azure_pnp_init_central
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_iot/uiflow_block_azure_pnp_init_central.svg">

```python
azurepnp = IoT_Central(scope_id='', device_id='', device_key='', model_id='dtmi:m5stack:pnpdevice:n3zte8m;1')
azurepnp.start()
```

<br><br>
- uiflow_block_azure_pnp_command_cb
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_iot/uiflow_block_azure_pnp_command_cb.svg">

```python
def azure_direct____(payload, rid):
  # global params

  azurepnp.response_direct_method(0, rid, body='')
```

<br><br>
- uiflow_block_azure_pnp_property_cb
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_iot/uiflow_block_azure_pnp_property_cb.svg">

```python
def ____cb(name, value):
  # global params
  _ = value

  result = 200
  return (value, result)
```

<br><br>
- uiflow_block_azure_pnp_send_telemetry
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_iot/uiflow_block_azure_pnp_send_telemetry.svg">

```python
# Send _ telemetry to Azure
azurepnp.publish_D2C_message(json.dumps({}), "_")
```

<br><br>
- uiflow_block_azure_pnp_update_property
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/iot_cloud/azure_iot/uiflow_block_azure_pnp_update_property.svg">

```python
# Update _ property to Azure
azurepnp.update_twin_reported_properties(json.dumps({'_':{'__t':'c', }}))
```




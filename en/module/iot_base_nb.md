# IoT Base NB

## API
- Checks if the device is registered on the GPRS network.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_check_gprs_network_registration.svg">

```python
nbiot.get_gprs_network_registration()
```

<br><br>
- Checks if the device is successfully registered on the network (general network registration check).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_check_network_registration.svg">

```python
nbiot.get_network_registration()
```

<br><br>
- Checks the signal quality of the current network and returns signal strength information.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_check_single_quality.svg">

```python
nbiot.get_single_quality()
```

<br><br>
- Checks the status of the module to see if it's working properly or if there are any issues.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_check_status.svg">

```python
nbiot.check_status()
```

<br><br>
- Destroys the CoAP connection, closing the CoAP session or releasing related resources.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_coap_destroy.svg">

```python
nbiot.coap_destroy()
```

<br><br>
- Executes a CoAP GET request with the specified URL. You can set security options, but here none is selected (None).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_coap_get.svg">

```python
nbiot.coap_get('/makerandcoder-get')
```

<br><br>
- Initializes the CoAP connection by specifying the target server's IP address (e.g., 120.77.157.90) and port (e.g., 5683).
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_coap_init_ip.svg">

```python
nbiot.coap_to_connect('120.77.157.90', 5683)
```

<br><br>
- Sends a CoAP POST request with the specified URL. The content (payload) is sent in plain text (TEXT_PLAIN) format. The URL here is /makerandcoder-post.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_coap_post.svg">

```python
nbiot.coap_post('/makerandcoder-post', '', content_format=0)
```

<br><br>
- Sends a CoAP PUT request with the specified URL, used to update resources or data. The payload's content format is also TEXT_PLAIN, and the URL is /makerandcoder-put.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_coap_put.svg">

```python
nbiot.coap_put('/makerandcoder-put', '', content_format=0)
```

<br><br>
- Asynchronously retrieves data from the cloud platform by specifying the topic and token.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_ezdata_async_get_value.svg">

```python
nbiot.get_ezdata(ezdata_get_NRZBHcb, 'GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

<br><br>
- Removes the specified topic from the cloud platform using the given token.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_ezdata_remove.svg">

```python
nbiot.remove_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '')
```

<br><br>
- Saves data to the specified topic, with a token for verification.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_ezdata_save.svg">

```python
nbiot.set_ezdata('GCJ3Ic5h2eXnzV3rT3bBXvrncCaJnART', '', '', 0)
```

<br><br>
- Retrieves the CCID (Integrated Circuit Card Identifier) of the device, typically used to identify the SIM card.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_get_ccid.svg">

```python
nbiot.get_CCID()
```

<br><br>
- Retrieves the IMEI (International Mobile Equipment Identity) of the device, used to uniquely identify mobile devices.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_get_imei.svg">

```python
nbiot.get_IMEI()
```

<br><br>
- Initializes Modbus communication, configuring the Tx and Rx pins, baud rate, mode (master/slave), and slave address.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_init.svg">

```python
nbiot.modbus_init(15, 13, 115200, 1, 1)
```

<br><br>
- Reads the status of coils from the specified slave address and start address, with configurable coil quantity.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_read_coils.svg">

```python
modbus.read_coils(1, 1, 0)
```

<br><br>
- Reads the status of discrete inputs from the specified slave address, with configurable start address and input quantity.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_read_discrete_inputs.svg">

```python
modbus.read_discrete_inputs(1, 1, 0)
```

<br><br>
- Reads the values of holding registers, specifying slave address, start address, and register quantity, with an option to read signed values.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_read_holding_registers.svg">

```python
modbus.read_holding_registers(1, 1, 0, True)
```

<br><br>
- Reads the values of input registers, specifying slave address, start address, and register quantity, with an option to read signed data.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_read_input_registers.svg">

```python
modbus.read_input_registers(1, 1, 0, True)
```

<br><br>
- Writes output values to multiple coils, specifying slave address, start address, and output values.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_write_multiple_coils.svg">

```python
modbus.write_multiple_coils(1, 1, 0)
```

<br><br>
- Writes values to multiple registers, specifying slave address, start address, register values, with an option to write signed data.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_write_multiple_registers.svg">

```python
modbus.write_multiple_registers(1, 1, 0, True)
```

<br><br>
- Writes output values to a single coil, specifying slave address, output address, and output value.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_write_single_coil.svg">

```python
modbus.write_single_coil(1, 1, 0)
```

<br><br>
- Writes values to a single register, specifying slave address, register address, and register value, with an option to write signed data.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_master_u_write_single_register.svg">

```python
modbus.write_single_register(1, 1, 0, True)
```

<br><br>
- Sets the function code of the slave for reading coil status.
  - 1:READ_COILS_STATUS
  - 2:READ_INPUT_STATUS
  - 3:READ_HOLDING_REGISTERS
  - 4:READ_INPUT_REGISTERS
  - 5:WRITE_SINGLE_COIL
  - 6:WRITE_SINGLE_REGISTER
  - 7:WRITE_MULTIPLE_COILS
  - 8:WRITE_MULTIPLE_REGISTERS
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_fun_status.svg">

```python
1~8
```

<br><br>
- Retrieves the address information of the slave.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_get_address.svg">

```python
modbus.find_address
```

<br><br>
- Retrieves the current function code being used.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_get_function.svg">

```python
modbus.find_function
```

<br><br>
- Retrieves the number of data points to be read.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_get_quantity.svg">

```python
modbus.find_quantity
```

<br><br>
- Initializes the Modbus slave function, setting the start address and quantity to be read, used for reading coil status.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_init_func.svg">

```python
modbus.function_init(1, 0, 0)
```

<br><br>
- Used to receive the Application Data Unit (ADU) request from the master.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_receive_adu.svg">

```python
modbus.receive_req_create_pdu()
```

<br><br>
- Sends the ADU response, typically used by the slave to reply to the master request.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_send.svg">

```python
modbus.create_slave_response(1)
```

<br><br>
- Updates the Modbus function block (e.g., READ_COILS_STATUS) data, setting the start address, quantity, and values to write.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modbus_slave_rtu_update_func.svg">

```python
modbus.update_process(1, 0, 0, [0, 0, 0])
```

<br><br>
- Controls the power switch of the communication module, with options to turn it on or off.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_modem_power.svg">

```python
nbiot.modem_power(True)
```

<br><br>
- Checks the MQTT connection status, ensuring the device is properly connected to the MQTT server.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_check_connection.svg">

```python
nbiot.mqtt_check_connection()
```

<br><br>
- Initializes the connection to the MQTT server, setting the server address, port, client ID, username, password, and heartbeat interval. Used to connect to the MQTT server for data communication.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_connect.svg">

```python
nbiot.mqtt_to_connect('mqtt.makerandcoder.com', 1883, '', '', '', 120)
```

<br><br>
- Disconnects from the MQTT server.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_disconnect.svg">

```python
nbiot.mqtt_disconnect()
```

<br><br>
- Polls and receives messages from the MQTT server.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_poll.svg">

```python
nbiot.mqtt_poll()
```

<br><br>
- Publishes a message to the specified MQTT topic, including the payload and Quality of Service (QoS) level.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_publish.svg">

```python
nbiot.mqtt_publish('', '', 0)
```

<br><br>
- Subscribes to the specified MQTT topic, receiving messages from that topic. QoS defines the message service quality level.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_sub.svg">

```python
nbiot.mqtt_subscribe('', iotbase_mqtt_cb, 0)
```

<br><br>
- Registers a callback function to handle messages received from the subscribed MQTT topic. `nb_topic` and `nb_msg` are used to get the topic and message content.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_sub_cb.svg">

```python
def iotbase_mqtt_cb(nb_mq_topic, nb_mq_payload):
  global ezdata_value1, nb_topic, nb_msg
  nb_topic = nb_mq_topic
  nb_msg = nb_mq_payload
  pass
```

<br><br>
- Unsubscribes from the specified MQTT topic.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_mqtt_unsubscribe.svg">

```python
nbiot.mqtt_unsubscribe('')
```

<br><br>
- Powers off the module, usually for saving energy or shutting down the device.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_power_down_module.svg">

```python
nbiot.poweroff()
```

<br><br>
- Resets the module, restoring it to its initial state.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_reset_module.svg">

```python
nbiot.reset()
```

<br><br>
- Sets the command echo mode. You can choose whether to display the command echo returned by the device when executing commands.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_set_echo_mode.svg">

```python
nbiot.set_command_echo_mode(0)
```

<br><br>
- Checks and retains cached data, used to determine whether there is unread data in the UART buffer.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_any.svg">

```python
modbus._mdbus_uart.any()
```

<br><br>
- Reads all data in the UART buffer.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_read.svg">

```python
modbus._mdbus_uart.read()
```

<br><br>
- Reads a line of data from UART until a newline character is encountered.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_readline.svg">

```python
modbus._mdbus_uart.readline()
```

<br><br>
- Reads the specified number of characters from UART. In this example, it reads 10 characters.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_read_characters.svg">

```python
modbus._mdbus_uart.read(10)
```

<br><br>
- Writes the specified text or data to the UART port.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_write.svg">

```python
modbus._mdbus_uart.write('')
```

<br><br>
- Writes the specified text or data to the UART port in the form of a line, appending a newline character at the end.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_write_line.svg">

```python
modbus._mdbus_uart.write(''+"\r\n")
```

<br><br>
- Writes raw data to the UART in the form of a byte list. This block can send binary data, commonly used for transmitting raw or non-text data.
<img class="blockly_svg" src="https://makerandcoder.com/MCLab/blockly/modules/iot_base_nb/uiflow_block_iotbase_uart_write_raw_data.svg">

```python
modbus._mdbus_uart.write(bytes([0, 0, 0]))
```


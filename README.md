# EXPERIMENT-06-Data-Publishing-to-IoT-Broker-Using-MQTT3
 
 ### NAME:  VISHNUPRIYA R
 ### REGISTER NUMBER:212222110054
 ### DEPARTMENT: CSE-IoT
 ### YEAR:3rd year

 ## Aim:
To publish data to an IoT broker using the MQTT protocol.

 ## Apparatus Required:
MQTT Broker: An MQTT broker, such as HiveMQ or Mosquitto, for handling communication.
Python Environment: To run the script for publishing data to the broker.
Internet Connection: For connecting to the IoT broker.
Theory:
MQTT (Message Queuing Telemetry Transport) is a lightweight messaging protocol used in IoT applications. It allows devices to publish data to a broker, where other devices or applications can subscribe to receive updates. This experiment demonstrates how to use MQTT to send messages to an IoT broker using the paho-mqtt library in Python.

 ## Procedure:

Setup MQTT Broker:</BR>
You can use a public broker like broker.hivemq.com or set up your own broker using software like Mosquitto.
Choose a topic for the message, e.g., test/topic.

Install MQTT Client Library:</BR>
Install the paho-mqtt Python library to facilitate communication with the MQTT broker.
```
!pip install paho-mqtt
```

Write the Python Script to Publish Data:</BR>
Create a Python script to connect to the broker and publish a message to a specific topic.
Code Implementation: Here’s the Python code to publish data to the IoT broker using MQTT:
```
import paho.mqtt.client as mqtt
```

## Broker details
```
broker_address = "broker.hivemq.com"  # Broker address
broker_port = 1883  # Broker port
topic = "test/topic"  # Topic to publish to
```

## Initialize the MQTT Client
```
client = mqtt.Client()
```

## Connect to the broker
```
client.connect(broker_address, broker_port, keepalive=60)
```

## Publish a message to the topic
```
message = "Hello, MQTT!"  # Message to be published
client.publish(topic, message)
```

## Disconnect from the broker
```
client.disconnect()
```

# Print confirmation message
```
print(f"Message '{message}' published to topic '{topic}'")
```
Run the Script:
Execute the script. It will connect to the MQTT broker, publish the message to the specified topic, and then disconnect.
Verify Message Publishing:
You can verify the message by subscribing to the same topic using an MQTT client, such as MQTT.fx or any other MQTT subscriber tool.
 
## Outputs:
Message Confirmation: The script will print a message confirming that the data has been successfully published to the topic.
Example output:
Message 'Hello, MQTT!' published to topic 'test/topic'
Broker Message: The message "Hello, MQTT!" will be published to the topic test/topic.

## Python Code 
```
!pip install paho-mqtt
import paho.mqtt.client as mqtt
broker_address = "broker.hivemq.com"
broker_port = 1883
topic = "test/topic"
client = mqtt.Client()
client.connect(broker_address, broker_port, keepalive=60)
message = "Hello, MQTT"
client.publish(topic, message)
client.disconnect()
print(f"Message '{message}' published to topic '{topic}' ")
broker_address = "broker.hivemq.com"
broker_port = 1883
topic = "test/topic"
client = mqtt.Client()
client.connect(broker_address , broker_port , keepalive = 60)
message = "Hello , MQTT"
client.publish(topic,message)
client.disconnect()
print(f"Message '{message}' publish to topic '{topic}' ")
```
  
 ## Simulation Screenshots:

![6](https://github.com/user-attachments/assets/3f0267d2-86bc-4e9e-adc0-d41adf355164)

![RE](https://github.com/user-attachments/assets/0542aaa8-6cda-4294-848e-5821b61c7689)

 ## Results:
The data was successfully published to the MQTT broker. The experiment demonstrated how to use the MQTT protocol to transfer data to an IoT broker, enabling remote communication between devices or applications. The message was confirmed to be received by the topic, and this communication can be extended to more complex IoT systems.

# Exploring MQTT QoS Levels

Experiment with QoS 0, 1, and 2.
Observe how message delivery changes based on QoS settings.

## Publisher_qos.py output

```
Enter message to publish: [15:22:50] DEBUG | Received CONNACK (0, 0)
hello moneky
Enter QoS level (0, 1, 2): 2
[15:22:58] DEBUG | Sending PUBLISH (d0, q2, r0, m1), 'b'test/qos/6510301024/temperature'', ... (12 bytes)
[15:22:58] PUBLISH REQUESTED | QoS=2 | Message='hello moneky' | msgid=1
Enter message to publish: [15:22:58] DEBUG | Received PUBREC (Mid: 1)
[15:22:58] DEBUG | Sending PUBREL (Mid: 1)
[15:22:58] DEBUG | Received PUBCOMP (Mid: 1)
[15:22:58] PUBLISHED | msgid=1
```

## Subscriber_qos.py Output

```
[15:53:55] RECEIVED | temperature: hello worldddd | QoS=2
[15:53:55] DEBUG | Sending PUBCOMP (Mid: 1942)
[15:53:56] DEBUG | Received PUBLISH (d0, q1, r0, m1943), 'test/qos/6510301024/temperature', ...  (5 bytes)
[15:53:56] RECEIVED | temperature: 31.19 | QoS=1
[15:53:56] DEBUG | Sending PUBACK (Mid: 1943)
[15:53:56] DEBUG | Received PUBLISH (d0, q1, r0, m1944), 'test/qos/6510301024/humidity', ...  (5 bytes)
[15:53:56] RECEIVED | humidity: 66.12 | QoS=1
[15:53:56] DEBUG | Sending PUBACK (Mid: 1944)
[15:53:56] DEBUG | Received PUBLISH (d0, q1, r0, m1945), 'test/qos/6510301024/pressure', ...  (7 bytes)
[15:53:56] RECEIVED | pressure: 1014.59 | QoS=1
[15:53:56] DEBUG | Sending PUBACK (Mid: 1945)
[15:53:56] DEBUG | Received PUBLISH (d0, q1, r0, m1946), 'test/qos/6510301024/fan_speed', ...  (1 bytes)
[15:53:56] RECEIVED | fan_speed: 3 | QoS=1
[15:53:56] DEBUG | Sending PUBACK (Mid: 1946)
```
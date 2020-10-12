# Door Lock System 

Atmega128, 키패드, 모터, LCD, 터미널, 버튼 등을 활용한 도어락 시스템

****
> 1. Keypad를 이용해 비밀번호를 입력합니다.
> 2. 비밀번호가 일치하면, LCD창에 “Open The Door” 라는 문구가 나타나며 문(모터)이 열립니다.
> 3. 비밀번호가 일치하지 않으면, LCD창에 “Password False!!” 라는 문구가 나타납니다.
> 4. 변경 버튼을 누르게 되면, Keypad를 통해 비밀번호 변경이 가능합니다.
> 5. 터미널 버튼을 누르게 되면, Serial 통신을 통해 비밀번호 변경아 가능합니다.
****


#### 시연영상

![QR](/readmeFile/DoorLock_QRCode.png)

****
> Proteus
****
![Proteus](/readmeFile/DoorLock_Main.png) 

## Getting Started
To use MQTT-C you first instantiate a `struct mqtt_client` and initialize it by calling
@ref mqtt_init.
```c
    struct mqtt_client client; /* instantiate the client */
    mqtt_init(&client, ...);   /* initialize the client */
```
Once your client is initialized you need to connect to an MQTT broker.
```c
    mqtt_connect(&client, ...); /* send a connection request to the broker. */
```
At this point the client is ready to use! For example, we can subscribe to a topic like so:
```c
    /* subscribe to "toaster/temperature" with a max QoS level of 0 */
    mqtt_subscribe(&client, "toaster/temperature", 0);
```
And we can publish to a topic like so:
```c
    /* publish coffee temperature with a QoS level of 1 */
    int temperature = 67;
    mqtt_publish(&client, "coffee/temperature", &temperature, sizeof(int), MQTT_PUBLISH_QOS_1);
```
Those are the basics! From here the [examples](https://github.com/LiamBindle/MQTT-C/tree/master/examples) and [API documentation](https://liambindle.ca/MQTT-C/group__api.html) are good places to get started.




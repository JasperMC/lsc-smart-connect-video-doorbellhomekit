# LSC Smart Connect Video Doorbell Homekit
Attempt to make the Bell 8S / LSC Smart Connect Video Doorbell fully compatible with HomeKit

# Device specifications:
Device name: Smart Home Camera
Model: Bell 8S
Softwareversion: 2.9.7
Hardwareversion: BE8S_H1_V10_433
Firmwareversion: ppstrong-c51-tuya2_lcs-2.9.7.20201020

# Possible HomeKit Configuration:
Accessory (Bell 8S): Video Doorbell
- Doorbell Service (Programmable Switch Button)
- Camera RTP Stream Management Service
- Microphone Service
- Speaker Service (for two-way audio)

# Approach to make compatible:
Device runs an app called ppsapp which contains the bell's logic: Streaming video, playing audio, registering events, etcetera.

In order to get a fully working HomeKit doorbell that application needs to either be patched into, modified (keeping the Tuya-side intact) or completely replaced.

# Investigating HomeKit Compatability
- Doorbell Service: The state of the doorbell can be retrieved by hooking into the devices's logs.
- Motion Service: The motion detection of the doorbell can be retrieved by hooking into the device's logs
- Camera RTP Stream Management Service: Can be hooked into via RTSP or Onvif
- Speaker Service: Requires modification of ppsapp due to it reserving the connection to the audio device. Two way audio is an entirely different challenge.
- Microphone Service: Unknown at this time.


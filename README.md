# OpenCV 3 - Docker image

Docker image for OpenCV 3.x.x with Python3 support and FFmpeg with x264 enabled. It is meant to be used in servers for video processing task or just for scripting purposes.

## Building

You can build and modify this image by cloning the project and executing:

```
docker build -t docker-compose-marker-crop .
```

## Checking

Just exec `docker-compose up`

and you should see a message like

```
opencv_1  | You have OpenCV <version> installed!
```

## Running

To make the image lightweight it lacks of an X11 environment installed so, for example, you cannot use cv::createWindow or cv::waitKey functions.However, you can create a container with access rights to your webcam writing:

```
Example of running this project
docker run -it --privileged --device /dev/video0:/dev/video0 docker-compose-marker-crop python3
```


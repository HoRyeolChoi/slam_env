# build
docker build . --tag slam:latest --progress=plain
echo "xhost +local:docker" >> ~/.profile

# run
xhost +local:docker : enable docker port for visualization
docker build . -t slam:latest
docker run -it --env DISPLAY=$DISPLAY -v /tmp/.X11-unix/:/tmp/.X11-unix:ro slam:폴더명
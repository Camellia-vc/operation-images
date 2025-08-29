### docker run命令
```bash
sudo docker run -Pdit \
--name=development \
--privileged \
-e NVIDIA_DRIVER_CAPABILITIES=all \
-e DISPLAY=$DISPLAY \
-e WAYLAND_DISPLAY=$WAYLAND_DISPLAY \
-e XDG_RUNTIME_DIR=$XDG_RUNTIME_DIR \
-e QT_QPA_PLATFORM=wayland \
-v /home/nmh/Operation:/home/nmh/Operation \
-v /tmp/.X11-unix:/tmp/.X11-unix:rw \
-v /run/user/$(id -u)/wayland-0:/run/user/1000/wayland-0:rw \
-v /dev/dri:/dev/dri \
--device=/dev/snd \
--device=/dev/dri/renderD128 \
--net=host \
--ipc=host \
-w /home/nmh/Operation development:1.0
```
### 只挂载/home/nmh/目录下的Operation文件夹
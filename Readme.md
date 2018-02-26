## Store CAN data from solar box into db

### Create CAN socket
``` shell
modprobe vcan
ip link add vcan0 type vcan
ip link set vcan0 up
```

### Test socket
``` shell
candump -L vcan0
cansend vcan0 012#deadbeef
```

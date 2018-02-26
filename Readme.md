## Store CAN data from solar box into db

### Create CAN socket
``` shell
sudo modprobe vcan
sudo ip link add vcan0 type vcan
sudo ip link set vcan0 up
```

### Test socket
``` shell
candump -L vcan0
cansend vcan0 012#deadbeef
```

### prepare python env (not needed but advised)
In directory with requirements.txt:

``` shell
virtualenv -p python3 .cantodb
source .cantodb/bin/activate
pip install -r requirements.txt
```
You can skip the first two commands, then all python packages will be added to your computer's python installation! You can leave the environment simply with
``` shell
deactivate
```

### Usage:
``` shell
python cantodb.py vcan0
```
You should see decoded cbor data

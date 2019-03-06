# Introduction

This is a control package for DJI N3/PX4(in progress) high level position control using Visual Odometry or mocation capture.
It also provide some system iden function with combintation of my other great repo https://github.com/xuhao1/pyaircraftiden.

## Usage
The only interface is sending message to topic "/drone_commander/onboard_command".

drone_cmd.py provide a great example for usage including takeoff, flyto somewhere landing and also do a sweep frequency experiment.

```
uint32 CTRL_POS_COMMAND=0
uint32 CTRL_VEL_COMMAND=1
uint32 CTRL_ATT_COMMAND=2
uint32 CTRL_MISSION_LOAD_COMMAND=3
uint32 CTRL_MISSION_END_COMMAND=4
uint32 CTRL_TAKEOF_COMMAND=5
uint32 CTRL_LANDING_COMMAND=6
uint32 CTRL_HOVER_COMMAND=7
uint32 CTRL_ARM_COMMAND=8

uint32 command_type

# For POS param1 2 3 is x y z * 10000 
# 4 is yaw*10000 if yaw =666666, then use last yawsp
# 567 is vel feedforward

# For VEL param1 2 3 is x y z * 10000 
# 4 is yaw*10000 if yaw =666666, then use last yawsp

# For ATT 
# param1 2 3 4 is roll pitch yaw vz * 10000 
# 5 (>0 use thrust else z is velz)
# 6 (>0 use yaw else yawrate) 
# For TAKEoff param 1 is takeoff height * 10000
# For arm param = 0 is disarm param>0 is arm
# For mission param1-7 is  mission id

int32 param1
int32 param2
int32 param3
int32 param4
int32 param5
int32 param6
int32 param7
int32 param8
```

## License
You can use this software freely. But if this crash your drone, no body will help you.
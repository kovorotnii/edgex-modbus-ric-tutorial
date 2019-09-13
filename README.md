## edgex-modbus-ric-tutorial

### Prerequisites

 - Docker and Docker-compose shoud be installed.
 
 - Customize [configuration.toml](./configuration.toml) and [another.modbus.profile.yml](./another.modbus.profile.yml) according your device.
 
 - Use [docker-compose.yml](./docker-compose.yml) for launching Edgex services.

### First of all download modbus emulator for simulating registers.
 - http://modbuspal.sourceforge.net/

### Launch emulator. Then add a slave.

![Adding slave](./gifs/add-slave-1.gif)

### Add registers to slave device.
 #### Add a holding register
 - We will add a holding register with address 12
 
![Adding holding register](./gifs/added-holding-register-2.gif)

  #### Add two coils.
 - We will add two coils with addresses: 1 and 15. In field "Name" you can add names for variables.
 
 ![Adding cois 1 and 15](./gifs/added-coils-3.gif)
 
  #### Run slave
  - The modbus emulator can be available at `pc-ip-address:502`
  
 ![Running slave](./gifs/running-slave-4.gif)
 
  #### Create model
  
  ![Creating model](./gifs/create-model-5.gif)
  
  #### Create commands for controlling Switches. 
   - SwitchA is a coil register with address: 1. SwitchB is a coil register with address: 15. Values can be 0 or 1.
   - For setting 1, in the field "Payload", set `{"SwitchA": "true"}`. For setting 0, set `{"SwitchA": "fasle"}`
   - This way you also can create controll command for SwitchB. Don't forget to change name!
  ![Creating command for SwitchA](./gifs/create-switchA-6.gif)
  
  #### Create command for getting state of both switches.
  
  ![Creating command for getting switches states](./gifs/get-switch-state-7.gif)
  
  
  #### 
  
 

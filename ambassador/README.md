# Ambassador 
## Ambassador is a meshtastic module that will send a direct message to newly discovered nodes
### Goals
* Autonomous operation: After initial configuration the ambassador functionality should run without requiring user interaction, phone connectivity, or external processes. 
* Easy to configure: Setup and change of ambassador message text should not require code/recompile
* Not spammy: Ambassador messages will only be sent once and via direct message to avoid annoying channel members
* Non-dedicated: Ambassador will be an added feature and will not prevent the normal use of the node

### Approach  
Ambassador was created as a module that listens for text messages and initiates the **"Exchange User Information"** process.  
This process is necessary to obtain the public encryption key for a node. Once the encryption key is obtained we can DM a node.  
When the public encryption key for a node is obtained and saved in nodedb we send the Ambassador message.   

Amabassador message text is retreived from the first message in the **Canned Messages** module.  
`Hello <node shortname>,` is prepended to the canned message

### Code
The code is located in my forked meshtastic firmware repo under the branch [ambassador](https://github.com/ascendr/firmware/tree/ambassador)`

### Builds/Binaries
I've compiled [firmware](./firmware/) based on `2.7.15.567b8ea beta` that can be uploaded via the [Meshtastic Web Flasher](https://flasher.meshtastic.org/) 
     

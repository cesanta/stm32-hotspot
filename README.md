# STM32 Mongoose TCP/IP

This repository contains example projects for Mongoose TCP/IP stack
integration for various STM32 development boards. Every board has
two projects:

```text
BOARD-NAME/
          make/       <--- a minimal, pure CMSIS implementation
          cubemx/     <--- CubeMX / vscode implementation
```

Each project demonstrates the same core functionality:
- Professional Web UI dashboard (LED control + OTA firmware update)
- MQTT-based remote device control and OTA updates

<center>
  <img src="screenshot.webp" alt="Mongoose Wizard dashboard" width="75%"/>
</center>

### make

The `make` project is the most minimal bare-metal implementation.

- Uses only Mongoose and CMSIS headers  
- No external frameworks or vendor libraries  
- Includes lightweight `hal.c` / `hal.h` implemented directly on top of CMSIS  

Best suited for:
- understanding low-level integration
- production firmware with full control over the stack

### cubemx

The `cubemx` project provides STM32CubeMX-based setup.

- Includes a `.ioc` configuration file  
- Comes with integration instructions in README  

Workflow:
1. Open the `.ioc` file in STM32CubeMX  
2. Generate a project (VS Code, CubeIDE, or any IDE)  
3. Follow the README to integrate Mongoose  

Best suited for:
- rapid setup using STM32 tools  
- developers familiar with CubeMX ecosystem  


## Web UI and customization

Projects are built using the Mongoose Visual  
[Web UI Builder](https://mongoose.ws/wizard/)

It is easy to alter its functionality and build a production firmware -
just load the `mongoose/mongoose_wizard.json` in the Web UI builder
and start altering it.

No frontend or network programming skills are required.

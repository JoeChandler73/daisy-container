<h1 align="center">Daisy Dev Container</h1>

This is a dev conatiner for getting started with Daisy.

Before starting read the official [Getting started page](https://daisy.audio/tutorials/cpp-dev-env/)!

This dev container will set up a containerised vscode developemnt environment with the necessary build tools installed and the DaisyExamples git repository cloned and libraries build.

This avoid you having to install the embeded C++ tools on your host machine.

## Getting Started

### Pre-requisites

<ul>
    <li>Install Docker</li>
    <li>Install VSCode (Visual Studio Code)
    <li>Install the 'Dev Containers' vscode extension</li>
</ul>

You must have Docker installed. Currently this dev container will only work on Linux with native Docker. This is because Docker Desktop and Docker on Windows / Mac use Virtual Machines which do not allow access to the hosts USB devices.

### Getting the Source

Clone this repo

```sh
git clone https://github.com/JoeChandler73/daisy-container
```

### Creating the Daisy Development Container

Open the checked out folder in vscode and when prompted choose 'Reopen in continer'.

This will take quite a while first time as the full container has to be built, tools installed, Daisy code cloned and libraries built.

### Compiling the Blink Example

```sh
cd DaisyExamples/seed/Blink
make
```

### Flashing Blink to the Daisy

Put Daisy into bootloader mode by holding the BOOT button down, and then pressing the RESET button. Once you release the RESET button, you can also let go of the BOOT button. 

Lastly flash the firmware using

```sh
cd DaisyExamples/seed/Blink
make program-dfu
```

### Next Steps

Help me make this dev container better!
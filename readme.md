# OS Modification - Deploy Processor Exceptions/Interrupts

## Overview
A custom embedded operating system kernel for STM32F446RE microcontroller featuring processor exception handling, interrupt management, and multi-threading support.

## Project Structure

```
src/
├── kern/                      # Kernel core
│   ├── arch/                  # Architecture-specific code
│   │   ├── cm4/              # ARM Cortex-M4 support
│   │   └── stm32f446re/      # STM32F446RE specific implementation
│   │       ├── dev/          # Device drivers (clock, GPIO, timer, USART)
│   │       ├── sys/          # System initialization and startup
│   │       └── linker/       # Linker script
│   ├── dev/                   # Device support (seven segment display)
│   ├── include/              # Kernel headers
│   ├── kmain/                # Main entry point
│   ├── lib/                   # Kernel libraries (math, stdio, string, time)
│   ├── syscall/              # System call interface
│   └── thread/               # Threading/scheduling support
│
├── userland/                  # User space
│   ├── include/              # User-facing headers (times, unistd)
│   └── utils/                # User utilities
│
└── compile/                   # Build system
    ├── Makefile
    ├── mapfiles/
    ├── object/
    └── target/
```

## Key Features

- **Exception Handling** - Processor exception handling for ARM Cortex-M4
- **Interrupt Management** - Interrupt handling and prioritization
- **Multi-Threading** - Thread scheduling and context switching
- **Device Drivers** - Support for clock, GPIO, timer, and USART
- **System Calls** - System call interface for user programs
- **Standard Libraries** - Kernel math, stdio, string, and time libraries
- **Seven Segment Display** - Device driver for 7-segment displays

## Hardware Target

- **Microcontroller**: STM32F446RE (ARM Cortex-M4)
- **Architecture**: ARM Cortex-M4

## Building

```bash
cd src/compile
make
```

The build process generates:
- Object files in `object/`
- Target binary in `target/duos`

## Components

### Kernel Core Libraries
- `kmath.c` - Mathematical functions
- `kstdio.c` - Standard I/O functions
- `kstring.c` - String manipulation
- `kfloat.c` - Floating-point operations
- `ktimes.c` - Time management
- `kunistd.c` - POSIX-like functions

### Device Drivers
- `clock.c` - Clock configuration
- `gpio.c` - GPIO control
- `timer.c` - Timer functionality
- `usart.c` - Serial communication

### System Features
- `syscall.c` - System call dispatcher
- `thread.c` - Thread management
- `sys_init.c` - System initialization

## Testing

Test programs are available in:
- `src/kern/lib/testprog/test_interrupt.c` - Interrupt testing

## Documentation

Additional documentation is available in:
- [src/doc/Readme.txt](src/doc/Readme.txt)

## Build Artifacts

After compilation, the following artifacts are generated:
- **Binary**: `src/compile/target/duos` - Main kernel binary
- **Object Files**: `src/compile/object/` - Compiled object files
- **Map Files**: `src/compile/mapfiles/` - Linker map files

## License

MIT License

Copyright (c) 2026

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.

## Author

Mehedi Hasan Sakib, csedu : 28 batch

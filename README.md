## Project Milestones

The goal of this project is to develop a Slow Control supervisory module for the FIT detector (ALICE, CERN). The board, based on a Raspberry Pi Pico, is responsible for cooling the electronics, monitoring the electromagnetic field, and communicating with the superior control system.

### 1. Hardware & PCB Design (Deadline: End of November)

* [ ] Design the circuit schematic (Pico, MAX232, fan transistors/controllers, probe connector).
* [ ] Add I2C bus buffers/protections dedicated to the 1-meter cable length.
* [ ] Design the printed circuit board (PCB routing).
* [ ] Generate Gerber files and order the PCBs from a manufacturer.

### 2. RS232 & Software Skeleton (Deadline: Early December)

* [ ] Initialize the repository and configure the environment (MicroPython).
* [ ] Test communication via UART (Sockat)
* [ ] Integrate with the serial device server (MOXA) and test data transmission.

### 3. EMF Sensor & I2C (Deadline: Mid-December)

* [ ] Establish communication with the electromagnetic field sensor via I2C (short cable).
* [ ] Test I2C stability on the final 1-meter cable (adjust pull-up resistors and lower the clock to e.g., 50kHz if necessary or use I2C buffer like P82B715).
* [ ] Parse sensor readings into a data format compatible with RS232 frames.

### 4. Fan Control & Assembly (Deadline: End of December)

* [ ] Assemble and solder components onto the final PCB.
* [ ] Develop software for fan speed control (PWM signal).
* [ ] Develop software for fan RPM counting (Tacho signal / GPIO interrupts).
* [ ] Implement fail-safe logic: automatically generate an RS232 alarm in case of a cooling failure.

### 5. Final Integration & Testing (Deadline: January)

* [ ] Combine all modules into a single, non-blocking main loop (handling fans, sensor, and RS232 simultaneously).
* [ ] Enable the Hardware Watchdog Timer (automatic reset in case of a software freeze).
* [ ] Perform system stress tests (e.g., 48 hours of continuous operation under load).
* [ ] Complete the API documentation and board pinout description.

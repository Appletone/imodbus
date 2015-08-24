Objective of this project is to implement:


**1. Core: Modbus ASCII/RTU protocol implementation portable library Core in C++.**

Library should provide:

  * Message classes for request/response messages, conversion from raw byte stream and to raw byte stream (Modbus RTU and ModBus ASCII).

  * 4-table Memory convenience classes for simplified implementation of slave devices.

  * Utility functions (LSB2MSB, MSB2LSB, byte2asciihex, etc).

_When using core library as in 1 above, application developer should only focus on its GUI interface and communication handlers (serial, tcp/ip) & event dispaching. He or she should use Core which implement actual Modbus PDU._

**2. Comm: Modbus ASCII/RTU communication engine/library**

A set of classes implemented as a multi-threaded application which utilize Appl Mac OS X technologies to pool serial or TCP/IP ports, get received Modbus messages and dispatch them to the registered listeners (GUI, log, rdbms, etc), as well as being used to send outgoing messages. Error handling, diagnostics for serial are handled on this level.

_Application developer would use this component and/or 1 to abstract low-level needs of Modbus communication and just focus its efforts on application development and data processing._


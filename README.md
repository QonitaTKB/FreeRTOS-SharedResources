Exercise 5 – Demonstrate access contention problems
when using shared resources in a multitasking system.

This project demonstrates how FreeRTOS is used to manage multiple tasks accessing shared resources in a multitasking system. In this implementation, LEDs serve as activity indicators for each task and highlight conflicts in accessing shared resources.
Diagram Task:

Required Hardware:

STM32F401CCU6
LEDs

Required Software:

STM32CubeIDE
FreeRTOS

How It Works:

Initialization and Task Scheduling:

The program starts the FreeRTOS kernel to manage the execution of multiple threads.
Tasks have different priorities to reflect system requirements.
Mutual Exclusion (Shared Resource Management):

The GreenTask and RedTask alternate in accessing the StartFlag variable.
Access to the variable is protected to prevent simultaneous access by both tasks.
If access fails (when the shared resource is in use), the yellow LED lights up as an indicator of a conflict.
Conflict Access Indicator:

If the critical section is removed, access conflicts to the shared resource occur more frequently, causing the yellow LED to light up more often.
LED Behavior Cycles:

Normal Case:
The green and red LEDs light up alternately, indicating conflict-free access to the shared resource.
Conflict Case:
If the critical section is not correctly implemented, the yellow LED lights up, indicating access conflicts.

LED Behavior:

Green LED: Lights up when the GreenTask accesses the shared resource.
Red LED: Lights up when the RedTask accesses the shared resource.
Yellow LED: Lights up when a conflict occurs during access to the shared resource.

Hardware Overview:

Demo Video:

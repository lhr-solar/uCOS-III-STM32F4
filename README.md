# RTOS

This system uses the uC/OS - III RTOS from Micrium. The full reference manual can be found [here](https://www.analog.com/media/en/dsp-documentation/software-manuals/Micrium-uCOS-III-UsersManual.pdf)

## Setup

This system currently uses the **STM32F4xx** port.

### Setup for STM32F4xx
*Documentation to be updated when this has been tested*

# Development

Every thread in uC/OS - III is called a **task**, and every task is created using the ```OSTaskCreate()``` method. All required arguments for that function can be found in the reference manual linked at the top of this document.

### Basic Task Requirements
1. The first task created must call ```CPU_Init()``` and ```OS_CPU_SysTickInit()```
2. Every task's body must be enclosed in a ```while``` loop
3. Every task's body must include a function call to one of the following services:
    - ```OSFlagPend()```
    - ```OSMutexPend()```
    - ```OSQPend()```
    - ```OSSemPend()```
    - ```OSTimeDly()```
    - ```OSTimeDlyHMSM()```
    - ```OSTaskQPend()```
    - ```OSTaskSemPend()```
    - ```OSTaskSuspend()```
    - ```OSTaskDel()```

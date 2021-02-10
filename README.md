# TMS570_free_RTOS_blinky
This is an example code helps to use TMS570 to do blink or 0 output and 1 output

please follow these steps:

/*In HALCOGEN*/ 
Step 1:

go -> creat project -> select your microcontroller

Step 2:

Configure driver code generation:
•Enable GIO driver
•Disable others

Navigate: -> TMS570LSxx /RM4 -> Driver Enable

Step 3:

Configure Interrupt handling:
•Enable SVC
•Enter FreeRTOS SVC handler name 'vPortSWI'

Navigate: -> TMS570LSxx /RM4 -> Interrupts

Step 4:

Configure VIM RAM:
•Enter FreeRTOS Timer Tick handler name 'vPortPreemptiveTick' at offset 0x0000000C
•Enter SSI handler name 'vPortYeildWithinAPI ' at offset 0x00000058

Navigate: -> TMS570LSxx /RM4 -> VIM RAM

Step 5:

Configure Vectored Interrupt Module Channels:
•Enable VIM Channel 2
•Map VIM Channel 2 to IRQ
•Enable VIM Channel 21
•Map VIM Channel 21 to IRQ

Navigate: -> TMS570LSxx /RM4 -> VIM Channel 0-31

Step 6:

Configure OS timer tick to 1 ms:
•Enter Tick Rate of 1000

Navigate: -> OS -> General

Step 7:

Generate code

Navigate: -> File -> Generate Code

/*In CODE COMPOSER STUDIO*/ 

Step 8:

Navigate: -> File -> NEW -> CCS project 
then in the window Navigate: -> target -> TMS570LS04x 
Navigate: -> Connection -> texas instruments XDS100v2 USB Debug probe 

Step 7:

in project properties
Navigate: -> include option -> add include file from the code we generate in HALCOGEN
Navigate: -> advanced option -> language -> change it to c99
Navigate: -> Debug -> Flash option -> erase option -> neccessry only


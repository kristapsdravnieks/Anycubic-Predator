# Anycubic-Predator
 Files and notes on thinkering with my Anycubic Predator 3d Printer


# Files
You can find Marlin 2.0.7 source code in ***Marlin-2.0.7_Stock_Board*** directory.

Precompiled marlin firmware files are in ***Compiled Marlin bin*** directory.
Currently I have 3 files, for stock hardware, I have changed stock titan clone extruder with BMG clone extruder, for that I had to invert extruder motor direction and change steps/mm from 400 to 415. last one I have enabled linear adwance feature.


# Flashing the board
Process of flashing the board can be found here:
https://www.youtube.com/watch?v=g2cAJXle6t0&t=18s&ab_channel=SlavaN


STM32 Flasher:
https://www.youtube.com/redirect?redir_token=QUFFLUhqa0lCTVUtNVJQWGVuVGdINmFxZWd5MWlvSGFxUXxBQ3Jtc0ttQ2hCZG5VN2ZNTVBIQ1ZhcWQ0eTJyU255ZjhqNHNJb3l2OW5tV3BEVGNNZEE3NnhYNzF2LUN1TzJNekM3Y2NqRk1jUlJSR2Y1RXAtM3pVWFN5RHNIOGc3WFF0RnA0OE1QSXlXOUJUdzZsTWNpT0xkbw%3D%3D&q=https%3A%2F%2Fwww.st.com%2Fen%2Fdevelopment-tools%2Fflasher-stm32.html&v=g2cAJXle6t0&event=video_description


Info on how to edit and compile Marlin:

https://marlinfw.org/docs/basics/install_platformio_vscode.html



# First run
Before starting your first print Your printer has to be calibrated.
Start with attaching your leveling probe (it is good idea to stick folded piece of paper or some plastic shim between nozzle and probe, to make probe sit tight and imposible to move during calibration) and go to Configuration / Delta Calibration / Auto Calibration menu on the LCD menu.
Store settings after calibration process is compleded.



## Fine tuning delta height.
Logic behind Delta calibration, home to max pos, send effector down towards bed at known steps/mm until brobe triggers, z0 is homing pos minus delta height, delta height equals distance traveled to trigger point + height of probe. If your nozzle is too close to bed after calibration and your probe offset in config menu is -16.20mm change it to -16.10mm and nozzle will rise by 0.1mm, if it is too far away change probe offset in negative direction eg. -16.30 will bring the nozzle closer. 

# Unified Bed Leveling
After initial Delta calibration is completed, go to Motion / Unified Bed Leveling / and Activate UBL, then go to Step by Step UBL / Build Cold mesh.


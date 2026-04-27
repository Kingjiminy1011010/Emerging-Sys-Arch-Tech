# Emerging-Sys-Arch-Tech

Lab Questions
1.	Why does the loop that processes the LED blinking need to run in a separate thread?
a.	The blinking loop runs in a separate thread so it doesn't block the main program. This allows the script to continuously transmit Morse code while simultaneously listening for real-time input from the button. 
2.	What is the purpose of returning to the off state after each completed state action?
a.	 Returning to the off state provides a consistent "neutral" baseline for the hardware. It ensures that all LEDs are explicitly turned off before the state machine initiates the next timed dot, dash, or pause event.
3.	How could you integrate serial communications to facilitate changing the messages available to the program?
a.	 You could use a library like pyserial to create a listener that monitors the Raspberry Pi's serial port for new text. When a new string is received, the script would update the message1 or message2 variables, which the transmit loop would then process into Morse code.
4.	How could you use the 16x2 display to provide debugging information to the user when they don’t have access to the application console?
a.	The updateScreen method can be used to output internal data like the current state name (e.g., "State: dot"), the current character being processed, or error codes. This provides a physical visual log for the user to troubleshoot the system without needing a monitor or SSH connection.

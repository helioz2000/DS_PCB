# Bilge Pump Alarm
## Functional Description
The purpose of this bilge pump control is to provide an audible and visual alarm to the operator when the automatic bilge pump is triggered by it's own water sensor.

The alarm circuit monitors the current flow through the blige pump at all times. The measured idle current of the pump is <100mA. When the pump starts and the current rises above 300mA the alarm circuit activates teh buzzer and the indicator light.

The operator will then acknowledge the alarm by changing the selector from the ARMED to the OFF position. The alarm will then silence the buzzer but the indicator light stays on while blige pump curretn flow is above 300mA.

Once the bilge pump stops (<300mA) the indicator light will go off.

If the selector is not in the armed position the operator will have to switch to ARMED and the to OFF to silence the buzzer.

The alarm will trigger regardless of the switch position (could be OFF).

If the alarm is not acknowledged it will continue until reset, even after the bilge pump stops. This is to alert operators, upon returning, that the bilge pump did run.

- The bilge pump can not be switched off (safety).
- The bilge pump can be operated via the TEST poition on the selector switch. 


## Design Considerations

### Driver Transistors:
The SS8050 is capable of 1.5A and has hfe 120-400, VBE is 1.2V.

The expected load is 40mA for the buzzer and 80mA for the indicator light.

A base resistor of 4K7 will allow Ib of 810uA x 120 = 97mA load current.

### Current Sensor:
The 0R1 resistor provides 31mV for 310mA current flow in the bilge pump. At bilge pump current of 3.5A the voltage drop on the resistor is 350mV and the the power loss is 1.2W which will leave the 5W well within it's operating range.

### Voltage Divider:
brings the 12-15V signal from the selector switch within 4-5V range for atTiny85.

### Filter Capacitors:
100nF, 1uF, 10uF caps provide filtering.
The 47R+100nF low pass filter removes any RF signals from the analog signal 

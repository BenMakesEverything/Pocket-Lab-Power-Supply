# Frequently Asked Questions

## Q: Does this design include a Battery Management System (BMS)?

A: No, you MUST use this PCB in conjunction with a battery pack that includes a BMS to prevent damage.

## Q: What is the maximum output voltage?

A: Short Answer: 20V. 

Long Answer: Theoretical max allowed by the regulator is 22V. However I have it capped at 20V in software. Due to the nature of the compensation system on the chip, it falls slightly short of 22V even when set to that, so I soft-limited it.

## Q: What is the maximum current it can supply?

A: Software limited to 5A. Theoretical max is 6.35, but the system was not designed for high-current loads. (In fact, 5A is probably too high for extended use at higher voltages). I advise against powering anything beyond about 50 Watts.

## Q: Can it supply power via the USBC port?

A: No, the USB C port is for charging only.

## Q: Can it charge while being used/powering something?

A: Yes (if the load is less than the charging current)

## Q: What is the battery life?

A: That depends on what you are powering! Capacity is 4500mAh.

## Q: What happens when the battery drains down to its minimum level?

A: the BQ25792 chip will cut off battery drain before it goes below 12V (3V per cell). This will cause the device to simply not power on.

## Q: Can the firmware be modified?

A: Yes! It is simply written in Arduino.

## Q: How do I program the ATTiny?

A: UPDI. If the battery is connected, all you need to do is connect the UPDI pin through a resistor to an Arudino that has the UPDI programmer flashed to it, as well as the ground pin of the PCB to the arduino's ground pin.

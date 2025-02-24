# VHDL Counter Race Condition

This repository demonstrates a subtle race condition in a simple VHDL counter. The `buggy_counter.vhd` file contains the buggy code, while `buggy_counter_fixed.vhd` provides a corrected version.

**Bug Description:**
The original counter has a potential race condition where the reset signal and counter increment might interact unpredictably, especially if the reset is deasserted at the same clock cycle the counter hits its maximum value. This leads to a momentary incorrect output.

**Solution:**
The solution involves synchronizing the reset and counter update via an intermediate signal, ensuring that the reset takes effect only after the counter's value is stable for that clock cycle.
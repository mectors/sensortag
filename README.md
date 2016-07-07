# Sensortag
BTLE TI Sensortag snapcraft yaml file to buils a sensortag snap

# Build and run the snap
Clone or dowload the repo to a Linux device running snapcraft 2.x and build the snap with snapcraft. Run the snap installing on a snapd capable system. More info at http://snapcraft.io/create/

# USage and examples

Use hcitool lescan to get the sensortag address:

~$ sudo hcitool lescan
LE Scan ...
A0:E6:F8:B6:E7:86 (unknown)
A0:E6:F8:B6:E7:86 CC2650 SensorTag


Call sensortag with --all to get reading from all the sensors and -n 2 to get two readings, do specify the address of your sensortag device.

```
~$ sudo sensortag --all -n 1 A0:E6:F8:B6:E7:86
Connecting to A0:E6:F8:B6:E7:86
('Temp: ', (26.125, 19.375))
('Humidity: ', (26.31622314453125, 48.590087890625))
('Barometer: ', (26.55, 1018.32))
('Accelerometer: ', (0.049560546875, 0.060791015625, -0.94140625))
('Magnetometer: ', (-20.841514041514042, 21.44126984126984, -31.337240537240536))
('Gyroscope: ', (1.13677978515625, 0.091552734375, -2.54058837890625))
('Light: ', 7.640000000000001)
```

This snap works with the TI CC2650 multi-standard SensorTag.

- Temp: Ambient and Object temperature (Cs)
- Humidity: Ambient temperature (Cs) and relative humidity (%)
- Barometer: Temperature (Cs) and Air Pressure (hPa)
- Accelerometer: X,Y,Z axis with a default period for the data is one second. (Gs)
- Magnetometer: Strength of a magnetic field in the three axis (uT)
- Gyroscope: Rotational motion (degrees/second)
- Light: Ambient Light (Lux)

# zephyr-application

I. Download Zephyr-Application
============

It's recommend to create your own python virtualenv
```
$: mkdir zephyryproject
$: cd zephyryproject
$: python3 -m venv zephyr-venv
$: source zephyr-venv/bin/activate
```
To get the module you need to have `west` installed and use it as:

Install the `west` utility:

```
$: pip install west
```
Download the Zephyr-Application sources (Including Zephyr master revision):

```
$: west init -m https://github.com/jorisoffouga/zephyr-application.git
$: west update
```
At the end of the commands you have every metadata you need to start work with.

II. Install dependancies
=======

See [Zephyr Documentation](https://docs.zephyrproject.org/latest/getting_started/index.html)

# Weather Station

In group with Offouga Joris, I had to get the data from the sensor BME280.
We decided to use Zephyr thanks to its ease of use. First, we had to create an overlay to make the program compatible with STM32 discovery. You can find the source files in `samples/weather_station/src`
After declaring two struct corresponding to UART communication and sensor, you enter in a while loop where you get all data from the BME280 with the line :
```
sensor_sample_fetch(bme280);
```
After that, you have to get the data you want with the `sensor_channel_get()` fonction.

I send all data through UART with a specific communication protocol we made with Joris, you can find it in the `send_data()` fonction. 

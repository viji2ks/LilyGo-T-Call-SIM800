
## Flash Micropython to ESP32

The recommended version of Micropython for this board is
[`MicroPython_LoBo_esp32_psram_all.zip`](https://github.com/loboris/MicroPython_ESP32_psRAM_LoBo/raw/master/MicroPython_BUILD/firmware/MicroPython_LoBo_esp32_psram_all.zip)
from [LoBo prebuilt packages](https://github.com/loboris/MicroPython_ESP32_psRAM_LoBo/tree/master/MicroPython_BUILD/firmware).

Flash using [`esptool`](https://github.com/espressif/esptool):
```sh
esptool --chip esp32 --port PORT --baud BAUD --before default_reset --after no_reset write_flash -z --flash_mode dio --flash_freq 40m --flash_size detect 0x1000 bootloader/bootloader.bin 0xf000 phy_init_data.bin 0x10000 MicroPython.bin 0x8000 partitions_mpy.bin
```
Or you can use any other GUI/tools and specify address for each file.

## Upload the example

Using [`ampy`](https://github.com/pycampers/ampy):

```sh
ampy put main.py
```
if ur using micropython in thonny

in thonny repl looks like this
>>>
then open the main.py
in line code 32 update APN like below with ur apn 
GSM_APN = 'airtelgprs.com'  # Your APN is airtelgprs.com 

then run main.py using > sybol and see results like below displays

Connecting to GSM...

I (215236) [PPPOS CLIENT]: Connect requested.
I (215236) [PPPOS CLIENT]: GSM initialization start
I (215836) [PPPOS CLIENT]: AT COMMAND: [AT..]
I (215859) [PPPOS CLIENT]: AT RESPONSE: [..OK..]
I (215959) [PPPOS CLIENT]: AT COMMAND: [ATZ..]
I (215982) [PPPOS CLIENT]: AT RESPONSE: [..OK..]
I (216082) [PPPOS CLIENT]: AT COMMAND: [ATE0..]
I (216105) [PPPOS CLIENT]: AT RESPONSE: [ATE0...OK..]
I (216205) [PPPOS CLIENT]: AT COMMAND: [AT+CFUN=1..]
I (216228) [PPPOS CLIENT]: AT RESPONSE: [..OK..]
I (217328) [PPPOS CLIENT]: AT COMMAND: [AT+CPIN?..]
I (217353) [PPPOS CLIENT]: AT RESPONSE: [..+CPIN: READY....OK..]
I (217453) [PPPOS CLIENT]: AT COMMAND: [AT+CREG?..]
I (217477) [PPPOS CLIENT]: AT RESPONSE: [..+CREG: 0,1....OK..]
I (217577) [PPPOS CLIENT]: AT COMMAND: [AT+CNMI=0,0,0,0,0..]
I (217601) [PPPOS CLIENT]: AT RESPONSE: [..OK..]
I (217701) [PPPOS CLIENT]: AT COMMAND: [AT+CGDCONT=1,"IP","airtelgprs.com"..]
I (217731) [PPPOS CLIENT]: AT RESPONSE: [..OK..]
I (217831) [PPPOS CLIENT]: AT COMMAND: [AT+CGDATA="PPP",1..]
I (217856) [PPPOS CLIENT]: AT RESPONSE: [..CONNECT..]
I (218856) [PPPOS CLIENT]: GSM initialized.
I (219600) [PPPOS CLIENT]: status_cb: Connected
I (219600) [PPPOS CLIENT]:    ipaddr    = 100.76.32.177
I (219600) [PPPOS CLIENT]:    gateway   = 192.168.254.254
I (219606) [PPPOS CLIENT]:    netmask   = 255.255.255.255
I (219612) [PPPOS CLIENT]:    ip6addr   = ::
IP: 100.X.X.177
Connected !
b'HTTP/1.1 200 OK\r\nServer: nginx/1.10.3\r\nDate: Mon, 19 Apr 2021 15:57:22 GMT\r\nContent-Type: text/html; charset=utf-8\r\nTransfer-Encoding: chunked\r\nConnection: keep-alive\r\nVary: Accept-Encoding\r\nX-Frame-Options: SAMEORIGIN\r\nStrict-Transport-Security: max-age=15768000\r\n\r\n1fa8\r\n<!DOCTYPE html>\n\n\n\n<html lang="en">\n  <head>\n    <meta charset="utf-8">\n    <meta http-equiv="X-UA-Compatible" content="IE=edge">\n    <meta name="viewport" content="width=device-width, initial-scale=1">\n    <!-- The above 3 meta tags *must* come first in the head -->\n\n    <link rel="icon" href="/static/img/favicon.ico">\n\n    <title>MicroPython - Python for microcontrollers</title>\n\n    <link href="/static/bootstrap-3.3.7-dist/css/bootstrap.min.css" rel="stylesheet">\n\n    <link href="/static/css/style.css?v=2" rel="stylesheet">\n\n    \n  <link href="/static/css/pygments.css" rel="stylesheet">\n  <link href="/static/home/css/style.css" rel="stylesheet">\n\n\n    <link href="https://fonts.googleapis.com/css?family=Open+Sans:40'

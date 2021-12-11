# ESP32-S2-Break-Out
ESP32-S2 Break Out Board rev. 0.9

Some Notes on using the ESP32-S2 Break Out Board rev. 0.9

Two mistakes were made on rev. 0.9 but the module is useable. The problems are in uploading.  Uploads happen fine - but then as soon as you open the Serial Port to view debug data - Nothing happens.  You have to remove the DTR and RTS connections.  This means it is easier to use jumpers between the USB-Serial adapter, be it my CP2104, a regular CP2102 or FTDI.

Mistake #1 - I got the header for my CP2104 turned around - so you have to plug it in from the bottom of the ESP32-S2 break out board, if you want the convenience of this header - otherwise solder in the headers of your choice and use jumpers... ( NOTE - the DTR and RTS pins are transposed on the CP2104 header. )

Mistake #2 - I did not include the "auto upload" circuitry...  this is what causes the board to stop working as soon as the serial port is opened after uploading if either the DTR or RTS lines are connected.

WorkArounds:

#1 - use jumpers or plug in the CP2104 from the bottom and upload OTA firmware - as I do ( you will have to push the 'Flash' button)..<br>
#2 - use jumpers to connect my CP2104 or a regular CP2102 or FTDI<br>
  ---  my CP2104 - <b>SET jumper for 3V3</b> operation!! reverse the DTR and RTS lines and upload will be automatic.<br>
  ---  CP2102    - connect 3V3 to + and DTR to RTS, Gnd to Gnd, TXD to >Rx and RXD to <Tx.<br>
  ---  FTDI      - <b>set jumper for 3V3</b> operation - connect Vcc to + .... rest same as CP2102 above.<br>
  ---  in all 3 case you will need to push the 'Flash' button to upload and then disconnect the DTR ( and RTS ) lines to use a Serial Monitor.<br>
    
I have yet to try the ESP32-S2 specific features of the IDE such as uploading using the native USB and debugging via a different Serial Port.<br>

...... TBD    ......

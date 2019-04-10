# b4j-library-jtm1637
jTM1637 is an open source B4J Library to control the 4 digits LED display TM1637 connected to Raspberry Pi.

The library supports digits 0 - 9 and the clock point ":" and is based upon the jPi4J library.
The file attached contains the library source, library jar&xml, examples basic functions, clock, Raspberry Pi CPU temperature.

The library is written in B4J (requires v5.80 or higher) making use of Inline Java (requires Java 8 update 40 or higher).
[B4J](https://www.b4x.com/b4j.html) development tool for cross platform desktop, server and IoT solutions by [Anywhere Software](https://www.b4x.com). 

__Library Version:__ v1.0 (20170228)

## Files
* jTM1637.zip contains the library and sample projects
* jTM1637.pdf manual 

## Prototype with Clock Example
```
Wiring used:
TM1637 DIO Pin = wPi 28 = Raspberry Pi Pin 38
TM1637 CLK Pin = wPi 29 = Raspberry Pi Pin 40
```

## Example showing the Library Methods
```
Sub Process_Globals
    Private tm As TM1637
    Private pinData As Byte = 28    'DIO
    Private pinClock As Byte = 29    'CLK
End Sub

Sub AppStart (Args() As String)
    tm.Initialize(pinData, pinClock)
    Tests
    StartMessageLoop
End Sub

Sub Tests
    tm.Brightness = tm.BRIGHTDARKEST
    tm.ShowDoublePoint = False
    tm.DisplayDigits(Array As Int(1,9,5,8))
    tm.Delay(2000)
    tm.Brightness = tm.BRIGHTHIGHEST
    tm.Clear
    tm.DisplayDigit(1,1)
    tm.Delay(1000)
    tm.DisplayDigit(2,9)
    tm.Delay(1000)
    tm.DisplayDigit(3,5)
    tm.Delay(1000)
    tm.DisplayDigit(4,8)
End Sub
```

## Author
Robert W.B. Linn
 
## Licence Copyright (C) 2017 Robert W.B. Linn
This program is free software: you can redistribute it and/or modify it under the terms of the GNU General Public License as published by the Free Software Foundation, either version 3 of the License, or (at your option) any later version. This program is distributed in the hope that it will be useful, but WITHOUT ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS for A PARTICULAR PURPOSE.  See the GNU General Public License for more details. You should have received a copy of the GNU General Public License along with the samples.  If not, see [GNU Licenses](http://www.gnu.org/licenses/).

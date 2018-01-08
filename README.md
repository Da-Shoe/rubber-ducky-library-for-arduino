# Rubber Ducky library for Arduino

An Arduino library that allows you to use a cheap Arduino (Leonardo) as a Rubber Ducky 

## Device used

Arduino Leonardo Mini with USB adapter

![Arduino leonardo mini with USB adapter](https://raw.githubusercontent.com/luisbraganca/rubber-ducky-library-for-arduino/master/Photos/device.jpg)

## What's a Rubber Ducky?

"The USB Rubber Ducky is a keystroke injection tool disguised as a generic flash drive. Computers recognize it as a regular keyboard and accept pre-programmed keystroke payloads at over 1000 words per minute." Taken from [Hak5 Gear](https://hakshop.com/products/usb-rubber-ducky-deluxe).

## Why using an Arduino instead of a Rubber Ducky?

### Price

Rubber Ducky: $44.99

Arduino Leonardo Mini: $4.22 (no it's not a mistake)

### Customization

Rubber Ducky: ???

Arduino Leonardo Mini: Switches, Memory Card, Wifi, etc...

If you're interested in building one from scratch with switches and such, take a look at [Seytonic's youtube channel](https://www.youtube.com/channel/UCW6xlqxSY3gGur4PkGPEUeA), or you can simply buy a pre-built one from [his store](https://shop.malduino.com).

## Technical details

This library allows you to use an Arduino Leonardo as a [Rubber Ducky](https://hakshop.com/products/usb-rubber-ducky-deluxe) with pre-built methods to simplify your keyboard script coding.

### Methods

#### Utilities

```arduino
/**
 * Prepares the virtual keyboard.
 * This method should be the first instruction on the setup code block.
 */
void init();
```

```arduino
/**
 * Ends the virtual keyboard.
 * This method should be the last instruction on the setup code block.
 */
void finish();
```

```arduino
/**
 * For the keyboard functions to work they need a small
 * delay between them. If you notice there's some bugs
 * when running your arduino, try using different delay values
 * on this function.
 */
void rdDelay();
```

```arduino
/**
 * A longer delay (5 times the regular delay).
 */
void rdLongerDelay();
```

```arduino
/**
 * Used to type non-alphanumeric keys.
 */
void rdTypeKey(uint8_t key);
```

#### Library

```arduino
/**
 * Runs a program.
 * Example: "notepad" starts notepad, "calc" starts the calculator.
 */
void rdRun(String program);
```

```arduino
/**
 * Takes a screenshot.
 */
void rdPrintScreen();
```

```arduino
/**
 * Opens the JavaScript console on a browser.
 */
void rdOpenJavascriptConsole();
```

```arduino
/**
 * Hides a window:
 * Basically it drags a window to the lowest it can be
 * and then repositions the cursor.
 */
void rdHideWindow();
```

```arduino
/**
 * Same as Win + D
 */
void rdShowDesktop();
```

```arduino
/**
 * Same as Ctrl + V
 */
void rdPaste();
```

```arduino
/**
 * Same as Ctrl + X
 */
void rdCut();
```

```arduino
/**
 * Same as Ctrl + C
 */
void rdCopy();
```

```arduino
/**
 * Same as Gui + (the received key)
 */
void rdGuiCombination(uint8_t c);
```

```arduino
/**
 * Same as Alt + (the received key)
 */
void rdAltCombination(uint8_t c);
```

```arduino
/**
 * Same as Ctrl + (the received key)
 */
void rdCtrlCombination(uint8_t c);
```

```arduino
/**
 * Same as Shift + (the received key).
 */
void rdShiftCombination(uint8_t c);
```

```arduino
/**
 * Same as (Received hold key) + (target key).
 */
void rdKeyCombination(uint8_t holdKey, uint8_t targetKey);
```

```arduino
/**
 * Same as (Received hold key 1) + (received hold key 2) + (target key).
 */
void rdKeyCombination(uint8_t holdKey1, uint8_t holdKey2, uint8_t targetKey);
```

```arduino
/**
 * Same as above but with one more hold key.
 */
void rdKeyCombination(uint8_t holdKey1, uint8_t holdKey2, uint8_t holdKey3, uint8_t targetKey);
```

```arduino
/**
 * Opens the command prompt without admin rights.
 */
void rdOpenCommandPrompt();
```

```arduino
/**
 * Opens the command prompt, if the "admin" parameter
 * has a "true value", it opens a command prompt
 * with admin rights. Or without admin rights otherwise.
 */
void rdOpenCommandPrompt(boolean admin);
```

```arduino
/**
 * Accepts the windows smart screen to grant admin permissions.
 */
void rdAcceptWindowsSmartScreen();
```

## Getting started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

It's highly recommended that you edit this project using Arduino IDE that can be downloaded [here](https://www.arduino.cc/en/Main/Software) since it was developed using that same tool.
After installing, run the IDE and go to Tools > Board and select "Arduino Leonardo" or other compatible board (read the notes for further information).

## Notes

The [Arduino website](https://www.arduino.cc/reference/en/language/functions/usb/keyboard) suggests that only three boards are supported for the Mouse and Keyboard library:

* Leonardo (CPU: ATmega32u4)

* Micro (CPU: ATmega32u4)

* Due (CPU: Atmel SAM3X8E ARM Cortex-M3)

## Authors

* **Luís Bragança Silva** - *Initial work*

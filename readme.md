# [Number to words](https://github.com/savoirfairelinux/num2words) for NVDA

Author: Mateo Cedillo

## Introduction:

I was inspired to make this little add-on, because some people use speech synthesizers like `ETI-Eloquence` which has some flaws when it comes to number processing, even if they are separated and confuses the user saying both numbers separated by spaces as if it were a decimal point. 

This add-on improves the reading of numbers to words for these cases, it supports larger numbers and, in addition, the library supports many languages.

## comparison of results between original and converted speech input

This comparison table demonstrates the differences between number processing on a synthesizer and num2words processing.

The following comparison has been evaluated using the [IBMTTS driver](https://github.com/davidacm/NVDA-IBMTTS-Driver) for NVDA.


### Using long numbers:

| Language | Original input | Output | Converted input |
|---|---|---|---|
| Spanish | 921359131290481307233416326 | nueve dos ún tres cinco nueve ún tres ún dos nueve cero cuatro ocho ún tres cero siete dos tres tres cuatro ún seis tres dos seis | novecientos veintiuno cuatrillones trescientos cincuenta y nueve mil ciento treinta y uno trillones doscientos noventa mil cuatrocientos ochenta y uno billones trescientos siete mil doscientos treinta y tres millones cuatrocientos dieciséis mil trescientos veintiséis |
| English | 921359131290481307233416326 | nine two one three five nine one three one two nine zero four eight one three zero seven two three three four one six three two six | nine hundred and twenty-one septillion, three hundred and fifty-nine sextillion, one hundred and thirty-one quintillion, two hundred and ninety quadrillion, four hundred and eighty-one trillion, three hundred and seven billion, two hundred and thirty-three million, four hundred and sixteen thousand, three hundred and twenty-six |

### Using spaces as separators (only in Spanish):

* Original input: 12 499
* Output: doce mil cuatrocientos noventa y nueve
*  Converted input: doce cuatrocientos noventa y nueve

## Usage:

This addon has two ways of using numbers to words:

* Real time mode: as long as NVDA is talking and there's a text containing numbers anywhere in it, the conversion will display its result and be transmitted by speech. This applies to any speech synthesizer you use.
* Manual mode: you can write numbers or text, and/or numbers at the same time, interacting through a dialog box to do so. The dialog has:
	* A checkbox to convert to ordinal.
	* If the ordinal box is not checked, a combo box will appear to choose the conversion mode. There are four conversion modes and they are as follows:
		* Ordinal
		* Ordinal number
		* Year
		* Currency
	* An input box to write your entry.
	* A convert button. By pressing this button, you will be shown a message box with the final result.
	* A cancel button: Exits the conversion dialog.

### Input gestures:

* Toggle numbers to words (or real time mode): (Unassigned gesture for now to avoid interference with other add-ons).
* Open conversion dialog (manual mode): alt+shift+NVDA+n.
* More features soon!

#### Important notes:

* As the library supports many languages, keep in mind that the conversion is done in the language of your speech synthesizer. This will even apply when you change the language of your synthesizer.
* The num2words library can convert up to 27 consecutive numbers. If the text is longer than 27 numbers, it will let you know with a beep and a speech message.
* Currently, speaking a converted number with the cursor isn't implemented and as a consequence will spell out the converted number.
* Decimal numbers to words conversion support is being implemented, as there are conflicts with some native Python libraries installed in NVDA.

## Compile this add-on:

Note: this add-on depends on a submodule, so:

1. cd to this repo: `cd num2words_nvda`
2. Type `git submodule init` and `git submodule update` in the console to clone the num2words library repository that is set as a module.
3. If there are no errors, `scons` command should work correctly.

## Contact:

If you want to help improve this addon, you can send an email to `angelitomateocedillo@gmail.com` or make your contributions on the GitHub repo.

---

# Changelog:

## 0.2

* Now the result from numbers to words is capitalized.
* Updated num2words library to commit `d09862790503a0ec03f3c3ffb2f70e03c41ae2f6`.
* Added conversion modes supported by the num2words library in the manual conversion GUI.

## 0.1

* Initial release. You may find some minor bugs. If so, please let me know.
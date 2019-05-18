# binder_medidas2

## Control de equipos por Python

### Equipos a controlar:
 * [analizador de espectro](https://www.keysight.com/en/pd-817002-pn-N9320A/rf-spectrum-analyzer-9-khz-3-ghz?cc=US&lc=eng)
 * [generador de señal](https://www.keysight.com/en/pdx-x202262-pn-N9310A/rf-signal-generator-9-khz-to-3-ghz?cc=AR&lc=eng)
 * [medidor de potencia](https://www.anritsu.com/en-US/test-measurement/products/ml2487b) y [sensor](https://www.bellnw.com/manufacturer/Anritsu/MA2472D.htm)
___

### instalar dependencias
- pip install -U pyvisa
- pip install -U pyvisa-py
- pip install pyserial
- pip install pyusb
___

### [my binder](https://mybinder.org/v2/gh/ingenieriaam/binder_medidas2/binder_shared)
[![Binder](https://mybinder.org/badge_logo.svg)](https://mybinder.org/v2/gh/ingenieriaam/binder_medidas2/binder_shared?urlpath=https%3A%2F%2Fgithub.com%2Fingenieriaam%2Fbinder_medidas2%2Fblob%2Fmaster%2Fnotebook_init.ipynb)

___

### pasos basicos

Ver si se reconoce al equipo

```py
>>> import visa
>>> rm = visa.ResourceManager()
>>> print(rm.list_resources())
>>> a = rm.list_resources()
>>> print(a[0])
	USB0::6833::2400::DSA8A194601374::0::INSTR
>>> inst = rm.open_resource(a[0])
>>> print(inst.query("*IDN?"))
	Rigol Technologies,DSA815,DSA8A194601374,00.01.18.00.02

```

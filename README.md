Fourier Features Toolkit for Gamera
===================================

The FourierFeatures Toolkit implements a wide variety of Fourier descriptors.
These are useful features for shape recognition. In contrast to ordinary
Fourier descriptors, this toolkit also provides descriptors that work on
broken shapes. 


Purpose
-------

This toolkits provides an implementation of all Fourier descriptors
that were discussed and evaluated in the following paper:

> Dalitz, C., Brandt, C., Goebbels, S., Kolanus, D.:
> "Fourier Descriptors for Broken Shapes." EURASIP Journal on
> Advances in Signal Processing 2013:161, 2013
> https://doi.org/10.1186/1687-6180-2013-161

In this study, the best performing Fourier descriptors were
fdsingle_complex_position for unbroken (connected) shapes, and
fdbroken_a or fdbroken_c for arbitrary (including broken) shapes.


Requirements
------------

This toolkit has been written for the Gamera framework and requires
a working installation of Python 3.x Gamera 4.x installation.
See the Gamera homepage	http://gamera.sourceforge.net/.


Documentation
-------------

For a user's guide and a developer's guide see ``doc/html/index.html``.
For release notes and a revision history see ``CHANGES``.

If you need to generate the HTML docs, you can do so with

    cd doc
    python3 gendoc.py


Installation
------------

See the section "Installation" in 'doc/html/index.html' or 
'doc/src/index.txt'.


Usage
-----

When the toolkit is instaled, you can use it in a python script as follows:

```python
from gamera.core import *  				# import Gamera core
from gamera.toolkits import fourierfeatures		# import fourierfeatures toolkit
from gamera.toolkits.fourierfeatures import broken	# import the 'broken' plugin from fourierfeatures
# from gamera.toolkits.fourierfeatures import single	# import the 'single' plugin from fourierfeatures

# Initialize Gamera
init_gamera()

# Load an image and convert it to one-bit
img = load_image("path/to/your/image.png").to_onebit()

# Apply a Fourier descriptor from the 'broken' plugin
fd = img.fdbroken_a()

# Print the resulting FloatVector
print(fd)
```

Authors
-------

 - Christoph Dalitz, 2013, https://lionel.kr.hsnr.de/~dalitz/
 - Christian Brandt, 2013

Please contact Christoph Dalitz for questions about this toolkit.


Acknowledgements
----------------

Thanks to Fabian Schmitt, who helped fixing some bugs and
to Oskar Waedt for porting this toolkit to Python 3.

License
-------

This toolkit is free software; you can redistribute it and/or modify
it under the terms of the GNU General Public License.

This program is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
file LICENSE for more details.

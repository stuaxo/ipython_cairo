ipython_cairo
=============

Render cairo surfaces and contexts in an ipython notebook.


installation
============

For now this can be installed with

```
%install_ext https://raw.githubusercontent.com/stuaxo/ipython_cairo/master/ipython_cairo.py
```

Once this is a bit more polished it will be added to pypi.


dependencies
============

Pycairo and CairoCFFI are both supported, one of these will need to be installed
in your current python environment.


```
$ pip install cairocffi
````


Will install the latest version of cairocffi.


usage
=====

Enable the extension:

```
%load_ext ipython_cairo
```

Try the following code in an ipython notebook to see surface and
context output.

[ The output should look like this:  http://nbviewer.ipython.org/gist/stuaxo/0f4e1ee9b603c3bc5a6c ]

```
# Example cairo code.
import cairo

width, height = 100, 50


surface = cairo.ImageSurface(cairo.FORMAT_ARGB32, width, height)

cr = cairo.Context(surface)
cr.set_source_rgb(0.7, 0.9, 0.0)
cr.rotate(-45)
cr.rectangle(0, 0, 40, 40)
cr.fill()

# The context will output in the cell
cr
```

```
# surfaces will also output
surface
```





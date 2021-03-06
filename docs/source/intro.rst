
Getting started: 30 seconds with IPywidgets server
==================================================

Let's create a simple widget::

    # example.py

    from ipywidgets import IntSlider, Text, VBox
    s = IntSlider(max=200, value=100)
    t = Text()


    def update_text(change=None):
        t.value = str(float(s.value) ** 2)


    s.observe(update_text, names='value')
    update_text()
    vbox = VBox([s, t])

To serve this, just run the following, in the directory containing ``example.py``:

.. code-block:: bash

   $ ipywidgets-server example:vbox

This will serve the widget on ``http://localhost:8866/``:

.. image:: _images/simple-example.gif

The command line argument, ``example:vbox``, is ``<module name>:<object name>``,
where ``<module name>`` is the name of a Python module that can be imported (for
instance, a file in the current directory, without the ``.py`` extension or a
Python package that is installed in your environment), and ``<object name>`` is
the name of the variable that holds the widget to display.

For information on other command line arguments, run::

    $ ipywidgets-server --help

Installation
============

Install `IPywidgets server` with:

.. code-block:: bash

    $ pip install ipywidgets_server

Currently, `IPywidgets server` only runs on Python 3.6.

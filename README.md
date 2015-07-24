sync_page
================
Overlays `sync_media.py`, to run on all media resources in a page.

Examples
--------------
python sync_page.py "http://127.0.0.1:8000/politics/archive/2015/07/2016-election/384828/"


sync_media_function.py
------------------------
This is sync_media.py, but made callable as a Python function.


metafuncs.py
-----------------
Metafunctions used for generic flow control and function building.


sync_page.py
--------------
This is written in a functional pipeline style, which grafts together a bunch of very small functions. This has a lot of benefits for debugging and refactoring, but it is not commonly used in Python, so I'm a little embarrased to let anyone set it.

If you become determined to read `sync_page.py`, then:
- '>>' means 'Compose the previous function and the next function'. Hence the following are equivalent::
    allfuncs = Chainable(func1) >> func2 >> func3
    # Equivalent
    def allfuncs(*args, **kwargs):
        return func3(func2(func1(*args, **kwargs)))
- The ":: Type" comments at the end of lines refer to the type of output from that line. Useful for keeping track of what's going on in a chain of functions.


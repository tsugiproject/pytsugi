# pytsugi


**Deprecated:** As of November 2018, this effort is deprecated.
We are in the process of developing a new technology / apprach
that will allow Tsugi tools to be built in a wide range of environments
connected to the core of Tsugi using web services wather than through
the database as is done in this approach.

This is an emergent implementation of the Python Tsugi library.

See also the pytsugi-web2py repository for a sample of using this library:

https://github.com/tsugiproject/pytsugi-web2py

If you want to use this:

    pip install pytsugi

Use sudo as necessary.

Developing and Testing Locally
------------------------------

If you want to change source code and develop pytsugi, do the following:

    pip uninstall pytsugi

    git checkout https://github.com/tsugiproject/pytsugi
    cd pytsugi
    python setup.py develop

Usie sudo as necessary.  This sets up a soft link so you can go
a `git pull` in pytsugi and not have to rerun `setup.py`.

Of course if you are using Web2Py (I don't know about other
frameworks) it caches module loads so you need to restart Web2Py
when you change pytsugi code.

To go back to the released version:

    python setup.py develop --uninstall
    pip install pytsugi

Releasing
---------

To release you first must have a pypi account and have permission to upload
a new version.

Also you should tag a release the git repo for the version in `setup.py`
in case you want to go back.

You have to do this once to reserve the name in PyPi - which is already done.

    python setup.py register

Undo developer mode if you were developing (sudo as needed):

    python setup.py develop --uninstall
    rm -r pytsugi.egg-info/

Then package and upload

    python setup.py sdist
    python setup.py sdist upload  (Requires pypi account)

Check on pypi to see if it made it.

    https://pypi.python.org/pypi/pytsugi/

After you do the release, increment the version number in the setup.py file since
you can only do one release per version.  That is the next "working version" until
you send it up to `pypi`.

After you release you might want to switch back to developer mode:

    python setup.py develop

References
----------

* https://ewencp.org/blog/a-brief-introduction-to-packaging-python/



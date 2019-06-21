********************************************************************************
Contributions
********************************************************************************

Bug reports
===========

When `reporting a bug <https://github.com/compas-dev/compas/issues>`_
please include:

* Operating system name and version.
* Any details about your local setup that might be helpful in troubleshooting.
* Detailed steps to reproduce the bug.


Feature requests and feedback
=============================

The best way to send feedback is to file an issue on
`Github <https://github.com/compas-dev/compas/issues>`_.
If you are proposing a feature:

* Explain in detail how it would work.
* Keep the scope as narrow as possible, to make it easier to implement.


Code contributions
==================

We accept code contributions through pull requests. Here we outline a basic workflow on how does one create a fork, install the fork to a virtual environment, invoke tests, and create a pull request. For more detailed developer guides, see :ref:`developer_guide`.

1. Fork `the repository <https://github.com/compas-dev/compas>`_ and clone the fork to a local directory on your computer, for example on your desktop:

::

  $ cd C:\Users\<your user name>\Desktop
  $ git clone https://github.com/<your github account>/compas.git

2. Create a virtual environment using your tool of choice (e.g. ``virtualenv``, ``conda``, etc). We will use ``conda`` as an example in the following guidelines. If the environment is brand new and does not have `compas` dependencies installed, run the following lines after you activate your env:

::

    (compas-dev) conda config --add channels conda-forge
    (compas-dev) conda install COMPAS

See :ref:`getting-started--virtual-environments` for more info on creating conda environment and installing compas.

3. In the Anaconda command prompt, ``cd`` to the directory where you clone the forked repo:

::

    (your-dev-env) cd C:\Users\<your user name>\Desktop

4. Install development dependencies:

::

    $ pip install -r requirements-dev.txt

This will install the forked local repo to your conda envirnment.

5. Make sure all tests pass:

::

    $ invoke test

.. note::

  For compas version ``0.6.2``, not all the tests are passed. In this version, the test results are ``84 passed, 11 xfailed in 4.55 seconds``.

6. Start making your changes to the **master** branch (or branch off of it).

7. After you are done with your development and before you submit a pull request, make sure all tests still pass:

::

    $ invoke test


7. Add yourself to ``AUTHORS.md``.
8. Commit your changes and push your branch to GitHub.
9. Create a `pull request <https://help.github.com/articles/about-pull-requests/>`_ through the GitHub website.


During development, use `pyinvoke <http://docs.pyinvoke.org/>`_ tasks on the
command line to ease recurring operations:

* ``invoke clean``: Clean all generated artifacts.
* ``invoke check``: Run various code and documentation style checks.
* ``invoke docs``: Generate documentation.
* ``invoke test``: Run all tests and checks in one swift command.
* ``invoke``: Show available tasks.

lua-test-42
===========

|Stability Experimental| |Documentation Status|

.. |Stability Experimental| image:: https://img.shields.io/badge/stability-experimental-orange.svg?style=for-the-badge
   :target: https://github.com/jeblad/test-lvl-42/blob/master/STABILITY.md#experimental
   
.. |Documentation Status| image:: https://readthedocs.org/projects/test-lvl-42/badge/?style=for-the-badge&version=latest
   :target: https://test-lvl-42.readthedocs.io/en/latest/?badge=latest

.. role:: bash(code)
   :language: bash

.. role:: python(code)
   :language: python

This is a small project to test documentation of Lua scripts, integration with `the shitty blog <https://jeblad.github.io>`_ and `RTFM <https://lua-test-42.readthedocs.io>`_.

Usage
-----

#. Clone repository

   .. code-block:: bash

	git clone git@github.com:jeblad/whatever.git .

#. Move to development directory

   .. code-block:: bash

	cd whatever

#. Initialize environment and activate

   .. code-block:: bash

	virtualenv sphinxenv
	source activate

#. Install Sphinx

   .. code-block:: bash

	pip install sphinx

#. Create document structure

   .. code-block:: bash

	sphinx-quickstart

   Name of the master document should be set to `index`, and add :python:`master_doc = 'index'` to `conf.py` if necessary.

#. Install a local Sphinx version of ReadTheDocs standard theme (`sphinx-rtd-theme <https://pypi.org/project/sphinx-rtd-theme/>`_)

   .. code-block:: bash

	pip install sphinx_rtd_theme

#. Add the code for using this theme in `conf.py`

   .. code-block:: python

	# on_rtd is whether we are on readthedocs.org
	import os
	on_rtd = os.environ.get('READTHEDOCS', None) == 'True'

	if not on_rtd:  # only import and set the theme if we're building docs locally
		import sphinx_rtd_theme
		html_theme = 'sphinx_rtd_theme'
		html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

	# otherwise, readthedocs.org uses their theme by default, so no need to specify it

#. Install an extension for Lua code (`sphinx-lua <https://pypi.org/project/sphinx-lua/>`_)

   .. code-block:: bash

	pip install sphinx-lua

#. Install recommonmark

   .. code-block:: bash

	pip install recommonmark

#. Build the site by

   .. code-block:: bash

	make html

   or

   .. code-block:: bash

	sphinx-build -t html source build

Notes
-----

* Tutorials
* Topical guides
* Reference material

* `Jacop Kaplan-Moss: What to write <https://jacobian.org/writing/what-to-write/>`_
* `WriteTheDocs: Beginners guide to docs <https://www.writethedocs.org/guide/writing/beginners-guide-to-docs/>`_
* `Steve Losh: Teach don't tell <https://stevelosh.com/blog/2013/09/teach-dont-tell/>`_

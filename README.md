# lua-test-42

1. Clone repository

	```bash
	git clone git@github.com:jeblad/whatever.git .
	```

2. Move to development directory

	```bash
	cd whatever
	```

3. Initialize environment and activate

	```bash
	virtualenv sphinxenv
	source activate
	```

4. Install Sphinx

	```bash
	pip install sphinx
	```

5. Create document structure

	```bash
	sphinx-quickstart
	```

	Name of the master document should be set to `index`, and add `master_doc = 'index'`to `conf.py` if necessary.

5. Install a local Sphinx version of ReadTheDocs standard theme ([sphinx-rtd-theme](https://pypi.org/project/sphinx-rtd-theme/))

	```bash
	pip install sphinx_rtd_theme
	```

6. Add the code for using this theme in `conf.py`

	```python
	# on_rtd is whether we are on readthedocs.org
	import os
	on_rtd = os.environ.get('READTHEDOCS', None) == 'True'

	if not on_rtd:  # only import and set the theme if we're building docs locally
		import sphinx_rtd_theme
		html_theme = 'sphinx_rtd_theme'
		html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

	# otherwise, readthedocs.org uses their theme by default, so no need to specify it
	```

7. Install an extension for Lua code ([sphinx-lua](https://pypi.org/project/sphinx-lua/))

	```bash
	pip install sphinx-lua
	```

8. Install recommonmark

	```bash
	pip install recommonmark
	```

8. Build the site by

	```bash
	make html
	```

	or

	```bash
	sphinx-build -t html source build
	```

#########################################
Sphinx
#########################################

* Language: reStructuredText
* Compiler: Sphinx (Python)
* Deployment: ReadtheDocs (via GitHub)

********************
References
********************
* Sphinx and reStructuredText: `<https://www.sphinx-doc.org/en/master/usage/restructuredtext/basics.html>`_ 。
* Template from ReadtheDocs: `<https://github.com/readthedocs/sphinx_rtd_theme/tree/master/docs>`_
* Template user manual: `<https://sphinx-rtd-theme.readthedocs.io/>`_
* Template configuration: `<https://sphinx-rtd-theme.readthedocs.io/en/stable/configuring.html>`_
* Configuration file: Set ``html_theme_options`` in ``FENGSim/docs/src/conf.py``.

********************
Deployment
********************
* Specify the paths for ``conf.py`` and ``requirements.txt`` in ``FENGSim/docs/.readthedocs.yaml``.
* The ``FENGSim/docs/requirements.txt`` file lists all the packages required by ReadtheDocs. The version ``sphinx-rtd-theme`` must be 3.0.2; otherwsie, the ``version_selector`` option in the ``html_theme_options`` dictionary within ``FENGSim/docs/src/conf.py`` will cause errors.
* In ``FENGSim/docs/Makefile``, specify ``SOURCEDIR`` for the source files (e.g., ``conf.py`` and ``.rst`` files) and ``BUILDDIR`` for the compilation output.
* Specify ``html_logo`` for logo file in ``FENGSim/docs/src/conf.py``.

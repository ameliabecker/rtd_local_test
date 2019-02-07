*****************
Setting up Sphinx
*****************

Easy Sphinx Setup
=================

`ezsphinx`_ 

.. _ezsphinx: https://docs.readthedocs.io/en/latest/intro/getting-started-with-sphinx.html

Sphinx Automatic HTML Updates
=============================

`autogen`_ 

.. _autogen: https://sublime-and-sphinx-guide.readthedocs.io/en/latest/build.html

Add this text to the Makefile:

.. code-block:: python

	SPHINXAUTOBUILD = sphinx-autobuild

	ALLSPHINXLIVEOPTS   = $(ALLSPHINXOPTS) -q \
		-p 0 \
		-H 0.0.0.0 \
		-B \
		--delay 1 \
		-i "*.swp" \
		-i "*.pdf" \
		-i "*.log" \
		-i "*.out" \
		-i "*.toc" \
		-i "*.aux" \
		-i "*.idx" \
		-i "*.ind" \
		-i "*.ilg" \
		-i "*.tex" \
		--watch source

	.PHONY: livehtml
	livehtml:
		$(SPHINXAUTOBUILD) -b html $(ALLSPHINXLIVEOPTS) "$(SOURCEDIR)" "$(BUILDDIR)"
		@echo
		@echo "Build finished. The HTML pages are in $(BUILDDIR)."

use ``ctrl + C`` to stop server
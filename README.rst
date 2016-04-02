Stanza
======

|Master Build Status| |Documentation Status|

Stanza is the Stanford NLP group’s shared repository for Python
infrastructure. The goal of Stanza is not to replace your modeling tools
of choice, but to offer implementations for common patterns useful for
machine learning experiments.

Usage
-----

You can install the package as follows:

::

    git clone git@github.com:stanfordnlp/stanza.git
    cd stanza
    pip install -e .

To use the package, import it in your python code. An example would be:

::

    from stanza.text.vocab import Vocab
    v = Vocab('UNK')

Please see the documentation for more use cases.

Documentation
-------------

Documentation is hosted on Read the Docs at
http://stanford-nlp.readthedocs.org/en/latest/. Stanza is still in early
development. Interfaces and code organization will probably change
substantially over the next few months.

Development Guide
-----------------

To request or discuss additional functionality, please open a GitHub
issue. We greatly appreciate pull requests!

Adding a new module
~~~~~~~~~~~~~~~~~~~

If you are adding a new module, please remember to add it to
``setup.py`` as well as a corresponding ``.rst`` file in the ``docs``
directory.

Tests
~~~~~

Stanza has unit tests as well as longer, integration tests. We asks that
all contributors run the unit tests before submitting pull requests:

.. code:: python

    python setup.py test

Documentation
~~~~~~~~~~~~~

Documentation is generated via
`Sphinx <http://www.sphinx-doc.org/en/stable/>`__ using inline comments.
This means that the docstring in Python double both as interactive
documentation and standalone documentation. This also means that you
must format your docstring in RST. RST is very similar to Markdown.
There are many tutorials on the exact syntax, essentially you only need
to know the function parameter syntax which can be found
`here <http://thomas-cokelaer.info/tutorials/sphinx/rest_syntax.html#auto-document-your-python-code>`__.
You can, of course, look at documentations for existing modules for
guidance as well. A good place to start is the ``text.dataset`` package.

To set up your environment such that you can generate docs locally:

::

    pip install sphinx sphinx-autobuild

If you introduced a new module, please auto-generate the docs:

::

    sphinx-apidoc -F -o docs `pwd`
    cd docs && make
    open _build/html/index.html

You most likely need to manually edit the `rst` file corresponding to your new module.

Road Map
--------

-  common objects used in NLP

   -  [x] a Vocabulary object mapping from strings to integers/vectors

-  tools for running experiments on the NLP cluster

   -  [ ] a function for querying GPU device stats (to aid in selecting
      a GPU on the cluster)
   -  [ ] a tool for plotting training curves from multiple jobs
   -  [ ] a tool for interacting with an already running job via edits
      to a text file

-  [ ] an API for calling CoreNLP

For Stanford NLP members
------------------------

Stanza is not meant to include every research project the group
undertakes. If you have a standalone project that you would like to
share with other people in the group, you can:

-  request your own private repo under the `stanfordnlp GitHub
   account <https://github.com/stanfordnlp>`__.
-  share your code on `CodaLab <https://codalab.stanford.edu/>`__.
-  For targeted questions, ask on `Stanford NLP
   Overflow <http://nlp.stanford.edu/local/qa/>`__ (use the ``stanza``
   tag).

.. |Master Build Status| image:: https://travis-ci.org/stanfordnlp/stanza.svg?branch=master
   :target: https://travis-ci.org/stanfordnlp/stanza
.. |Documentation Status| image:: https://readthedocs.org/projects/stanford-nlp/badge/?version=latest
   :target: http://stanford-nlp.readthedocs.org/en/latest/?badge=latest
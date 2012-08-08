SEP 100 - Citations List
=========================================================

======   ====================
Author   Anthony Scopatz
Status   Draft
======   ====================


Overview
--------
At SciPy 2012, there was a lot of discussion around how to 
legitimize and formalize our activities - especially in the 
eyes of funding agencies.  One mechanism to prove our value, 
to computational science would be to have a visible, searchable 
database of citations.  This would include papers that discuss: 

* Science applications which use Python,
* General purpose packages (NumPy, SciPy, IPython, etc.),
* Domain specific packages, 
* and new methods primarily implemented in any of the above.

Proposal
--------
This proposal aims to develop three resources:

* A plain text bibliography file (in bib, json, or py format),
* A mechanism to transform this file to other standard bibliography formats,
* And a web interface to this file. 

The bibliography file would be a normal file hosted on GitHub.
This will be either a bibtex file (unlikely), a JSON file, or a python
file with a single dictionary. This file could then be able to be added to 
manually by the community  via the pull request mechanism.  Individuals 
publishing with Python could then use this citations file as a reference 
for their own publications.  They would also be asked to submit their 
articles back to this file for posterity.  An example of the format of this
file is as follows::

    {'doi:10.1088/0067-0049/199/1/5': {
        'id': 'doi:10.1088/0067-0049/199/1/5',
        'doi': '10.1088/0067-0049/199/1/5',
        'dependencies': ['cython', 'numpy', 'libpsht', 'wavemoth', 'nose'],
        'version': '0.1-dev'
        },
     'PER-GRA:2007': {
        'id': 'PER-GRA:2007',
        'type': 'article',
        'author': ['Fenando Perez', 'Brian E. Granger'],
        'title': "IPython: a System for Interactive Scientific Computing',
        'journal': 'Comput. Sci. Eng.',
        'volume': 9,
        'number': 3,
        'pages': '21-29',
        'month': 'may',
        'year': 2007,
        'url': "http://ipython.org",
        }
        ...
    }

Functions which transformation this file to other formats would be made available.
This certainly include BibTeX, AMA, and others.  However, it may also include other 
library-based back ends such as Zetero or Mendeley.  Most of the heavy lifting here 
could likely be outsourced to other projects, such as pyzotero.

The web interface to this file would likely be hosted at http://numfocus.org/.
It should be a searchable page similar to the 
`FLASH publication list <http://flash.uchicago.edu/site/publications/flash_pubs.shtml>`_.
This will provide an easy place to refer potential funders to.
After an initial first cut of the web interface, visualizations of the metadata could 
be added.  For example, Individual citations could receive their own pages which may
contain force-directed graph visualizations of the code dependencies.  Author graphs
which link this document to other publications is also possible.


Discussion
----------
Please visit the following threads for more information:

* https://groups.google.com/forum/?fromgroups#!topic/numfocus/S0g1428DX3U
* https://groups.google.com/forum/?fromgroups#!topic/numfocus/GT35Y1uq7ew
* https://groups.google.com/forum/?fromgroups#!topic/numfocus/-tBHj1AT8fA


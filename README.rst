========
PyKrylov
========

PyKrylov is a pure Python package implementing common Krylov methods.


Requirements
============

1. `Python <http://www.python.org>`_ 2.7. I've never tested with Python 3.
2. `NumPy <http://www.scipy.org/NumPy>`_

If you are working under Linux, OS/X or Windows, prebuilt packages are
available. Remember that for efficiency, it is recommended to compile Numpy
against optimized LAPACK and BLAS libraries. Under OS/X efficient
implementations of BLAS and LAPACK are available from Xcode. Specify
``-framework Accelerate`` when installing NumPy.


Krylov Methods
==============

Krylov methods are iterative methods for solving (potentially large)
systems of linear equations

        A x = b

where A is a matrix and x and b are vectors of compatible dimension. Different
Krylov methods are used depending on the properties of the matrix A. Typically,
only matrix-vector products with A are required at each iteration. Some methods
require matrix-vector products with the transpose of A when the latter is not
symmetric. For more information on Krylov methods, see the references below.

PyKrylov does not rely on any particular dense or sparse matrix package because
all matrix-vector products are handled as operators, i.e., the user supplies
a function to perform such products. Similarly, preconditioners are handled as
operators and are not held explicitly. As a result, PyKrylov should be easy to
use with dense Numpy array or matrices and with sparse matrix packages such as
those of `Pysparse <http://pysparse.sf.net>`_ and `Scipy
<http://www.scipy.org>`_.


Installing
==========

Type the usual Distutils stance::

    python setup.py install

To select the install location, use ::

    python setup.py install --prefix=/some/other/place


Documentation
=============

Current documentation can be found at http://dpo.github.com/pykrylov.
PyKrylov documentation is based on the Sphinx system and can be regenerated by::

    cd doc
    make html
    make latex
    cd build/latex
    make all-pdf

The html documentation is in doc/build/html and the PDF manual is in
doc/build/latex. Obviously, if you don't have a working LaTeX distribution such
as TeXLive, only issue the first two commands.


Bugs, Comments, Feature Requests
================================

Please send bugs, comments, feature requests, test cases, chocolate and coffee
via Github Issues or the `Lighthouse PyKrylov page
<http://pykrylov.lighthouseapp.com/projects/21441-pykrylov>`_.


References
==========

* J.W. Demmel, *Applied Numerical Linear Algebra*, SIAM, Philadelphia, 1997.
* A. Greenbaum, *Iterative Methods for Solving Linear Systems*,
  number 17 in *Frontiers in Applied Mathematics*, SIAM, Philadelphia, 1997.
* C.T. Kelley, *Iterative Methods for Linear and Nonlinear Equations*,
  number 16 in *Frontiers in Applied Mathematics*, SIAM, Philadelphia, 1995.
* Y. Saad, *Iterative Methods for Sparse Linear Systems*, 2nd ed., SIAM,
  Philadelphia, 2003.
* R. Barrett, M. Berry, T.F. Chan, J. Demmel, J.M. Donato,
  J. Dongarra, V. Eijkhout, R. Pozo, C. Romine and
  H. Van der Vorst, *Templates for the Solution of Linear Systems:
  Building Blocks for Iterative Methods*, SIAM, Philadelphia, 1993.

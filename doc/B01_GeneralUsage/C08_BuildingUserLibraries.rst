


.. |newpage| raw:: latex

   \newpage





|newpage|


Building user libraries and documenting them
============================================================

XlCalcNet allows the user to build libraries of user defined functions in Python and C\#, which can be used from spreadsheet formulas in Microsoft Excel and LibreOffice Calc, as well as from Python scripts and C\# programs. The user libraries can be documented using Sphinx, which allows to build documentation in html and pdf format.

Basic examples of building a user library are provided for Python in the subfolders of the ``A03_UserlibPython`` folder, and for C\# in the subfolders of the ``A04_UserlibCSharp`` folder, which can be used as templates for building more complex user libraries.

The user library can be documented using Sphinx, which allows to build documentation in html and pdf format. The documentation can be built starting with examples in the ``A05_UserlibDocs`` folder, which can be used as a template for documenting more complex user libraries. The documentation for the already included starting user libraray is part of this manual. It is written in the same style as this manual and comprises two parts: User library: numerical; and User library: graphics. 

Examples of using the user libraries are provided in the subfolders of the ``A06_UserlibExamplesPython`` folder for Python and in the ``A07_UserlibExamplesCSharp`` folder for C\#.



Building a library of user defined Python functions
------------------------------------------------------------------------------------


In Python, the user library is built in the subfolders of the ``A03_UserlibPython`` folder, which contains Python modules with the user defined functions. The modules can be imported in Python scripts and used from spreadsheet formulas in Microsoft Excel and LibreOffice Calc. The functions are decribed here.

These functions can be tested  in the subfolders of the ``A06_UserlibExamplesPython`` folder.






Building a library of user defined functions in C\#
----------------------------------------------------------------------------------------

The library of user defined functions in C\# is built in form of 2 dynamic link libraries (DLLs), which are called ``UserFixedPrecNet.dll`` and ``UserArbPrecNet.dll`` and which are written into the Binary Output Folder. These functions are described here.

There is also a third DLL called ``UserMpPrecNet.dll``, which is used by the Python user library. This DLL is also written into the Binary Output Folder.




.. _rst_user_documentation: 

Sphinx: building documentation for software with Python (html and pdf)
----------------------------------------------------------------------------------

This manual is written in reStructuredText (reST) format, which is a lightweight markup language. The manual is built using Sphinx, which is a tool that makes it easy to create intelligent and beautiful documentation for Python projects (or other software projects). Sphinx uses reStructuredText as its markup language and can generate output in various formats, including HTML and PDF.

To build the documentation, you need to have Sphinx installed. You can install Sphinx using pip: 

``python -m pip install sphinx``

See also: https://www.sphinx-doc.org/en/master/


You also need to install 3 additional Sphinx extensions that are used in this manual: the Sphinx Book Theme, the Sphinx Copybutton extension, and the Sphinx Contrib Bibtex extension. They can be installed using pip:

``python -m pip install sphinx-book-theme``

``python -m pip install sphinx-copybutton``

``python -m pip install sphinxcontrib-bibtex``


With these packages installed, you can build the documentation of the user library by opening in the Tiny IDE the file ``A05_UserlibDocs\B01_Lib01\_static\builddoc.py``. In the Tiny IDE main menu, click on ``Run``. The HTML documentation will then be built in the subfolder ``html`` in the ``XlCalcNetIDE`` folder in the AppData\Local folder. If built has succeded, the documentation will be opened automatically. The html documentation can be viewed by opening the file ``index.html`` in a web browser. 









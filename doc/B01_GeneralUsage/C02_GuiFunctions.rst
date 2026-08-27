


.. |newpage| raw:: latex

   \newpage





|newpage|


General and user interface functions
==================================================




.. _rst_ClientServer: 

Starting and calling the socket server
--------------------------------------------------------------------------------

A running socket server is critical for the use of XlCalcNet from Microsoft Excel.


.. image:: ../_static/SocketServer.png
    :width: 50 %
    :align: center

The socket server can be startet in various ways:


Starting the socketserver from the TinyIDE or GalleryOfPlots application
...................................................................................

Explain use of menu.




Starting the socketserver from the Navigator dialog in Excel
...................................................................................

Explain use of dialog.




Starting the socketserver programmatically from Python
...................................................................................


.. method:: gui.socketserver()

    Describe the start of the socket server

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.socketserver()




Calling the socketserver from Python
.............................................

Describe calling the socketserver from Python


.. code-block:: pycon

    >>> import socket

    >>> host = socket.gethostname()
    >>> port = 11958  # socket server port number
    >>> client_socket = socket.socket()  # instantiate
    >>> client_socket.connect((host, port))  # connect to the server

    >>> client_socket.send(SnippetToSend.encode())  # send message
    >>> DataReceived = client_socket.recv(1024).decode()  # receive response
    >>> print('Received from server: ' + DataReceived)  # show in terminal

    >>> client_socket.close()  # close the connection


Calling the socketserver from C\#
.............................................

Describe calling the socketserver from C\#




Source code
.............................................


The Python source code for the socketserver can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/Addin/NET48/Bin/socketspy.py

The C\# source code for the socket client can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/ClientServer






|newpage|



.. _rst_OutputMonitor: 

Starting the output monitor
--------------------------------------------------------------------------------


.. method:: gui.outputmonitor()

    Describe the start of the output monitor


    .. image:: ../_static/DataMo0nitor.png
       :width: 50 %
       :align: center


    The Python source code for starting the output monitor can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ShowOutputMonitor.py


    The C\# source code for the output monitor can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/OutputMonitor




    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.outputmonitor()






|newpage|

.. _rst_TinyIde: 


Starting an additional instance of the IDE
--------------------------------------------------------------------------------


.. method:: gui.tinyide()

    Describe the start an additional instance of the IDE

    .. image:: ../_static/TinyIDE.png
       :width: 50 %
       :align: center



    The Python source code for starting the IDE can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ShowEditor.py


    The C\# source code for the IDE can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/TinyEditor



    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.tinyide(x)






|newpage|

.. _rst_GalleryOfPlots: 


Starting the gallery of plots
--------------------------------------------------------------------------------


.. method:: gui.plot2d()

    Describe the start of the gallery of plots

    .. image:: ../_static/GalleryOfPlots.png
       :width: 50 %
       :align: center



    The Python source code for starting the IDE can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ShowEditor.py

    The C\# source code for the gallery of plots can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/TinyPlot2D




    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.plot2d(x)






|newpage|

.. _rst_Wpf3D: 


Starting the interactive 3D wpf plots
--------------------------------------------------------------------------------


.. method:: gui.plot3d()

    Describe the start of Interactive 3D Wpf plots

    .. image:: ../_static/Wpf3D.png
       :width: 50 %
       :align: center


    The Python source code for starting the interactive 3D wpf plots can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ShowPlot3d.py

    The C\# source code for the gallery of plots can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/TinyPlot3D


    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.plot3d(x)





|newpage|

.. _rst_DataViewer: 


Starting the data viewer
--------------------------------------------------------------------------------


.. method:: gui.dataviewer()

    Describe the start of data viewer

    .. image:: ../_static/DataViewer.png
       :width: 50 %
       :align: center



    The Python source code for starting the data viewer can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ShowDataViewer.py

    The C\# source code for the data viewer can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/DataViewer



    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.dataviewer(x)





|newpage|


Starting IDLE
--------------------------------------------------------------------------------


.. method:: gui.idle()

    Describe the setup and use of IDLE

    .. image:: ../_static/IDLE.png
       :width: 50 %
       :align: center



    The Python source code for starting the data viewer can be found here: https://github.com/duhadler/XlCalcNet/blob/master/xlcalcnet/ShowDataViewer.py

    The C\# source code for the data viewer can be found here: https://github.com/duhadler/XlCalcNet/tree/master/xlcalcnet/Addin/NET48/Source/DataViewer

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.idle(x)



|newpage|


Functions related to folders
--------------------------------------------------------------------------------

There are several functions related to folders


.. method:: gui.get_local_appdata()

    Return the current user's local Application Data folder


    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.get_local_appdata()




.. method:: gui.get_local_appdata_xlcalcnet()

    Return the current user's local AppData/XlCalcNetIDE folder

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.get_local_appdata_xlcalcnet()



.. method:: gui.get_my_documents()

    Return the current user's local AppData/XlCalcNetIDE folder

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.get_my_documents()



|newpage|


Information about installation status of supporting python packages
--------------------------------------------------------------------------------


.. method:: gui.info()

    Support for Matplotlib output in a separate process

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.info()


.. method:: gui.has_gpm()

    Returns True if gmpy2 is installed

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.has_gpm()


.. method:: gui.has_apm()

    Returns True if python-flint is installed

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.has_apm()



.. method:: gui.has_xlcalcnet2()

    Returns True if xlcalcnet2 is installed

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.has_xlcalcnet2()






|newpage|

Information about context lists, and setting global precision
--------------------------------------------------------------------------------


.. property:: gui.ctxlistreal

    Returns a list of all available numerical contexts supporting real data types

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.ctxlistreal



.. property:: gui.ctxlistcplx

    Returns a list of all available numerical contexts supporting complex data types

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.ctxlistcomplex



.. method:: gui.setdps(dps)

    Sets the decimal precision for all multiprecision data types

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> dps = 50
        >>> gui.setdps(dps)




|newpage|

Support for running interactive Matplotlib output in a separate process
--------------------------------------------------------------------------------

There is support for Matplotlib output in a separate process

See also: https://matplotlib.org/stable/users/explain/figure/interactive.html#default-ui

.. property:: gui.plot(fig, file, fname)

    Support for Matplotlib output in a separate process

    .. code-block:: pycon

        >>> from xlcalcnet import gui
        >>> gui.plot(fig, file, fname)



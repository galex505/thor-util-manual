Download Packages (download)
============================

Using the “download” flag you can download any of the scanner packages
for Windows, Linux and macOS.

.. note:: 
   THOR Util can not download THOR binaries and signatures whose license was obtained through the ASGARD Management Center.
   Use the Management Center API for this. Only the Nextron Customer Portal is accepted as a license source.

This option is especially useful in cases in which you have to download
the updates on an Internet connected machine and bring them to a system
without Internet access.

.. code:: doscon
 
   C:\thor>thor-util.exe download -t thor10-win

THOR TechPreview Version
------------------------

To download the TechPreview version, use the following command line flag.

.. code:: doscon
   
   C:\thor>thor-util.exe download -t thor10-win --techpreview

You can find more information on the TechPreview version
`here <https://www.nextron-systems.com/2020/08/31/introduction-thor-techpreview/>`_.

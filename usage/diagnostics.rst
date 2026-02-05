.. role:: raw-html-m2r(raw)
   :format: html

Diagnostics
===========

If THOR does not behave like it should, e.g. using more resources than
you expected, taking a prolonged time to finish a scan, or unexpectedly
exits with a generic error, you can create a diagnostics pack for our
support to help you troubleshoot the issue.

This can be done using THOR Util's diagnostics command.

.. code:: doscon
 
   C:\thor>thor-util.exe help diagnostics

   Create diagnostics pack

   Usage:
     thor-util diagnostics [flags]

   Flags:
     -h, --help        help for diagnostics
     --output string   File to write diagnostics pack to (default "[...]\diagnostics.zip")
     --run             Rerun last THOR scan with debug logging before collecting diagnostics pack

By default the ``diagnostics.zip`` file is put in THOR's working
directory. The location is printed on the commandline in the end
of the data collection and can be changed using the ``--output`` flag.

Get diagnostics of a running THOR scan
--------------------------------------

The preferred method of collecting THOR diagnostics is
to run THOR Util's diagnostics command directly when
the issue is occurring. This generally means if you
suspect THOR is stuck during a scan, high memory or
CPU usage by THOR, or anything else during its runtime.

.. code:: doscon

   C:\thor>thor-util.exe diagnostics

Get diagnostics of a finished THOR scan
---------------------------------------

If the THOR run is already finished or stopped unexpectedly,
you can also use the diagnostics command above, with the
biggest downside that only a reduced - and mostly not helpful -
amount of information can be collected. In those cases, you
should use the ``--run`` flag to rerun the last THOR scan.
Using the ``--run`` flag is the preferred method if THOR
is exiting unexpectedly/randomly.

.. code:: doscon

   C:\thor>thor-util.exe diagnostics --run

What data is being collected
----------------------------

The below data is being collected by THOR Util's
diagnostics function:

- A log of THOR Utils diagnostics run itself
- Go Profiles for CPU, Memory and Go routines, see: https://go.dev/blog/pprof
- THOR's running configuration parameters
- A process list of all running processes on the machine. (this
  helps tremendously identifying processes that might disturb
  THOR, like an AV/EDR)
- A process dump of the running THOR instance
- The progress state of the running THOR instance
- A dump of the THOR DB
- The latest THOR log

.. hint::
   Critical or personal information may be present in the THOR log, THOR DB dump,
   running process list, in the THOR process dump, and in the progress report
   (working item details like path information). The profiles may allow insights
   on what type of data is being scanned but does not contain any specific pieces
   of data.

The diagnostics pack is only used to debug the issues you are facing with
THOR and will be deleted from our systems once the root cause of your issue
was found.
What is this ?
--------------

This is a [Drupal] module to allow people using [SecondLife]
or [OpenSimulator] to build inworld scripts linked to Drupal.

History
-------

This original module was first designed by Khalid Baheyeldin and hosted here :
https://drupal.org/project/secondlife
(Copyright 2007 Khalid Baheyeldin http://2bits.com)

This module was not maintained so another module was made on [github]
by ssm2017 Binder.
The Drupal 7 version was made with the help of Lennard
(see : https://github.com/Lennard/slfw )

Differences between this version and the old one :

  - allow to add a lot of allowed ips
  - allow the lsl script to choose the arguments separator instead of ":"
  - allow to use another xmlrpc host instead of the linden one
  - php 5.3 compatible
  - better proxy management
  - another name

Later, ssm2017 Binder decided to completely change the name
and replace the word "SecondLife" with "metaverse" but someone else took this word.
So now, this new module version is called Metaverse Framework.

Installation
------------

To install this module, Upload or copy the the entire metaverse_framework directory
and all its contents to your modules directory.

Configuration
-------------

To enable this module do the following:

Go to Administer -> Site Building -> Modules, and enable metaverse framework.

Developing for SecondLife and OpenSimulator
-------------------------------------------

Second Life objects are written in a language called llscript (Linden Lab Script).
For more on how to use this language, refer to this wiki:
http://wiki.secondlife.com/wiki/LSL_Portal

The Second Life framework module interfaces with Second Life using the llHTTPRequest function.

See details here:
http://wiki.secondlife.com/wiki/LlHTTPRequest

In order to write a Drupal application that interfaces with SecondLife or OpenSimulator,
you need to create a new module. See the sltest module in the samples directory for an example.

The app is the application name, and is also the module name. The cmd is a command
that your module/app must handle. The args vary from one cmd to the other.

The $sl object contains the inworld info you need to know, such as region,
location in the grid, user name, user key, ...etc. The $args is an array that
is passed from the llScript to you.

Debugging
---------
A test client emulator script is provided, called metaverse_framework_client.php. It is designed
to run from the command line, and takes two arguments: the server name, and
the handler.

    $ php metaverse_framework_client.php localhost /metaverse-framework

Modify the app and cmd array to the application you are developing. The app
will be your module name, and /metaverse-framework should remain the same.

A variable called metaverse_framework_debug can be set in your settings.php in the $conf
array. Set it to a path writable to your web server to see what is going on
between your web server and your SecondLife / OpenSimulator object.

Authors
-------
  - Khalid Baheyeldin (http://2bits.com)
  - Lennard (https://github.com/Lennard)
  - ssm2017 Binder (http://ssm2017.com)

[Drupal]: http://drupal.org
[SecondLife]: http://secondlife.com
[OpenSimulator]: http://opensimulator.org
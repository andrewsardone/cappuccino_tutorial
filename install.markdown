Installation
=============

This tutorial will only focus on the 0.7b branch and onward.

Grab the Source
----------------------

First, make sure you have the necessary tools:

*	[Rubygems](http://rubygems.org/) version >= 1.3.1: `gem --version`
	*	rake version >= 0.8.3
	*	plist gem version >= 3.0.0: `sudo gem install plist`
*	[Java 1.5](http://www.java.com/)
*	A *nix machine (not a real requirement, but you'll have to refer to the official documentation for Windows help)

Then, grab the code from [GitHub](http://github.com/280north/cappuccino/)

	$ git clone git://github.com/280north/cappuccino.git && cd cappuccino
	$ git checkout -b 0.7b origin/0.7b
	
Build and Install
-----------------

	$ rake release
	$ rake install

Now you have all of your Objective-J and Cappuccino tools installed

	$ ls -l /usr/local/share/objj/bin/
	total 80
	-rwxr-xr-x  1 root  wheel    bake
	-rwxr-xr-x  1 root  wheel    blend
	-rwxr-xr-x  1 root  wheel    capp
	-rwxr-xr-x  1 root  wheel    cplutil
	-rwxr-xr-x  1 root  wheel    nib2cib
	-rwxr-xr-x  1 root  wheel    objj
	-rwxr-xr-x  1 root  wheel    objjc
	-rwxr-xr-x  1 root  wheel    ojtest
	-rwxr-xr-x  1 root  wheel    press
	-rwxr-xr-x  1 root  wheel    steam

Getting Started
===============

### `capp`
via [http://wiki.github.com/280north/cappuccino/capp](http://wiki.github.com/280north/cappuccino/capp)

`capp` is a simple project creation tool for Cappuccino applications.

#### Usage

	$ capp /path/to/your/app [options…]

#### Options
	
*	**-l** By default, a set of the latest Cappuccino frameworks are installed with your project. Specifying the -l flag will instead create a set of symbolic links to your own built frameworks from source.
*	**-t, —template** Specify what project template to use. By default the Application template is chosen. Currently the following templates exist:
	*	*Application* - An empty application with an application controller class.
	*	*ThemeDescriptor* - A special project for creating custom Cappuccino themes.
	*	*NibApplication* - An empty application much like that one created in Application, but with the UI in .xib that can be converted to a cib with nib2cib
*	**-f, —frameworks** Just create the frameworks folder and don’t continue to making an actual project. You can use this with the -l flag to just create a set of symbolic links to the built frameworks from source

#### Example

	$ capp myApp -t NibApplication

Appendix
--------

### Remove the old install

	$ sudo rm /usr/local/bin/bake
	$ sudo rm /usr/local/bin/cplutil
	$ sudo rm /usr/local/bin/nib2cib
	$ sudo rm /usr/local/bin/objj
	$ sudo rm /usr/local/bin/objjc
	$ sudo rm /usr/local/bin/objjtest
	$ sudo rm /usr/local/bin/ojtest
	$ sudo rm /usr/local/bin/press
	$ sudo rm /usr/local/bin/steam
	$ sudo rm -Rf /usr/local/share/objj
	$ rm -Rf $STEAM_BUILD
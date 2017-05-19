.. AutomaticDocument documentation master file, created by
   sphinx-quickstart on Tue Mar 28 12:19:47 2017.
   You can adapt this file completely to your liking, but it should at least
   contain the root `toctree` directive.


  .. toctree::
   :maxdepth: 2

   intro
   strings
   datatypes
   numeric
   

1.Eris Cluster Creation
=======================
Prerequisites
-------------
        1.1.Hardware:	  
			- One AWS instance for root node
			- Two AWS instances for validator nodes
		1.2.Host OS:	  
			- UBUNTU 14.04
		1.3.Software:	  
			- Docker version:   17.03.0-ce	
			- Docker Machine version: 0.10.0 
Sequential Execution Steps        		
--------------------------
        1.1.Install Docker
              Use the following command:-
	           .. image:: _images/title1.png
			   :width: 600px
			   :align: center
			   :height: 500px	
			  Check the installed docker version using the command:-
			  	.. image:: _images/title2.png
			   :width: 600px
			   :align: center
			   :height: 500px	                 		   
		1.2.Install docker machine
		       .. image:: _images/title3.png
			   :width: 600px
			   :align: center
			   :height: 500px	
			  Check the installed docker-machine version using the command:-   
               .. image:: _images/title5.png
			   :width: 600px
			   :align: center
			   :height: 500px
		1.3.Install eris
		       .. image:: _images/title6.png
			   :width: 600px
			   :align: center
			   :height: 500px
	    1.4.Initialize eris
	           .. image:: _images/title7.png
			   :width: 600px
			   :align: center
			   :height: 500px
	    1.5.Start eris keys services 
	           .. image:: _images/title8.png
			   :width: 600px
			   :align: center
			   :height: 500px
	    1.6.Create chain
            - 	In the account-types folder, create specific account based toml files to provide specific permissions for various accounts that will be part of the chain.
			    Eg toml file to be placed in this folder is as follows:
		    -	In the chain-types folder, create the << chain name toml file>>. This file contains the chain specific configuration of accounts that are created via the toml files in the account-types folder.
			    Eg toml file to be placed in this folder is as follows:
			- To create the chain execute the following command

About Read the docs
===================
Read the Docs hosts documentation, making it fully searchable and easy to find. You can import your docs using any major version control system, including Mercurial, Git, Subversion, and Bazaar. We support web hooks so your docs get built when you commit code. There's also support for versioning so you can build docs from tags and branches of your code in your repository.


Write Your Docs
===============
You have two options for formatting your documentation. I am using restructured Text for writing.
	- In reStructuredText (You can learn restructuredText from http://www.sphinx-doc.org/en/stable/rest.html#rst-primer)
	- In Markdown
	
Read the docs using Sphinx
==========================
Install Python
---------------
	
		Most Windows users do not have Python, so we begin with the installation of Python itself. If you have already installed Python, please skip this section.
		Go to https://www.python.org/, the main download site for Python. Look at the left sidebar and under “Quick Links”, click “Windows Installer” to download.

     .. image:: _images/install.png
		:width: 800px
		:align: center
		:height: 500px
		:alt: Install Python

**Note**

	Currently, Python offers two major versions, 2.x and 3.x. Sphinx 1.5 can run under Python 2.7, 3.4, 3.5, 3.6, with the recommended version being 2.7. This chapter assumes you have installed Python 2.7.

Follow the Windows installer for Python.

	 .. image:: _images/next.png
		:width: 800px
		:align: center
		:height: 500px
		:alt: Install Python

| After installation, you better add the Python executable directories to the environment variable PATH in order to run Python and package commands such as sphinx-build easily from the Command Prompt.
	- Right-click the “My Computer” icon and choose “Properties”
	
	- Click the “Environment Variables” button under the “Advanced” tab
	
	- If “Path” (or “PATH”) is already an entry in the “System variables” list, edit it. If it is not present, add a new variable called “PATH”.
	
	Add these paths, separating entries by ”;”:
	  1. C:\Python27 – this folder contains the main Python executable
	  
	  2. C:\Python27\Scripts – this folder will contain executables added by Python packages installed with pip (see below)
	  	This is for Python 2.7. If you use another version of Python or installed to a non-default location, change the digits “27” accordingly.

	- Now run the Command Prompt. After command prompt window appear, type python and Enter. If the Python installation was successful, the installed Python version is printed, and you are greeted by the prompt >>>. Type Ctrl+Z and Enter to quit.

**After installing python we need to install pip command (pip command is required for installing sphinx)**

Install the pip command
-----------------------

	Pip command can use for third party libraries with single command.		
	To install pip, download https://bootstrap.pypa.io/get-pip.py and save it somewhere. After download, invoke the command prompt, 	go to the directory with get-pip.py and run this command:
   	
	Command :- **C:\> python get-pip.py**		 
   
	Now pip command is installed. From there we can go to the Sphinx install.
	
Installing Sphinx with pip
--------------------------

	If you finished the installation of pip, type this line in the command prompt:
	
	|	Command:- C:\> pip install sphinx

	After installation, type sphinx-build -h on the command prompt. If everything worked fine, you will get a Sphinx version number and a list of options for this command.

First Steps with Sphinx
=======================
Setting up the documentation sources
The root directory of a Sphinx collection of reStructuredText document sources is called the source directory. This directory also contains the Sphinx configuration file conf.py, where you can configure all aspects of how Sphinx reads your sources and builds your documentation.

Sphinx comes with a script called sphinx-quickstart that sets up a source directory and creates a default conf.py with the most useful configuration values from a few questions it asks you. To get started, cd into the documentation directory and type:

		Command:- $ sphinx-quickstart

After running this command you will get the following

Please enter values for the following settings(just press Enter to accept a default value, if one is given in brackets).

Here is a list of the default used in this project:

	 .. image:: _images/sphinx.png
		:width: 800px
		:align: center
		:height: 500px
		:alt: Install Sphinix
		
Then you should get:

conf.py
-------

In your doc/source directory is now a python file called conf.py.
This is the file that controls the basics of how sphinx runs when you run a build. Here you can do this like:

	- Change the version/release number by setting the version and release variables.

	- Set the project name and author name.

	- Setup a project logo.

	- Set the default style to sphinx or default. Default is what the standard python docs use.

Adding content
--------------

In Sphinx source files, you can use most features of standard reStructuredText. There are also several features added by Sphinx. For example, you can add cross-file references in a portable way (which works for all output types) using the ref role.

Running the build
-----------------

Now that you have added some files and content, let’s make a first build of the docs. A build is started with the sphinx-build program, called like this:

	Command:- **$ sphinx-build -b html sourcedir builddir**
	
where sourcedir is the source directory, and builddir is the directory in which you want to place the built documentation. The -b option selects a builder; in this example Sphinx will build HTML files.

However, sphinx-quickstart script creates a Makefile and a make.bat which make life even easier for you: with them you only need to run.

	Command:- **$ make html**
	
to build HTML docs in the build directory you chose. Execute make without an argument to see which targets are available.

Installing Theme
================

There are two ways to install theme
	- HTML theming support using sphinx
	- Using Third party
	
HTML theming support using sphinx
---------------------------------
Using an existing theme is easy. If the theme is builtin to Sphinx, you only need to set the html_theme config value. With the html_theme_options config value you can set theme-specific options that change the look and feel. For example, you could have the following in your conf.py:

	html_theme = "classic"
	html_theme_options = {"rightsidebar": "true","relbarbgcolor": "black"}

The theme will look like :

 .. image:: _images/classicTheme.png
		:width: 500
		:align: center
		:height: 500px
		:alt: Install Sphinix theme

That would give you the classic theme, but with a sidebar on the right side and a black background for the relation bar (the bar with the navigation links at the page’s top and bottom).


For more details http://www.sphinx-doc.org/en/stable/theming.html

Using Third party
-----------------

Download the package or add it to your requirements.txt file:
**$ pip install sphinx_rtd_theme**

In your conf.py file search theme and replace it with 

import sphinx_rtd_theme

html_theme = "sphinx_rtd_theme"

html_theme_path = [sphinx_rtd_theme.get_html_theme_path()]

Theme will look like:

.. image:: _images/sphinxtheme.png
		:width: 800px
		:align: center
		:height: 500px
		:alt: Third Party theme

Please Visit the following website for help

- http://www.sphinx-doc.org/en/stable/theming.html
- http://www.sphinx-doc.org/en/stable/
- http://www.sphinx-doc.org/en/stable/tutorial.html
- https://docs.readthedocs.io/en/latest/


* :ref:`search`

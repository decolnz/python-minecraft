===============
 Release Notes
===============

The following changes have been made to the classroom materials over
time. Look for annotated Git tags that match the headings below.

The `full changelog`_ is available on GitHub.

.. _full changelog: https://github.com/CoderDojoTC/python-minecraft/commits/master

Unreleased Changes
==================

* Merged several documentation fixes from `Markus Khouri`_. Thanks
  Markus!

.. _Markus Khouri: https://github.com/markuskhouri

* Began migrating documentation into the Jupyter/IPython
  notebook. This gives the students a more integrated path through the
  course, with less jumping between the static docs and the live
  environment.

* Added some tools to help with course content development:

  * Added a :file:`requirements.txt` file for use in setting up a
    Python environment with the necessary tools.

  * Added a `Fabric`_ script (:file:`fabfile.py`) to help automate
    tasks performed while developing and delivering the course.

.. _Fabric: http://www.fabfile.org/


2015-08-01
==========

* Fixed the lab server controler to work with the latest version of
  gspread, which requires OAuth2.

* Changed the source location where we pull the Canary JAR file. The
  CanaryMod project is going through some changes, and have
  reorganized where files are available on their web server.

* Added a dirty hack to work around a problem that Canary seems to be
  having in determining the UUID of the players listed in ops.txt on
  startup. I've had to put this reactive code in the run-canary.sh
  script to do the job after the player joins the server. A better
  long-term fix is to find the root cause in Canary itself.


2015-05-09
==========

* Upgraded to CanaryMod 1.2.0 (compatible with Minecraft client
  version 1.8), version 1.3 of the RaspberryJuice plugin, and the
  latest python libraries that support them. This brings some new
  programming capabilities, such as being able to have Python code
  receive messages from the game chat.

* Added Martin O'Hanlon's *Minecraft Turtles* so that students can use
  the library and run the examples. This gives students a logo-like
  model for writing programs.

* Upgraded to IPython 3.1.0. This improves the development user
  interface. It also changes the "branding" of the development UI from
  "IPython" to "Jupyter".

* Removed many calls to the obsolete ``server`` module from example
  scripts in the :file:`examples` folder (thanks to Joshua Fasching).

* Fixed a problem where it seemed to rain in Minecraft from time to
  time.


2015-02-21
==========

* Simplify the generated world in the student lab instance to make it
  better for programming projects. Now, the students are placed in a
  "FLAT" world (no terrain, no biomes, no structures, no mobs, etc.),
  and the weather is clear.

* Reorganized the exercises and examples into subfolders, and
  converted all the previous :file:`*.py` files into :file:`*.ipynb`
  files so students can load them directly in IPython.

* Improved our classroom exercises:

  * **Exercise 1:** Reformatted Hello World to be a single code block
    so that it's easier to run, added some hints, and added some extra
    challenges.

  * **Exercise 2:** Took out the TNT Pyramid (which was too big and
    distracting), pointed students to the online help and guided tour,
    wrote more about added the REPL environment.

  * **Exercise 4:** Added a delay so students have a chance to observe
    what is happening as the script runs, added some extra challenges.

  * **Exercise 5:** Added a field of wool so students have something
    that will react to sword strikes.

* Updated some example scripts to work better in our new student
  environment.

* Upgraded to CanaryRaspberryJuice version 1.2. This added methods
  such as getPlayerId(playerName), getDirection(), getRotation(), and
  getPitch(). This also includes version 1.1, which added various
  entity methods.

* Upgraded to IPython version 2.4 in the student lab server
  instance. This is a significant upgrade from the prior version,
  which was IPython 1.3. The main student-visible differences are that
  IPython can now navigate between directories, and the Notebook
  web UI now has separate Edit and Command modes.

* The docs for setting up a local, Vagrant-based lab environment have
  been updated to work much better. It now uses exactly the same
  environment and setup that students get when attending a CoderDojoTC
  event. The solo-server docs and files have been removed.

* The Lab Server Controller now accepts the name of a docker image
  (and version tags) in its configuration file. This makes it possible
  to use different lab images in different environments, which is
  particularly useful in testing a new image before committing to
  using it for a specific CoderDojo event.

* Lots of documentation updates, including new docs for Mentors.

* For people working on updating exercise or example code through the
  IPython notebook interface, launching a student lab instance with
  Vagrant will now copy the local working directory into the folder
  where IPython can edit the files. If there is no Vagrant-provided
  folder, the code will be retrieved from the Git repository specified
  in the :file:`private_config.yaml` file.

  By itself, this copy from Vagrant into the IPython notebook folder
  is a one-way-street. Edits made there will not be visible on the
  Vagrant host (where they can be committed to source code
  control). However, there is also a script installed in the image
  called :command:`sync-notebooks.sh`. It can be run as follows from
  the Vagrant host, and it will invoke Unison to sync up the changes::

    docker exec -it python-minecraft_default_1424407654 sync-notebooks.sh


2015-02-07
==========

* The table of contents and navigation between chapters has been
  improved. Some of the section index pages have been improved.

* Improved the layout of the Lab Instance Connection card, and its
  related documentation.

* Some unnecessary documentation files have been removed.


2015-01-24 and Before
=====================

Release notes are unavailable prior to the February 7, 2015
session. Please consult the `git log`_ for details of prior releases.

.. _git log: https://github.com/CoderDojoTC/python-minecraft/commits/master

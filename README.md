WildfirePy
=====

![](https://github.com/wildfirepy/wildfirepy/workflows/Python%20application/badge.svg)
![](https://github.com/wildfirepy/wildfirepy/workflows/Python%20package/badge.svg)

WildfirePy is an open-source Python library for Wildfire GIS data analysis.


Software Requirements
----------------------

If you are new to the world of development, then having the following software installed in your system might help in an easy follow-up, however, if you are confident with your skills set feel free to skip this section and move on to Installation part. 

To get started let's start with the installation of the elementary software that we will use in the project. A simple click in the name of the software will take you straight into the official sites of the software from where you can choose to download the version and edition according to your convenience and need.

For now we shall be using :

1) [Anaconda](https://www.anaconda.com/) Individual Edition, 64-Bit Graphical Installer (466 MB) with Python 3.7.

2) [Visual Studio Code](https://code.visualstudio.com/) Integrated Development Environment/ IDE.

Once we have our software-system setup ready we are now all set to dive in for the real work.

Installation
------------

Use git to grab the latest version of WildfirePy:

    git clone https://github.com/wildfirepy/wildfirepy.git

Once cloning is done, open VSCODE and on top left corner select ```File``` then click on ```Open Folder``` and choose the newly created folder i.e ```wildfirepy``` from the source where it was cloned.

Once the folder opens up in the IDE, it's time to fulfill the software requirements, in order to do so, first we will create a seperate environment for our project to dodge the problem of version conflicts and thereby isolating our project and its dependency requirements.Following are the steps in which it can be done. 

+ On top of the IDE choose ```Terminal``` and then ```New Terminal``` it will open up a new terminal at the bottom of the IDE.

+ Now to create the fresh environment, follow the below set of command :

  1) To create the environment :   ```conda create --name wildfirepy_env``` where 'wildfirepy_env' is the name of the environment.
  
  2) To activate the environment : ```conda activate wildfirepy_env```.
  
 Voila that's it, our fresh environment is already setup, now it's time for installing the dependencies.
 
+ From the list of folders and files in ```wildfirepy``` select ```requirements.txt```, this file contains the list of packages that are used in this project with there respective version specified alongside. 

+ Hover back to the terminal and download each of the dependencies one by one, so for instance if the file contains ```numpy==1.18.4``` as one of the package, then to install it type ```pip install numpy==1.18.4```.

Once all the dependencies are downloaded we are good to go with the futher steps.

In order to enable WildfirePy to be imported from any location you must make
sure that the library is somewhere in your PYTHONPATH environmental variable.
For now the easiest thing is to install it locally by running the following command.

```
pip install -e . 
```
(Note the '.' at the end of the command, No it's not a full stop and "YES ITS IMPORTANT" ).

The Command downloads some more build dependencies and makes a quick requirement check.Once it completes don't hesitate to move on the next section.

Usage
-----
Now it's time for a quick check on the working of ```wildfirepy``` , the part to where all the fun begins, sounds exciting right!
Here is a quick example of downloanding some burnt area information from MODIS, in the terminal type ```python``` and type following command in the given sequential order.

```python
>>> from wildfirepy.net.usgs import ModisBurntAreaDownloader
>>> import matplotlib.pyplot as plt
>>> dl = ModisBurntAreaDownloader() 
>>> jpg_file = dl.get_jpg(year=2020, month=2, latitude=28.7041, longitude=77.1025)
>>> plt.imshow(plt.imread(jpg_file))
>>> plt.show()
```
If a nice frame pops up and you feel satisfied and mesmerized, then my friend!, you did it, Mission Successfull and now it's time for further exploration.

Getting Help
------------

For more information or to ask questions about WildfirePy, check out:

 * IRC: #wildfirepy on [Riot](https://riot.im/app/#/room/!jWUOIxirCHymPQkpXb:matrix.org)

Contributing
------------

If you would like to get involved, start by joining the IRC chat room named `#wildfirepy` on [Riot](https://riot.im/app/#/room/!jWUOIxirCHymPQkpXb:matrix.org).

Help is always welcome so let us know what you like to work on, or check out the [issues page](https://github.com/wildfirepy/wildfirepy/issues) for a list of some known outstanding items.

Fork the Repository, clone it, solve the issue,commit it into your local repository and make a [Pull Request](https://help.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests).

NOTE : It's always advised to make changes and commit in the local repository first and not directly to the Master Branch.

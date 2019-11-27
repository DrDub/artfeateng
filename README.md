# Case studies for The Art of Feature Engineering

The code behind these case studies is intended as a communication tool
for the ideas expressed in the book. This code is as far from
production code as it can get. Moreover, many of the techniques
presented are available as part of some of the underlining libraries
used. Showing a step-by-step implementation of different feature
engineering techniques is intended.

The style used in Python is also intentionally kept simple for people
coming from other languages that plan to use the ideas described in
the book outside of Python.

As described in the book, the case studies explore as many feature
engineering ideas within the limits of:

* At most one day of execution time per notebook.
* No GPU required.
* Minimal dependencies.
* At most 8Gb of RAM.

As a result of these constraints, these notebooks do not undergo as
much hyperparameter tuning as necessary. This is a shortcoming of
these case studies, keep it in mind if you want to follow a similar
path with your experiments.

Minor issues:

As these case studies are foremost an educational tool, I expect
readers might want to try variants of some cells in isolation. To help
with that, I have tried for the cells to be executable without having
to re-run the whole notebook. That means that most cells read
everything they need from disk and write all their results back into
disk. This is unnecessary with normal notebooks as the values remain
in memory, so the code for each cell might look long and somewhat
unusual. In a sense, each cell tries to be a separate Python
program. To solidify the vision of independent tweaking, I am also
distributing these intermediate files besides the input data.

I dislike Pandas with a passion and discourage its use at any level.
These notebooks are Pandas-free, which might seem unusual to some.

The last topic in the last chapter (recommendation as imputation) uses
more than 8Gb of RAM.


## Fetching the data

The data is available in both Zip and Tar BZip2 files. Chapter 9
(images) uses a tile set provided by NASA. It contains 88 thousand
tiles occupying 6Gb of space. These tiles are used at the beginning of
Chapter 9's notebook to generate 80 thousand boxes around each city or
town. These boxes occupy less than 1Gb of disk space. As such, I am
distributing the boxes and leaving the tiles for a separate download,
in the event you might want to experiment with other techniques
extracting more data from the original tiles. Otherwise the feature
engineering techniques in Chapter 9's notebook should run fine from
the extracted boxes.

* (Book Data, Zip format 2.4Gb)[http://artfeatureengineering.com/data/feateng_data.zip]
* (Book Data, Tar BZip2 format 1.8Gb)[http://artfeatureengineering.com/data/feateng_data.bz2]
* (Tile Data, Zip format 5.4Gb)[http://artfeatureengineering.com/data/feateng_tiles.zip]
* (Tile Data, Tar BZip2 format 5.3Gb)[http://artfeatureengineering.com/data/feateng_tiles.bz2]

The full set of intermediate files weights about 20Gb and it is
distributed as BitTorrent file via Academic Torrents:


## Set-up a virtual environment

python3 -m venv feateng
source ./feateng/bin/activate


## Install local dependencies for graphviz
sudo apt install python-pydot python-pydot-ng graphviz


## General dependencies

pip3 install jupyter
pip3 install ipykernel
pip3 install scikit-learn
pip3 install lxml
pip3 install numpy
pip3 install scipy
pip3 install matplotlib
pip3 install graphviz


## Dependencies for Chapter 7

pip3 install statsmodels
  

## Dependencies for Chapter 8

pip3 install stemming
pip3 install gensim


## Dependencies for Chapter 9

pip3 install opencv-python


## Dependencies for Chapter 10

pip3 install geopy


## Launch Jupyter with the feateng environment

python -m ipykernel install --user --name feateng
jupyter notebook --no-browser .


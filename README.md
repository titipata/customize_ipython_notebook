klab_ipython_notebook
--------------------
CSS file and logo extension to customize ipython notebook style for Kording lab.

In this repository, I attached css file (adapted from HHammond ipython notebook example) and klab logo for ipython notebook. We can create new `profile_klab` folder in `.ipython` folder by typing this bash script:

`ipython profile create klab`

Note that `klab` is the profile name. Then, we will add this `css` file and logo into the folder to custom your ipython notebook! You can locate `.ipython` location by typing `ipython locate` in bash. Then we can go to that directory. We will see `profile_klab` folder located in `.ipython` folder. Now, we can place given file to the directory that we have created. The location of `custom.css` file is usually located in this location:

`~/.ipython/profile_klab/static/custom/custom.css`

And the location of logo is located as follow (use `mkdir` to create folder):

`~/.ipython/profile_klab/static/base/images/ipynblogo.png`

Now, you can run ipython notebook with your new created profile by typing:

`ipython notebook --profile klab`

Then, you will rejoice by this beautiful selected font :)

Inspriation
----------
* [Subject Zero](http://klab.smpp.northwestern.edu/wiki/index.php5/Subject_Zero), Kording lab mascot

Reference
----------
* HHammond ipython notebook (from nbviewer). Here is his [original link](http://nbviewer.ipython.org/gist/HHammond/7a78d35b34d85406aa60)

Team members
----------
* Titipat Achakulvisut

Example IPython Notebook
----------
Thai version of the k-lab logo
![Alt text](https://github.com/titipata/klab_ipython_notebook/blob/master/notebook_example.png "Example Notebook")


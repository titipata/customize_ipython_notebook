klab_ipython_notebook
--------------------
CSS file and logo extension to customize ipython notebook style for Kording lab.

####Quick style change for default notebook

```bash
cd ~/.ipython/profile_default/static/custom
rm custom.css
wget https://raw.githubusercontent.com/titipata/klab_ipython_notebook/master/custom.css
```

There are a lot more `custom.css` file that you can download from [Nikhil S's Github](https://github.com/nsonnad/base16-ipython-notebook).

####Custom by creating new profile

This is step-by-step on how to create a new ipython profile and add logo to your own ipython. In this repository, I attached css file (adapted from HHammond ipython notebook example) and klab logo for ipython notebook. We can create new `profile_klab` folder in `.ipython` folder by typing this bash script:

```bash
ipython profile create klab
```

Note that `klab` is the profile name. Our final goal, we will add this `css` file and logo `ipynblogo.png` into the folder to custom your ipython notebook! First, we can locate `.ipython` location by typing

```bash
ipython locate
```

in bash shell. Then we can go to that directory. We will see `profile_klab` folder located in `.ipython` folder. Now, we can place given file to the directory that we have created. Suppose the `.ipython` is located in home directory, the location of `custom.css` file is located in this given location:

```bash
~/.ipython/profile_klab/static/custom/custom.css
```

And the location of logo is located as follow (use `mkdir` to create folder):

```bash
~/.ipython/profile_klab/static/base/images/ipynblogo.png
```

Now, you can run ipython notebook with your new created profile by typing:

```bash
ipython notebook --profile klab
```

Then, you will rejoice by this beautiful selected font :)

####Custom Style in IPython Notebook

You can also download style to ipython notebook by simply adding these lines to the notebook. This will work with another  customize `css` file which will become handy if you want to change style in particular notebook:

```python
import requests
from IPython.core.display import HTML
link = requests.get("https://raw.githubusercontent.com/titipata/klab_ipython_notebook/master/custom.css")
HTML("<style>"+link.content+"</style>")
```

####Example IPython Notebook on NBViewer

If you want to put code on NBViewer, we can add `<style>` and `</style>` to the beginning of `custom.css` file (where we have `custom_nb.css` file added on the repository). Then, we can attach `custom_nb.css` file to notebook by put few lines of code that includes the file i.e.

```python
from IPython.core.display import HTML
HTML(open("<path_to>/custom_nb.css", "r").read())
```

Example is shown here in NBViewer [link](http://nbviewer.ipython.org/github/titipata/klab_ipython_notebook/blob/master/Example%20Notebook%20with%20Custom.ipynb)


Inspriation
----------
* [Subject Zero](http://klab.smpp.northwestern.edu/wiki/index.php5/Subject_Zero), Kording lab mascot

Reference
----------
* HHammond ipython notebook (from nbviewer). Here is his [original link](http://nbviewer.ipython.org/gist/HHammond/7a78d35b34d85406aa60)

Team members
----------
* Titipat Achakulvisut
* Daniel Acuna

Example IPython Notebook
----------
Thai version of the k-lab logo
![Alt text](https://github.com/titipata/klab_ipython_notebook/blob/master/notebook_example.png "Example Notebook")


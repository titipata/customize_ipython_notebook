Customize IPython Notebook
--------------------

CSS file and logo extension to customize IPython Notebook style for [Kording lab](http://klab.smpp.northwestern.edu/wiki/index.php5/Main_Page) (it's now named as Jupyter notebook).


#### Quick style change for default notebook

**Before version 4.1** easy way to try the `css` file is just to replace original `custom.css` file with new one using `wget`

```bash
cd ~/.ipython/profile_default/static/custom
rm custom.css
wget https://raw.githubusercontent.com/titipata/klab_ipython_notebook/master/custom.css
```

There are a lot more `custom.css` file that you can download from [Nikhil S's Github](https://github.com/nsonnad/base16-ipython-notebook).

**After 4.1** they move `~/.ipython/profile_default/static/custom/` to `~/.jupyter/custom/` instead (see more details  [here](http://jupyter.readthedocs.org/en/latest/migrating.html)). So first, we have to create the folder in `~/.jupyter`. Then download the `css` file into `~/.jupyter/custom/custom.css`

```bash
wget https://raw.githubusercontent.com/titipata/klab_ipython_notebook/master/custom.css
```


#### Customize by creating new profile

**Before version 4.1** This is step-by-step on how to create a new ipython profile and add logo to your own ipython. In this repository, I attached css file (adapted from HHammond IPython Notebook example) and klab logo for ipython notebook. We can create new `profile_klab` folder in `.ipython` folder by typing this bash script:

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

**After version 4.1 and before too**

We can actually apply css in order to custom the logo. Basically, we can add `logo.png` into `.jupyter/custom/logo.png`. Then add the following line to `.jupyter/custom/custom.css` in order to load the logo. (See this [post](http://stackoverflow.com/questions/35469343/change-jupyter-notebook-version-4-x-logo) and this [post](http://stackoverflow.com/questions/27177459/customize-welcome-page-of-ipython-notebook) on Stack Overflow.)

```css
#ipython_notebook {
    height: 40px !important;
}

#ipython_notebook img{
    display:block;
    background: url(logo.png) no-repeat;
    background-size: contain;
    width: 233px;
    height: 33px;
    padding-left: 233px;
    -moz-box-sizing: border-box;
    box-sizing: border-box;
}
```

If you want to increase the space for logo, just add first css tag. And you can control the size of logo by customizing `width` and `height`
in the second component.

#### Custom Style directly on IPython Notebook

You can also download style to ipython notebook by simply adding these lines to the notebook. This will work with another  customize `css` file which will become handy if you want to change style in particular notebook:

```python
import requests
from IPython.core.display import HTML
link = requests.get("https://raw.githubusercontent.com/titipata/klab_ipython_notebook/master/custom.css")
HTML("<style>"+link.content+"</style>")
```

#### Example IPython Notebook on NBViewer

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

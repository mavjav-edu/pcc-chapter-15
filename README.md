# Generating Data 
In this chapter, we’ll use @matplotlib to make simple plots, such as line graphs and scatter plots. After which, we’ll create a more interesting data set based on the concept of a random walk—a visualization generated from a series of random decisions.

We’ll also use a package called [Pygal](https://github.com/Kozea/pygal), which focuses on creating visualizations that work well on digital devices. You can use Pygal to emphasize and resize elements as the user interacts with your visualization, and you can easily resize the entire representation to fit on a tiny smartwatch or giant monitor. We’ll use Pygal to explore what happens when you roll dice in various ways.

- [Generating Data](#generating-data)
  - [Installing matplotlib](#installing-matplotlib)
    - [Checking if matplotlib is already installed](#checking-if-matplotlib-is-already-installed)
    - [Simple installation with pip](#simple-installation-with-pip)
  - [Installing matplotlib on Linux](#installing-matplotlib-on-linux)
  - [Installing matplotlib on OS X](#installing-matplotlib-on-os-x)
  - [Installing matplotlib on Windows](#installing-matplotlib-on-windows)
  - [Installing Pygal](#installing-pygal)
    - [Running Pygal code exactly as it appears in the book](#running-pygal-code-exactly-as-it-appears-in-the-book)
    - [Using the latest version of Pygal](#using-the-latest-version-of-pygal)
  - [Updates](#updates)
  - [TRY IT YOURSELF \#1](#try-it-yourself-1)
  - [TRY IT YOURSELF \#2](#try-it-yourself-2)
  - [TRY IT YOURSELF \#3](#try-it-yourself-3)

Installing matplotlib ---

There are many different ways to install matplotlib to your system. In this section, I'll recommend one method for each operating system. If you'd like to see the kinds of visualizations you can make with matplotlib, see the official matplotlib [sample gallery](http://matplotlib.org/gallery.html). When you click a visualization in the gallery, you can see the code used to generate the plot.

### Checking if matplotlib is already installed 
First, check if matplotlib is already installed on your system:

    $ python     >>> import matplotlib     >>>

If you don't see an error message, then matplotlib is already installed on your system and you should be able to get started right away on this chapter's projects. If you get an error message, read the appropriate section below for help installing matplotlib on your operating system.

### Simple installation with pip 
The matplotlib developers have been working hard to simplify the installation process, and sometimes you can install it using just pip. Try this and see if works on your system:

    $ pip install --user matplotlib 
If you need help using pip, see the [instructions](../chapter_12/installing_pip.md) in Chapter 12. If this doesn't work, try leaving off the `--user` flag.

If the installation seems to run without errors, try importing matplotlib:

    $ python     >>> import matplotlib     >>>

If the import runs successfully, you're finished and you can start using matplotlib. If the import statement fails, look at the appropriate section below for your operating system.

Installing matplotlib on Linux ---

If you're using the version of Python that came with your system, you can use your system's package manager to install matplotlib in one line. For Python 3, this is:

    $ sudo apt-get install python3-matplotlib 
If you're using Python 2.7, this is:

    $ sudo apt-get install python-matplotlib 
If you installed a newer version of Python, you'll have to install several libraries that matplotlib depends on:

    $ sudo apt-get install python3.5-dev python3.5-tk tk-dev     $ sudo apt-get install libfreetype6-dev g++

Then use pip to install matplotlib:

    $ pip install --user matplotlib 
If you need help using pip, see the [instructions](../chapter_12/installing_pip.md) in Chapter 12.

[top 🔝](#)

Installing matplotlib on OS X ---

Aple includes matplotlib with its standard Python installation, so make sure you <a href="#checking-if-matplotlib-is-already-installed">check if it's already installed</a> before installing it yourself.

If matplotlib is not already installed and you used Homebrew to install Python, install it like this:

    $ pip install --user matplotlib 
If you need help using pip, see the [instructions](../chapter_12/installing_pip.md) in Chapter 12. If you have trouble installing matplotlib using pip, try leaving off the `--user` flag.

[top 🔝](#)

Installing matplotlib on Windows ---

To install matplotlib on Windows you'll first need to install Visual Studio, which will help your system install the packages that matplotlib depends on. Go to [https://dev.windows.com/](https://dev.windows.com/), click [**Downloads**](https://dev.windows.com/downloads), and look for *Visual Studio Community*. This is a free set of developer tools for Windows. Download and run the installer.

Next you'll need an installer for matplotlib. Go to [https://pypi.python.org/pypi/matplotlib/](https://pypi.python.org/pypi/matplotlib/) and look for a wheel file (a file ending in *.whl*) that matches the version of Python you’re using. For example, if you’re using a 32-bit version of Python 3.5, you’ll need to download *matplotlib-1.4.3-cp35-none-win32.whl*.

If you don't see a file matching your installed version of Python, look at what’s available at [http://www.lfd.uci.edu/~gohlke/pythonlibs/#matplotlib](http://www.lfd.uci.edu/~gohlke/pythonlibs/#matplotlib). This site tends to release installers a little earlier than the official matplotlib site.

Copy the *.whl* file to your project folder, open a command window, and navigate to the project folder. Then use pip to install matplotlib:

    > cd python_work     python_work> python -m pip install --user matplotlib-1.4.3-cp35-none-win32.whl 
If you need help using pip, see the [instructions](../chapter_12/installing_pip.md) in Chapter 12.

[top 🔝](#)

Installing Pygal ---
Pygal has been updated recently, which is a good thing; you're learning a library that's being steadily improved. This also means you have two choices about how to install Pygal. You can install version 1.7 which supports the code in the book exactly as it's written, or you can install the most recent version of Pygal and modify some of the code in the book. If you install the most recent version there are some slight changes you'll need to make for the code in chapter 16.

### Running Pygal code exactly as it appears in the book 
Pygal 1.7 allows the code to run exactly as it appears in the book. To do this, modify the command for installing pygal so pip will install version 1.7 (page 340):

    $ pip install --user pygal==1.7

On Windows, this would be:

    > python -m pip install --user pygal==1.7

If you've already installed Pygal you can see which version was installed by running the command `pip freeze`:

    $ pip freeze     pygal==2.2.3

If you installed Pygal 2.0 or later and want to install 1.7 instead, uninstall Pygal first:

    $ pip uninstall pygal     $ pip install --user pygal==1.7

### Using the latest version of Pygal 
The latest version of Pygal is version 2.2.3. This is the version that will be installed if you don't specify a version for pip to install:

    $ pip install --user pygal 
or 
    $ python -m pip install --user pygal 
If you use the latest version, you'll need to make some slight changes to the code in chapter 16:

- [Updates to Chapter 16 Pygal code](../chapter_16/README.html#updates)

[top 🔝](#)

Updates ---

Pygal has been updated to version 2; make sure you've read the notes about [installing Pygal](#installing-pygal) above.

On the latest version of Pygal, the code from Chapter 15 runs as it's written in the book. In Pygal versions 2.0-2.1.1, there was a change to a default setting that caused tooltips not to appear. That change has been reverted, so the code in the book is still correct. If you're using one of these versions you can upgrade your installation of Pygal:

    $ pip install --upgrade pygal 
This should upgrade your installation to the latest version of Pygal, and your code should work as it's written.

TRY IT YOURSELF \#1
-------------------

<span id="ch15exe1"></span>**15-1. Cubes:** A number raised to the third power is a *cube*. Plot the first five cubic numbers, and then plot the first 5000 cubic numbers.

<span id="ch15exe2"></span>**15-2. Colored Cubes:** Apply a colormap to your cubes plot.

<span id="page_339"></span>

TRY IT YOURSELF \#2
-------------------

<span id="ch15exe3"></span>**15-3. Molecular Motion:** Modify [*rw_visual.py*](rw_visual.py) by replacing `plt.scatter()` with `plt.plot()`. To simulate the path of a pollen grain on the surface of a drop of water,
pass in the `rw.x_values` and `rw.y_values`, and include a `linewidth`
argument. Use 5000 instead of 50,000 points.

<span id="ch15exe4"></span>**15-4. Modified Random Walks:** In the class `RandomWalk`, `x_step` and `y_step` are generated from the same set of conditions. The direction is chosen randomly from the list `[1, -1]` and the distance from the list `[0, 1, 2, 3, 4]`. Modify the values in these lists to see what happens to the overall shape of your walks. Try a longer list of choices for the distance, such as 0 through 8, or remove the –1 from the *x* or *y* direction list.

<span id="ch15exe5"></span>**15-5. Refactoring:** The method `fill_walk()` is lengthy. Create a new method called `get_step()` to determine the direction and distance for each step, and then calculate the step. You should end up with two calls to `get_step()` in `fill_walk()`:

``` python x_step = get_step()
y_step = get_step()
```

This refactoring should reduce the size of `fill_walk()` and make the method easier to read and understand.

TRY IT YOURSELF \#3
-------------------

<span id="ch15exe6"></span>**15-6. Automatic Labels:** Modify [*die.py*](die.py)
and [*dice_visual.py*](dice_visual.py) by replacing the list we used to set the value of `hist.x_labels` with a loop to generate this list automatically. If you’re comfortable with list comprehensions, try replacing the other `for` loops in [*die_visual.py*](die_visual.py) and [*dice_visual.py*](die_visual.py) with comprehensions as well.

<span id="ch15exe7"></span>**15-7. Two D8s:** Create a simulation showing what happens if you roll two eight-sided dice 1000 times.
Increase the number of rolls gradually until you start to see the limits of your system’s capabilities.

<span id="ch15exe8"></span>**15-8. Three Dice:** If you roll three D6
dice, the smallest number you can roll is 3 and the largest number is 18. Create a visualization that shows what happens when you roll three D6 dice.

<span id="ch15exe9"></span>**15-9. Multiplication:** When you roll two dice, you usually add the two numbers together to get the result. Create a visualization that shows what happens if you multiply these numbers instead.

<span id="ch15exe10"></span>**15-10. Practicing with Both Libraries:**
Try using matplotlib to make a die-rolling visualization, and use Pygal to make the visualization for a random walk.


&nbsp; | &nbsp; | &nbsp; | &nbsp;
----|----|----|----
[&#10094; Prev](../../../pcc-chapter-14)| &nbsp; | &nbsp; | &nbsp;[Next &#10095;](../../../pcc-chapter-16)

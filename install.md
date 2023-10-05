## Downloading course material
All files that are associated with this course are available via this public git repository. The use of <code>git</code> is encouraged, but not mandatory.

Using git, the course material can be downloaded by cloning the github repository:

<pre class="prettyprint"><code class="language-java">$ git clone git@github.com:cforssen/BayesianMethodsNP.git </code></pre>

after which it will be available in the <code>BayesianMethodsNP</code> directory. You will have to perform a <code>git pull</code> operation when wou want to retrieve future updates in the github repository. When using the github repository to stay up-to-date with course material it is recommended to make a local copy of notebooks before starting to edit them. The easiest is probably to create a new directory with your local copies. The git approach, however, would be to create a new branch.

There are plenty of tutorials and guides how to use git. Two recommended ones are:
<ul>
<li><a href="https://guides.github.com/introduction/git-handbook/" target="_blank" rel="noopener">The Git Handbook</a> (a GitHub Guide),</li>
<li><a href="https://git-scm.com/book/en/v2" target="_blank" rel="noopener">Pro Git</a> (an online book by Scott Chacon and Ben Straub).</li>
</ul>

You are encouraged to set your user name and email address. This is important because every Git commit uses this information, and it&rsquo;s immutably baked into the commits you start creating:<

<pre class="prettyprint"><code class="language-java">$ git config --global user.name "Emilia Student"
$ git config --global user.email name@example.com
</code></pre>

You might also want to set your default editor. Pick the one that you prefer. E.g.,
<pre class="prettyprint"><code class="language-java">$ git config --global core.editor emacs/vi/nano/...
</code></pre>

## Python distribution
We will make extensive use of Python as programming language and its myriad of available libraries. You will find Jupyter notebooks invaluable in your work since they make it possible to run Python code interactively with the immediate benefit of visualizing your data. Jupyter notebooks also offer the possibility to run Julia or R code, or even integrate code in compiled languages like C++, Fortran etc if you prefer. The focus in this course will be on Python.

The notebooks that we will be using depend on several scientific python modules (see the list in <a href="environment.yml">environment.yml</a>) and they require a python3.x installation.

These python modules and their dependencies are best installed using <code>conda</code> by creating a virtual environment. The <code>conda</code> package manager can easily be installed as a local user, which does not require administrator permissions. Note that he miniconda installation requires 400 MB disk space.

<ol>
<li>Download and run the miniconda installer:
<pre class="prettyprint"><code class="language-java">$ wget https://repo.anaconda.com/miniconda/Miniconda3-latest-Linux-x86_64.sh
$ bash Miniconda3-latest-Linux-x86_64.sh
</code></pre>
During the installation you will have to accept the license agreement. We also recommend to use the default installation directory <code>~/miniconda3</code> and to allow the installer to run <code>conda init</code> to set environment variables (this is done by typing yes when prompted). It is recommended to use the <code>bash</code> shell. Further details and troubleshooting is available at <a href="https://conda.io/projects/conda/en/latest/user-guide/install/index.html">conda.io</a>.</li>
<li>Check the installation:
<pre class="prettyprint"><code class="language-java">$ conda list
</code></pre>
should give a list of python packages.
<pre class="prettyprint"><code class="language-java">$ which python
</code></pre>
should give the path to the conda python executable <code>~/miniconda3/bin/python</code> and
<pre class="prettyprint"><code class="language-java">$ python --version
</code></pre>
should show that you are using a Python3 version.</li>
<li>Make sure that you have downloaded the course material, preferably with <code>git clone</code> as described above. Go to the directory with the <code>environment.yml</code> file.</li>
<li>Create a virtual environment
<pre class="prettyprint"><code class="language-java">$ conda env create -f environment.yml
</code></pre>
<p>which reads the environment.yml file in your current directory. It will check dependencies and then download and install several packages. It might take a considerable time to run and you will probably be asked to accept the suggested installation procedure.</p>
<p>Some packages that we will be using are not included in the default conda channels. One can either specify relevant package channel(s) in the environment.yml file (as done here), or add them to the default conda channel configuration via, e.g, <code>conda config --append channels conda-forge</code></p>
</li>
<li>
<p>Once the virtual environment has been created it can be activated:</p>
<pre class="prettyprint"><code class="language-java">$ conda activate tif285-env
</code></pre>
<p>For future reference, to deactivate the virtual environment:<code>conda deactivate</code></p>
</li>
<li>
<p>To update the virtual environment (e.g. after adding packages to the <code>environment.yml</code> file)</p>
<pre class="prettyprint"><code class="language-java">$ conda env update -f environment.yml
</code></pre>
</li>
</ol>

There are also other options (<code>venv</code>, <code>pipenv</code>) for creating virtual environments with the python version and packages that we will be using. Or you can install packages, keeping track yourself of dependencies, using <code>pip install</code>.</p>

## Jupyter notebooks
<a href="https://jupyter.org/">Jupyter notebooks</a> will be used extensively in this course. It is an open-source web application that allows you to create and share documents that contain live code, equations, visualizations and narrative text. Uses include: data cleaning and transformation, numerical simulation, statistical modeling, data visualization, machine learning, and much more.

Therefore, once the environment is set up and activated, you are encouraged to get acquainted with the notebook workflow by starting a jupyter notebook in the directory with the lecture contents. In the directory tree from the github repository:

<pre class="prettyprint"><code class="language-java">$ jupyter notebook
</code></pre>

The Jupyter Notebook will open in your default browser. It should show a list of the subdirectories. It is recommended that you start with the Jupyter-Python-NumPy exercise notebooks in the Intro directory. Just double-click on the first one to get started. Make sure to evaluate the cells with <strong>shift-return</strong>.

However, a word of caution: Since Jupyter Notebooks are not pure text files (they are basically json files), they do not integrate seamlessly with git version control. The action of evaluating a cell in a notebook, without changing any code, will register as a file update in git. 

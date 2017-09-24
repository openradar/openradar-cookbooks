How to use the openradar-cookbooks?
===================================

Interactive examples with jupyter notebooks
-------------------------------------------

By running the `jupyter notebooks <http://jupyter.org/>`_ you can interactively explore various topics. Each notebook is organized in documented code blocks. You can browse through a notebook block by block, inspect the results, and experiment with the code. However, you can also view the rendered notebooks including the example results on the web pages of this section: Each page was directly generated from the notebooks-section. This way, you can copy&paste code snippets directly into your applications.

.. note:: Are you using the `Open Virtual Machine for Cross-Platform Weather Radar Science <http://openradar.github.io/>`_? Then skip the rest: just log in, run the command ``$ ./start_notebook.sh`` and direct your browser to `http://127.0.0.1:8888/tree <http://127.0.0.1:8888/tree>`__. That's it.

Otherwise, you need to make sure to

- :ref:`get the actual notebook files <ref_get_notebooks>`,
- :ref:`get the example data <ref_get_data>`,
- and :ref:`install jupyter <ref_get_jupyter>`

Once these conditions are met, you can open a notebook: Launch a console or bash window in the directory that contains the example notebooks. You just need to activate your python environment and execute::

	> source activate openradar
	> jupyter notebook
	
A browser window will open (typically at http://localhost:8888/tree) which will show the tree of the directory in which you started the jupyter notebook server. Just open any notebook by clicking. Code cells are executed by hitting ``Shift + Enter`` or by using the toolbar icons. It's pretty much self-explaining, and you'll soon get the hang of it.


.. _ref_get_notebooks:

How can I get the example notebooks?
------------------------------------

The notebooks are distributed with each openradar-cookbooks release. Alternatively, you can `download <https://github.com/openradar/openradar-cookbooks/archive/master.zip>`_ the latest ("bleeding edge") notebooks from our `GitHub repository <https://github.com/openradar/openradar-cookbooks>`_. In both cases, you find everything in the directory ``/notebooks`` (after extracting the downloaded archives).


.. _ref_get_data:

How can I get the example data?
-------------------------------

Most notebooks use example data. These data are provided in a separate repository and you need to "install" them manually. *"Installing"* actually means: Download the data archive `here <https://github.com/openradar/openradar-cookbooks-data/archive/master.zip>`_ and extract it into any arbitrary directory. Now you need to set an environment variable pointing to that directory:

**Under Windows**, open a console and execute ``setx OPENRADAR_DATA <full path to openradar-cookbooks-data>``.

**Under Linux**, you need to set the env variable in your current shell profile. In most cases, this will be loaded from ``~/.bashrc``. Open that file in an editor (e.g. via ``$EDITOR ~/.bashrc``) and add the following line at the end of the file::

	export OPENRADAR_DATA=/insert/full/path/to/openradar-cookbooks-data/

After this procedure, the example notebooks will automagically pull the required files from the data archive.
	

.. _ref_get_jupyter:
	
How to install jupyter?
-----------------------

As already pointed out above, you can just look at the rendered notebooks :doc:`online docs <notebooks>`. In order to use them interactively, you need to install ``jupyter``. ``jupyter`` is shipped with `Anaconda's <https://www.continuum.io/downloads>`_ distribution by default. If you installed wradlib into Anaconda's *default (root) environment*, you are already done. If you installed openradar-cookbooks in a separate *virtual environment*, you need to install ``jupyter`` in that virtual environment, too::

	Under Windows:
	> activate openradar
	[openradar] > conda install jupyter
	
	Under Linux/OSX:
	$ source activate openradar
	[openradar] $ conda install jupyter

If you are not sure which conda environments you have, you can check via ``conda info --envs``. 

If you did not install `openradar-cookbooks` on top of Anaconda, you should first check whether ``jupyter`` might already be available on your system (use e.g. ``jupyter --version``). If ``jupyter`` is not available, you should check out the `jupyter docs <http://jupyter.readthedocs.io/en/latest/install.html>`_ for alternative installation options.

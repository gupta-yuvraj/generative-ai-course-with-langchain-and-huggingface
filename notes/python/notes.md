## Different ways of creating python virtual environments:-

1. Using python directly:

   `python -m venv <name-of-the-environment-with-path>`

   Notes: The environment that is created by using this method will have the same version as that of source python version using which the environment was created.

   To activate this environment, just execute the activate binary placed inside the virtual environment's script folder like:
   `<path-of-the-virtual-env>/Scripts/activate`
2. By making use of virtualenv library.
3. By making use of conda library.

To create virtual envirnment using conda command: `conda create -p <name-of-virtual-env-with-path> python==<verion-number>`

For example: `conda create -p myvenv python==3.10`

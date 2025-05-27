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

To activate a conda environment, use the following command:
   `conda activate <full-path-to-conda-virtual-env-name>`

For example:
   `conda activate /Users/ygupta/Desktop/learning/generative-ai-course-with-langchain-and-huggingface/venvs/AiPy313`

**Additional Notes on Conda Virtual Environments:**

- To create a conda environment from a requirements.txt file:
  `conda create --name <env-name> --file requirements.txt`

- To create a conda environment from an environment.yml file (recommended):
  `conda env create -f environment.yml`

- To list all available conda environments:
  `conda env list`

- To export the current environment to an environment.yml file:
  `conda env export > environment.yml`

- To remove a conda environment:
  `conda remove --name <env-name> --all`

- The currently active conda environment is shown in your terminal prompt, or you can check it with:
  `echo $CONDA_DEFAULT_ENV`

- You can install additional packages into an active environment using:
  `conda install <package-name>`

- If you want to update all packages in the environment:
  `conda update --all`


Notes: To connect the newly created virtual env to jupyter notebooks, please install ipykernel package. You can use following command to do that:
   `pip install ipykernel`
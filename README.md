# Standards Readability Tool 

## Functions of the tool 
1. Upload pdf of standard
2. Break standard into subsets to calculate readability score
3. Determine readability score of each subset of the standard
4. Output an excel document with a table of each subset and the subsequent score
5. Provide an input feature where a user could input a sentence and receive readability scores in real time.


## How to use this repository

### Conda Environment
Have Anaconda installed (recommend Miniconda) and accessible via PATH (`conda` should work in your terminal). These instructions assume `conda>=4.6`. Rather than install each package as you need it it *directly*, we are going to be using an environment YAML file to keep track of all major dependencies you rely on. This will help you and others recreate the environment in the future.

To start, open the `environment.yml` file in the top-lvl directory. 

1. **Rename your environment**. 
This name will be used for all activation/deactivation in terminal and PyCharm, e.g. 
    `conda activate my-project-envname` 
before working, and `conda deactivate` after you're done. 
    
2. **Set environment channels** 
Usually the two supplied should be fine, as `conda` is the most typical, with many cutting-edge or latest-release packages can use `conda-forge`. If any packages you wish to install use a `-c some-channel` flag in the installation instructions, add `some-channel` here and it will automatically be searched during installation. 

3. **Conda Dependencies** 
Any packages that support conda installation can be added here as a member of the list. Some defaults have been provided, including `jupyter` which allows you to use notebooks, along with any `ipython` features, by extension. *NOTE*: versioning is done with the `conda` [package match specifications](https://docs.conda.io/projects/conda-build/en/latest/resources/package-spec.html#package-match-specifications)

4. **Pypi Dependencies** 
By far the most common way to install a package is via pip. The reason we are not using `pipenv` or `virtualenv` is that `conda` supports direct installation of Pypi packages, using a `pip` sublist. This supports names, version globbing, and even direct repository installation for unreleased packages e.g: 
```yaml
dependencies:
  - python=3.7
  - pip    
  - pip:
      - statsmodels
      - git+https://github.com/networkx/networkx.git
      - pomegranate==0.11.*
```

5. Creating/Maintaining
To create the environment (prior to activating it) simply run `conda env create -f environment.yml`. Then, if a new package is needed, rather than directly installing it via terminal, add it to the environment file and update your environment directly: `conda env update -f environment.yml`

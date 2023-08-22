# sport-repo-template



## Github
### Clone repo
#### Github Desktop
1. Click on "Add" in the top left corner
2. Click on "Clone repository"
3. Select the repository you want to clone
4. Select the location you want to clone the repository to
5. Click on "Clone"

#### Git Terminal
1. Go to the location you want to clone the repository to:
2.
```python
git clone <HTTPS or SSH>
```
![alt text](https://github.com/brondby-if/sport-repo-template/blob/main/images/Git%20clone.png "Failed pre-commit")

## Create new environment
Create new environment with Python 3.9:
```python
conda create -n <NAME> python=3.9
```

Activate new environment:
```python
conda activate <NAME>
```

Install requirements into new enviroment:
```python
pip install -r requirements.txt
```


## Pre-commit

for pre-commit to work you need to install pre-commit:
```python
pip install pre-commit
```

Automaticly when commiting to github there will be some pre-commit checks.

You can run the pre-commit command before pre-commiting to check your work:
```python
pre-commit run --all-files
```
### Pre-commit list
* check-yaml - checks yaml files for parseable syntax
* end-of-file-fixer - ensures that a file is either empty, or ends with one newline.
* trailing-whitespace - trims trailing whitespace.
* black - code formatter
* flake8 - linting the code (identifying bugs)
* interrogate - checks docstrings (Needs to be above 20%)
* isort - sorts imports
* check requirements.txt - checks if requirements.txt is made

### Pre-commit failed

#### Git Desktop
If pre-commit failed and "files were modified by this hook" this means files were modified and we need to git add them again.

![alt text](https://github.com/brondby-if/sport-repo-template/blob/main/images/Failed%20pre-commit.png "Failed pre-commit")

Click commit in the buttom left corner and then click "Commit to main" in the top right corner.

[comment]: https://www.dev2qa.com/how-to-fix-importerror-dll-load-failed-while-importing-_sqlite3-the-specified-module-could-not-be-found/?utm_content=cmp-true

#### Git Terminal
If pre-commit failed and "files were modified by this hook" this means files were modified and we need to git add them again.
It could look like:
```python
$ git add .
$ git commit -m <MESSAGE>
```
![alt text](https://github.com/brondby-if/sport-repo-template/blob/main/images/Failed%20pre-commit.png "Failed pre-commit")
```python
$ git add .
$ git commit -m <MESSAGE>
```
![alt text](https://github.com/brondby-if/sport-repo-template/blob/main/images/Passed%20pre-commit.png "Passed pre-commit")
```python
$ git push
```


### Skip pre-commit
#### Git Terminal
When commiting to GitHub and want to skip pre-commits:
```python
git commit -m <MESSAGE> --no-verify
```

## Update / create requriments.txt
Creating a requiments file with the used packages:
```python
pipreqs /path/to/project
```
Example:
```python
pipreqs ../sport-repo-template
```
pipreqs only creates a requirements file with the packages used in the other files.

Another way of creating a requirements file is by typing:
```python
pip freeze > requirements.txt
```
This creates a requirements file with all the packages install with pip in your environment.

## Copy environment
Copy environment:
```python
conda env export > environment.yml
```
This copies the environment to a yml file. This can be used to create a new environment with the same packages and name.

When downloading the environment.yml file type:
```python
conda env create -f environment.yml
```
This creates a new environment with the same packages and name.

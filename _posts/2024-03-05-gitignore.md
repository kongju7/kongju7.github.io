---
layout: post
title: ".gitignore 자동 생성하기"
subtitle: ".gitignore 자동 생성 사이트(gitignore.io)"
categories: Programming
tags: [Python, Programming, git, .gitignore, gitignore.io, toptal.com]
---

## .gitignore 자동 생성하기  
  

  
`.gitignore` 파일은 [git](https://git-scm.com/){:target="_blank"}을 활용한 버전 관리에서 제외할 파일 목록을 정리한 파일로,   
이 파일을 통해서 해당 파일이 [GitHub](https://github.com/){:target="_blank"}에 업로드되지 않도록 강제할 수 있습니다.   
  
주로 API key, 개인 정보가 포함된 데이터와 같이 외부로 유출되면 안되는 정보나 가상 환경과 같이 용량이 큰 파일 등이 여기에 포함될 수 있습니다.   
  
  
`.gitignore` 파일은 프로젝트별로 각각 수동으로 작성할 수도 있지만,   
`.gitignore` 파일을 자동 생성해 주는 사이트를 이용하면 쉽게 만들 수 있습니다.    

  
  
### 1. 먼저, [gitignore.io](https://www.toptal.com/developers/gitignore){:target="_blank"}사이트에 접속합니다.   
  
![gitignore_1](/assets/images/gitignore_1.png "gitignore_1")  
  

  
### 2. 검색창에 깃 커밋(git commit)에서 제외하고 싶은 내용을 입력합니다. 

여러 키워드를 중복해서 입력할 수도 있습니다.    
   
이 예제에서는 'Python', 'venv', 'Git' 등을 각각 입력해 추가하였습니다.  

![gitignore_2](/assets/images/gitignore_2.png "gitignore_2")  
  

   
### 3. 주요 단어를 입력한 후에 '생성' 버튼을 클릭합니다. 

그러면 `.gitignore` 파일에 들어갈 내용이 자동으로로 생성됩니다. 

![gitignore_3](/assets/images/gitignore_3.png "gitignore_3")  
  

생성된 내용을 그대로 복사해 현재 작업 중인 프로젝트 내 `.gitignore` 파일에 그대로 붙여넣기만 하면 됩니다.
그 후에 환경 변수 파일이나 개인 정보가 담긴 파일 등을 추가한다면 `.gitignore` 파일을 훨씬 쉽게 관리할 수 있게 되겠죠?  
  
 
     
참고로 위의 세 단어를 활용하여 생성된 파일은 다음과 같습니다. 

  
     
```
# Created by https://www.toptal.com/developers/gitignore/api/python,venv,git
# Edit at https://www.toptal.com/developers/gitignore?templates=python,venv,git

### Git ###
# Created by git for backups. To disable backups in Git:
# $ git config --global mergetool.keepBackup false
*.orig

# Created by git when using merge tools for conflicts
*.BACKUP.*
*.BASE.*
*.LOCAL.*
*.REMOTE.*
*_BACKUP_*.txt
*_BASE_*.txt
*_LOCAL_*.txt
*_REMOTE_*.txt

### Python ###
# Byte-compiled / optimized / DLL files
__pycache__/
*.py[cod]
*$py.class

# C extensions
*.so

# Distribution / packaging
.Python
build/
develop-eggs/
dist/
downloads/
eggs/
.eggs/
lib/
lib64/
parts/
sdist/
var/
wheels/
share/python-wheels/
*.egg-info/
.installed.cfg
*.egg
MANIFEST

# PyInstaller
#  Usually these files are written by a python script from a template
#  before PyInstaller builds the exe, so as to inject date/other infos into it.
*.manifest
*.spec

# Installer logs
pip-log.txt
pip-delete-this-directory.txt

# Unit test / coverage reports
htmlcov/
.tox/
.nox/
.coverage
.coverage.*
.cache
nosetests.xml
coverage.xml
*.cover
*.py,cover
.hypothesis/
.pytest_cache/
cover/

# Translations
*.mo
*.pot

# Django stuff:
*.log
local_settings.py
db.sqlite3
db.sqlite3-journal

# Flask stuff:
instance/
.webassets-cache

# Scrapy stuff:
.scrapy

# Sphinx documentation
docs/_build/

# PyBuilder
.pybuilder/
target/

# Jupyter Notebook
.ipynb_checkpoints

# IPython
profile_default/
ipython_config.py

# pyenv
#   For a library or package, you might want to ignore these files since the code is
#   intended to run in multiple environments; otherwise, check them in:
# .python-version

# pipenv
#   According to pypa/pipenv#598, it is recommended to include Pipfile.lock in version control.
#   However, in case of collaboration, if having platform-specific dependencies or dependencies
#   having no cross-platform support, pipenv may install dependencies that don't work, or not
#   install all needed dependencies.
#Pipfile.lock

# poetry
#   Similar to Pipfile.lock, it is generally recommended to include poetry.lock in version control.
#   This is especially recommended for binary packages to ensure reproducibility, and is more
#   commonly ignored for libraries.
#   https://python-poetry.org/docs/basic-usage/#commit-your-poetrylock-file-to-version-control
#poetry.lock

# pdm
#   Similar to Pipfile.lock, it is generally recommended to include pdm.lock in version control.
#pdm.lock
#   pdm stores project-wide configurations in .pdm.toml, but it is recommended to not include it
#   in version control.
#   https://pdm.fming.dev/#use-with-ide
.pdm.toml

# PEP 582; used by e.g. github.com/David-OConnor/pyflow and github.com/pdm-project/pdm
__pypackages__/

# Celery stuff
celerybeat-schedule
celerybeat.pid

# SageMath parsed files
*.sage.py

# Environments
.env
.venv
env/
venv/
ENV/
env.bak/
venv.bak/

# Spyder project settings
.spyderproject
.spyproject

# Rope project settings
.ropeproject

# mkdocs documentation
/site

# mypy
.mypy_cache/
.dmypy.json
dmypy.json

# Pyre type checker
.pyre/

# pytype static type analyzer
.pytype/

# Cython debug symbols
cython_debug/

# PyCharm
#  JetBrains specific template is maintained in a separate JetBrains.gitignore that can
#  be found at https://github.com/github/gitignore/blob/main/Global/JetBrains.gitignore
#  and can be added to the global gitignore or merged into this file.  For a more nuclear
#  option (not recommended) you can uncomment the following to ignore the entire idea folder.
#.idea/

### Python Patch ###
# Poetry local configuration file - https://python-poetry.org/docs/configuration/#local-configuration
poetry.toml

# ruff
.ruff_cache/

# LSP config files
pyrightconfig.json

### venv ###
# Virtualenv
# http://iamzed.com/2009/05/07/a-primer-on-virtualenv/
[Bb]in
[Ii]nclude
[Ll]ib
[Ll]ib64
[Ll]ocal
[Ss]cripts
pyvenv.cfg
pip-selfcheck.json

# End of https://www.toptal.com/developers/gitignore/api/python,venv,git
```

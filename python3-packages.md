
##  Package Management in python

   - PIP
   - Virtualenv
   - virtualenvwrapper

# Table of contents
1. [PIP](#pip)  
    1. Packages - file,download and install
    2. Manage
2. [Virtual Env](#venv)  
    1. Project specific dependencies context
3. [Virtualenvwrapper](#wrapper)  
    1. Making venv more convinient(#modular_func)  

## 1. PIP <a name="pip"></a>

Thirdparty dependency library package manager.  
Always Install pip on venv and not pollute different projects  
https://pypi.org  - list of all available libraries  
 
   - Find , Download , Install
   - Manage
   
 Check if pip is installed:  
 > pip -V  

 > pip list  

 > pip uninstall <pkg1> <pkg2>
    
 > pip show <pkgname>
 
 Better way to call pip if a machine hqs both python2 and python3  
 
 > python3 -m pip install <pkgname>  

 ### Where does the package get installed 
 
 sys.path = '','/usr/lib/python3.7','usr/local/lib/python2.7/dist-packages'
 
 > pip show <pkgname>  

 Shows the location as :   
 Location: /Library/Python/2.7/site-packages
   
 
## 2 virtualenv  <a name="venv"></a>

 Isolated context for installing packages. Always work inside venvs.  
 Contain packages,tools,python etc  
 Keep them separate from Project source code.
  
 Install the virtualenv at a system level  :
 > python -m pip install virtualenv  

To create a dump of an environment with current state of dependencies. This will create a new file called __requirements.txt__.  
> python -m pip freeze > requirements.txt  
 
To import the dependencies used in another environment to current use the requirements.txt as  
> python -m pip install -r requirements.txt  
 
#### 2.1 Projects and VirtualEnvs

What happens when we work on an external project like flask ?  
  - Requirements.txt is for your own development and sharing between co-developers.we have control over runtime env.    
  - git clone <https://github.com/pallets/flask  
  - Special file --> setup.py  
     this file has a section : install_requires[]  
     
  - If doing local development of such a project , and dont need the external flask but from my code base : 
      > python -m pip install -e flask  

  - tox.in (auto setup varying environments and run unit tests on all )  
 

## 3. VENVWRAPPER  <a name="wrapper"></a>  
 
   - User firndly wrapper of virtualenv
   - Bind projects with virtualenv
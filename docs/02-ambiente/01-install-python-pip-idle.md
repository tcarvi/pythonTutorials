# Install Python PIP IDLE

### No MAC
- `install python na versão 3.10` ( https://www.python.org/downloads/ )
```console
xcode-select --install
```
  
```console title="Para instalação inicial do pip, se não houver ainda qualquer instalação do pip!"
sudo easy_install pip
```
  
```console
sudo pip install --upgrade pip
```
  
```console
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```
  
```console
(echo; echo 'eval "$(/opt/homebrew/bin/brew shellenv)"') >> /Users/eduardosantosleal/.zprofile
```
  
```console
eval "$(/opt/homebrew/bin/brew shellenv)"
```
  
```console
source ~/.zprofile
```
  
```console
brew update
```
  
```console
brew install python3.10
```

```console
python3 --version
```

### Python Environment Variables
- PYTHONPATH
  - It has a role similar to PATH. This variable tells the Python interpreter where to locate the module files imported into a program. It should include the Python source library directory and the directories containing Python source code. PYTHONPATH is sometimes preset by the Python installer.
- PYTHONSTARTUP
  - It contains the path of an initialization file containing Python source code. It is executed every time you start the interpreter. It is named as .pythonrc.py in Unix and it contains commands that load utilities or modify PYTHONPATH.
- PYTHONCASEOK
  - It is used in Windows to instruct Python to find the first case-insensitive match in an import statement. Set this variable to any value to activate it.
- PYTHONHOME
  - It is an alternative module search path. It is usually embedded in the PYTHONSTARTUP or PYTHONPATH directories to make switching module libraries easy.

#### PATHs da instalação
- `/opt/homebrew/bin/python3.9`
  - Python path installation
- `/opt/homebrew/opt/python@3.9/libexec/bin`
  - Unversioned and major-versioned symlinks `python`, `python3`, `python-config`, `python3-config`, `pip`, `pip3`, etc. pointing to `python3.10`, `python3.10-config`, `pip3.10` etc.
- `/opt/homebrew/lib/python3.9/site-packages`
  - Path of Python packages installation: (`pip3 install <package>`).
- tkinter is no longer included with this formula, but it is available separately:
  - `brew install python-tk@3.10`
- If you do not need a specific version of Python, and always want Homebrew's `python3` in your PATH: `brew install python3`
- For more information about Homebrew and Python, see: https://docs.brew.sh/Homebrew-and-Python
- Tenha no seu PATH:
  - `/opt/homebrew/opt/python@3.10/libexec/bin`
- Instale python-tk@3.10:
```console title="Objetivo: poder usar o IDLE que vem junto com instalação do Python3"
brew install python-tk@3.10
```  

#### Teste da instalação
```console title="A retornar: Python 3.10.10"
python3.10 --version
```
  
```console title="A retornar: pip 23.0.1 from /opt/homebrew/lib/python3.10/site-packages/pip (python 3.10)"
pip3.10 --version
```
  
```console title="A retornar: Python 3.10.10"
python --version
```
  
```console title="A retornar: pip 23.0 from /opt/homebrew/lib/python3.9/site-packages/pip (python 3.9)"
pip --version
```  
  
```console title="Inicialização de IDE default do Python"
idle
```  
- From files editor, F5 re-executes the file's module.
  
```console title="Inicialização de IDE default do Python"
idle3
```  
- From files editor, F5 re-executes the file's module.

### Use um ambiente virtual, para uso de versões específicas do Python
- Crie e ative um ambiente virtual
```console
python3.10 -m venv myenv
```
  
```console
source myenv/bin/activate
```  

```console title="Para desativar o ambiente virtual do Python"
deactivate
``` 

### Instalação da dependência bpy de Blender
```console title"Instalação usando python 3.10.10 do ambiente local"
pip install bpy==3.4.0
```
  
  ou  

```console
blender -b --python-use-system-env --python-exit-code 1 --python-expr "import ensurepip; ensurepip.bootstrap(); import pip; pip.main(['install', 'bpy'])"
````  
- Esse comando: - iniciará o Blender em modo background (-b)
  - configurará a variável de ambiente PYTHONPATH para usar o ambiente do sistema (--python-use-system-env)
  - sairá com código de erro 1 em caso de falha (--python-exit-code 1)
  - e instalará o bpy usando o pip.
  
## Binário do python, usado por blender
```console
import sys
````
```console title="Retorno: /Applications/Blender.app/Contents/Resources/3.4/python"
sys.exec_prefix
````

## Para instalar dependências Python no Blender
```console
/Applications/Blender.app/Contents/Resources/3.4/python/bin/python3.10 -m ensurepip --user
````
  
```console
/Applications/Blender.app/Contents/Resources/3.4/python/bin/python3.10 -m pip install PyYAML --user
````
  
```console
dependency_path = '/Users/eduardosantosleal/.local/lib/python3.10/site-packages'
````

```console
 sys.path.append(dependency_path)
```

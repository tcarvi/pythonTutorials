# Install BPY (blender)

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

## Instalação de dependências Python para Blender
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

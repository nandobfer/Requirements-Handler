# Reqcheq

### Use this module to automatically verify and install referenced modules you are using in your project. It's a script made to ease the process of first running a program in a fresh environment.

## Instalation

```bash
pip install reqcheq
```

## Usage

```python
import reqcheq
```
reqcheq must be the first module to be imported.

Make a `requirements.txt` next to your main file, from which you are going to import reqcheq.
Each line is an item. It can have 1 or 2 words.

1st word: import name of the module. If install name is equal to import name, you can leave only this single word. (if you `import flask`, you should just add `flask` to your requirements.txt)

2nd word: install name (or non spaced string, see pysher at example) of the module. If your module is imported by a different name than it is installed you add the install name after the 1st word. (if you `import dotenv`, you should add `dotenv python-dotenv` to your requirements.txt)

Reqcheq will then automatically try to import given modules and if it fails, will try to install it with pip (windows) or pip3 (linux).

## Example
main.py
```python
import reqcheq
import pysher
import os
import json
from termcolor import colored
from dotenv import load_dotenv
from pusher import Pusher
from server_handler import connect, disconnect
load_dotenv(dotenv_path='.env')

user = ''


class terminalChat():

(...)
(...)
(...)
```

requirements.txt
```txt
pysher git+https://github.com/nlsdfnbch/Pysher.git
termcolor
pusher
dotenv python-dotenv
```

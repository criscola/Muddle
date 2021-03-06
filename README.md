# Muddle (Work in progress!)
A desktop Moodle client, because the web interface is painfully slow if you quickly need to grab a file.

![](./muddle.png)

## Configuration
On linux, copy `muddle.ini.sample` to `~/.config/muddle/muddle.ini` and add a token.
On other platforms there is no specific path implemented yet, so it will look for a file `muddle.ini` in the same folder as the executable.

## Development
This is written in Python 3 + PyQt. Virtualenv is probably the most comfortable way to work.
If you don't know how to set up a venv, type in you terminal (while in the project directory):
```bash
muddle $ python3 -m venv venv
muddle $ source ./venv/bin/activate
muddle $ pip3 install -r requirements.txt
muddle $ ./muddle --gui
```

The code is a bit garbage, as I hacked it toghether in one morning, though I've tried to clean it up a bit.

### Coding style

Use PEP8 except where Qt bindings are used (`gui.py`). To check use
```
$ pep8 --show-source --ignore=E501 moodle.py muddle.py <more files...>
```

### Compilation / Release
To create an executable you need PyInstaller, you can get it with
```
$ pip3 install pyinstaller
```
And then run
```
$ pyinstaller --onefile muddle
```
The computer will think for a while, and then once its done there will be a single executable `dist/muddle`.

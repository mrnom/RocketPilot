# 🚀 RocketPilot

Cross-platform tool for functional GUI testing of Qt applications based on Canonical Autopilot project.

## Installation

### Ubuntu
```
sudo apt-get install python3 python3-pyqt5 python3-dbus.mainloop.pyqt5 -y
sudo apt-get install libxpathselect-dev -y
sudo apt-get install libdbus-1-dev libdbus-glib-1-dev -y

virtualenv --system-site-packages -p python3 .venv

source .venv/bin/activate

pip install -e . 
```
### OS X

```
brew install python3 pkgconfig dbus dbus-glib pyqt5
brew services start dbus

virtualenv --system-site-packages -p python3 .venv

source .venv/bin/activate

pip install -e . 
```

## Introspect application
1. Install pyqt5
2. *OSX ONLY*: 
```
brew install qt5
cp bin/osx/dbus/mainloop/* .venv/lib/python3.6/site-packages/dbus/mainloop/
```
3. Run vis tool: `rocketpilot-vis APPNAME`

#### Troubleshooting
In case of `ImportError: No module named 'dbus.mainloop.pyqt5'`:

1. Locate `dbus.mainloop.pyqt5` with:
```
dpkg -L python3-dbus.mainloop.pyqt5
```
2. Add directory path to [`$PYTHONPATH`](https://docs.python.org/3.5/using/cmdline.html#envvar-PYTHONPATH):

Presuming that `dbus.mainloop.pyqt5` path is `/usr/lib/python3/dist-packages/dbus/mainloop/pyqt5.cpython-35m-x86_64-linux-gnu.so`:
```
export PYTHONPATH=/usr/lib/python3/dist-packages:$PYTHONPATH
```

# LLM RasPi5 Robot

## Demos

<img height="600" alt="image-2_nd-robot" src="https://github.com/user-attachments/assets/b708cdbe-721c-4886-b7f4-9bfd07937729" />
<img height="600" alt="Untitled 2776543" src="https://github.com/user-attachments/assets/c12f674a-8f56-45e3-850b-414f6956414e" />


## How it's made

## Description

## Technical Overview

### Robot Components

### Computer Components

## Setup

### Raspberry Pi 5

With the touchscreen connected, and after setting up the Pi upon bootup for the first time, including:

- Hostname
- User and password
- Wireless LAN SSID and password
- Locale settings

Enable SSH, I2C and Remote GPIO, using the touchscreen:

- Pi icon → Preferences → Raspberry Pi Configuration → Interfaces → SSH (enable)
- Pi icon → Preferences → Raspberry Pi Configuration → Interfaces → I2C (enable)
- Pi icon → Preferences → Raspberry Pi Configuration → Interfaces → Remote GPIO (enable)

Or using the Terminal and a keyboard:

```
sudo raspi-config
```

- Interface Options -> SSH -> Yes
- Interface Options -> I2C -> Yes
- Interface Options -> Remote GPIO -> Yes

Then install `picamera2` and `opencv` with `apt install`:

```
sudo apt update
sudo apt install -y python3-picamera2
sudo apt install -y python3-opencv
sudo apt install -y opencv-data
sudo apt install -y portaudio19-dev
```

Make (and enter) a project directory:

```
cd
mkdir Pi5Robot
cd Pi5Robot
```

Create a virtual environment:

```
python3 -m venv venv
```

Activate it:

```
source venv/bin/activate
```

And install the rest of the dependencies with `pip`:

```
pip install adafruit-circuitpython-pca9685
pip install adafruit-circuitpython-motor
pip install deepface
pip install tf-keras
pip install facenet-pytorch
pip install rpi-lgpio
pip install mediapipe
pip install pyaudio
pip install websockets
```

Make the apt-installed libraries accessible from within the virtual environment:

```
echo "/usr/lib/python3/dist-packages" > $(python -c "import site; print(site.getsitepackages()[0])")/system_packages.pth
```

Downgrade `numpy` because 2.0.0 seems incompatible:

```
pip install "numpy<2.0.0"
```

And this should now work:

```
python -c "from picamera2 import Picamera2; print(Picamera2)"
```

### Computer

## Usage

## Quick Communication Diagrams!

## License

[Missing license]

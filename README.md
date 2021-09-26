# Kinect_V1_Ubuntu_18
25-septiembre-2021

Instalación de drivers de Kinect v1 on ubuntu 18
Me basé en:

Setting up Kinect for programming in Linux (part 1)
https://www.kdab.com/setting-up-kinect-for-programming-in-linux-part-1/

Pero en la parte de instalación de Java
# Tomé la referencia de:
https://www.digitalocean.com/community/tutorials/como-instalar-java-con-apt-en-ubuntu-18-04-es

# Entonces, apliqué los siguientes comandos:

```
mkdir KinectLibs 
cd KinectLibs
git clone https://github.com/OpenKinect/libfreenect
git clone https://github.com/OpenNI/OpenNI
git clone https://github.com/avin2/SensorKinect

sudo apt-get install cmake freeglut3-dev pkg-config build-essential libxmu-dev libxi-dev libusb-1.0-0-dev python
sudo add-apt-repository "deb http://archive.canonical.com/ lucid partner"
sudo apt update
sudo apt-get install default-jre
java -version
sudo apt-get install default-jdk
javac -version
sudo apt-get install openjdk-8-jdk
java -version
sudo apt install openjdk-11-jdk
sudo apt install openjdk-11-jre

sudo apt-get install doxygen mono-complete graphviz
```

# in libfreenect directory, in the KinectLibs dir
```
cd libfreenect
mkdir build
cd build
cmake ..
make
sudo make install
sudo ldconfig /usr/local/lib/
 
sudo chmod a+rw /dev/bus/usb//

lsusb | grep Xbox
# Conectar el Kinect v1
sudo freenect-glview
```

# Robotics - UNAL - Primeros Pasos ROS

[TOCM]


## Requirements
Modern robotics relies on the versatile middleware known as ROS (Robotic Operative System). Some of the most useful tools in robotics run in this framework. Learning ROS could lead to insanity (jikes...) but fortunately with time and patience (tons of), all of you young padawans will master the power of ROS.

### Linux
**ROS runs on linux, period.**

There are a couple of ways to run Linux:
- Native installation :alien: (Recommended, almost mandatory)
- Virtual machine :nail_care: (Almost everything works, but intensive GPU apps will crash)
- Docker :whale2: (Too new)
- Windows subsystem for linux :trollface: (Fancy, but it has some compatibility issues, and has GUI only in Windows 11)

## Configuracion con máquina virtual

 En este caso se asume que el sistema operativo linux así como ROS es instalado sobre una máquina virtual. 
 Existen diferentes herramientas para virtualizar escritorios  como son: virtual box, WMare o paralells.  En este caso se    ha seleccionado la herramienta de WM-ware.
 
 
 
 
 VMware es un sistema de virtualización por software que proporciona un ambiente de simulación de la ejecución de varios ordenadores dentro de otro de manera simultánea. 
 
 El software de virtualización crea una capa de abstracción sobre el hardware de la computadora que permite que los elementos de hardware de una sola computadora (procesadores, memoria, almacenamiento y más) se dividan en múltiples computadoras virtuales, comúnmente llamadas máquinas virtuales (VM). Cada máquina virtual ejecuta su propio sistema operativo (SO) y se comporta como una computadora independiente, aunque se ejecuta en una parte del hardware informático subyacente existente.

Como se puede imaginar, la virtualización permite utilizar el hardware de forma más eficiente y ofrece un mayor retorno de inversión del hardware de una empresa. También permite a los proveedores de la nube, ya sea pública o privada, prestar servicios a más usuarios con su hardware informático físico existente.

Virtualización de desktop
VMware es un hipervisor basado en servidor bien establecido, pero también vende software que virtualiza los sistemas operativos de desktop. Esta sección abarca parte de ese software y cómo funciona.

¿Qué es VMware Workstation?
VMware Workstation incluye hipervisores de tipo 2. A diferencia de un hipervisor de tipo 1, que reemplaza el SO subyacente por completo, un hipervisor de tipo 2 se ejecuta como una aplicación en el SO de desktop y permite a los usuarios de desktop ejecutar un segundo SO encima de su SO principal (host).

VMware Workstation [link](  https://www.vmware.com/es/products.html "link") viene en dos versiones:

[![wm-vare.png](https://i.postimg.cc/C5kyNXkL/wm-vare.png)](https://postimg.cc/1VmYRWvL)

Workstation Player  es una versión sin costo que admite un único sistema operativo invitado.
Workstation Pro  admite varios sistemas operativos invitados y se integra con las herramientas de gestión de virtualización empresarial de VMware. Y WMware fusion es la aplcacion disponible para mac-OS.

Solo hay una cosa mejor que tener un segundo SO en su computadora desktop: tener un segundo SO que pueda intercambiar datos con el primero. Ahí es donde entra en juego VMware Tools. Es una parte fundamental de cualquier entorno de VMware Workstation. Permite que el SO invitado que se ejecuta dentro del hipervisor de tipo 2 funcione mejor con el SO host. 
 
 Paso 1: Primero se debe descargar wm-ware worstation player [link](https://www.vmware.com/es/products/workstation-player.html "link").
 
 Paso 2: Haz clic en el botón 'Descargar VMware Workstation player' para iniciar sesión en el portal con los datos de acceso que recibiste por correo electrónico.

 
 Paso 3: Abre el archivo de instalación de VMware Workstation player.
 Paso 4: Haz clic en Next.
 Paso 5: Acepta el acuerdo de licencia.
 Paso 6: Elige la ubicación deseada para la instalación y haz clic en Next.
 Paso 7: Marca las opciones si lo deseas y haz clic en Next.
 Paso 8: Haz clic en Next.
 Paso 9: Haz clic en Install. La duración de la instalación depende de la potencia de tu ordenador.


 
 ## Instalacion de linux en maquina virtual VMware
 
 Inicie VMware Workstation.
Haga clic Nueva máquina virtual.
Seleccione el tipo de máquina virtual que desea crear y haga clic en Home:
[![wm-01.png](https://i.postimg.cc/nVGCYhYm/wm-01.png)](https://postimg.cc/bddyq85Y)

Nota: Su elección depende parcialmente de la versión de hardware que desee que tenga la máquina virtual. 6).
Personalizado: Esto le ofrece una opción para crear una máquina virtual y elegir su compatibilidad de hardware. Puede elegir entre Workstation 16.x, Workstation 15.x y Workstation 14.x .
Típica: Esto crea una máquina virtual que tiene la misma versión de hardware que la versión de Workstation que está utilizando. Si utiliza Workstation 16.x, crea una máquina virtual con la versión 16 del hardware.

Haga clic en Siguiente.
Seleccione el sistema operativo invitado (SO) y, a continuación, haga clic Soy. Puede instalar el sistema operativo mediante:
Un disco instalador (CD/DVD)
Un archivo de imagen de disco (ISO) del instalador
[![wm-02.png](https://i.postimg.cc/nzHtHpj8/wm-02.png)](https://postimg.cc/yJrGjqyn)
 
Haga clic en Siguiente.

Cree un nombre de usuario y una contraseña.

Introduzca el nombre de una máquina virtual y especifique una ubicación para guardar los archivos de la máquina virtual. 

Luego:
Establezca el tamaño de disco de la máquina virtual, seleccione si desea almacenar el disco virtual como un único archivo o dividir el disco virtual en archivos de 2 GB y haga clic en Máquelo .
[![wm-03-a.png](https://i.postimg.cc/YqcB96mf/wm-03-a.png)](https://postimg.cc/SjGv1zdJ)
Compruebe el resto de opciones de configuración de la máquina virtual:
Memoria : permite cambiar la cantidad de memoria asignada a la máquina virtual.
Procesadores: cambie el número de procesadores, el número de núcleos por procesador y el motor de virtualización.
CD/DVD: con una configuración avanzada donde puede elegir entre SCSI, IDE.
Adaptador de red: configúrelo en modo de puente, NAT o solo host, o personalice dónde puede elegir entre 0 y 9 adaptadores.
Controlador USB.
Tarjeta de sonido.
Pantalla : habilite los gráficos 3D.
[![wm-03.png](https://i.postimg.cc/9fbnYTMS/wm-03.png)](https://postimg.cc/DWW62S1d)
Haga clic en Finalizar.
Cuando la máquina virtual está encendida, se inicia la VMware Tools de datos. Se le solicitará que reinicie la máquina virtual una vez que se complete la instalación de Tools.
 
 
 

## Instalación con linux nativo
For this course, the Linux of choice is [Ubuntu 20.04 LTS](https://ubuntu.com/download/desktop "Ubuntu 20.04 LTS"). In this [link](https://www.tecmint.com/install-ubuntu-20-04-desktop/ "link") you will find a good installation tutorial.

<p align="center">
<img src="https://images.wondershare.com/recoverit/article/11/linux-vs-windows-8.jpg" alt="drawing" width="600"/>
</p>





### ROS

<img src="https://www.ros.org/imgs/logo-white.png" alt="drawing" width="300"/>

Once Linux has been installed, it's ROS time. For this course, ROS Noetic will be used. The installation steps for ubuntu are [here](http://wiki.ros.org/noetic/Installation/Ubuntu "here"), for other Linux distros look [here](http://wiki.ros.org/noetic/Installation "here").

In any case, I left the instructions in this repo as well. Just open a new terminal and run the following commands:

```console
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu $(lsb_release -sc) main" > /etc/apt/sources.list.d/ros-latest.list'
sudo apt install curl
curl -s https://raw.githubusercontent.com/ros/rosdistro/master/ros.asc | sudo apt-key add -
sudo apt update
sudo apt install ros-noetic-desktop-full
echo "source /opt/ros/noetic/setup.bash" >> ~/.bashrc
source ~/.bashrc
sudo apt install python3-rosdep python3-rosinstall python3-rosinstall-generator python3-wstool build-essential
sudo apt install python3-rosdep
sudo rosdep init
rosdep update
```
If you use zsh instead of bash, change the commands 6 and 7 to
```console
echo "source /opt/ros/noetic/setup.zsh" >> ~/.zshrc
source ~/.zshrc
```
Please visit the [Frobs_RL](https://github.com/jmfajardod/frobs_rl "Frobs_RL") repo, leave a star and salute FajardROS (One of the only few guys that has master ROS).

### Recommended apps/packages
After years of trying learning ROS, I have compiled some useful tools, some of them have been suggestions, some have been my own discovery.

#### VSCode
Thanks to Microsoft for one of the best code editors in the world. I strongly recommend it. [Here](https://code.visualstudio.com/docs/setup/linux "Here") there is the official way to install VScode on Ubuntu.

<p align="center">
<img src="https://assets-global.website-files.com/6080d45b6168d4415fe5cbd7/608774655b7a0acbaf55de02_1589356832-code-editor-report-card.png" alt="drawing" width="700"/>
</p>
<p align="center">
<img src="https://assets-global.website-files.com/6080d45b6168d4415fe5cbd7/608774658fa197d2436608e9_1589356866-vscode-ranking.png" alt="drawing" width="700"/>
</p>

#### Kitty
Linux terminal is really powerful, when you master the shell you are gonna look kinda hackerish. Nonetheless, the default terminal in Ubuntu could be constrained. FajardROS found Kitty, since then I started loving cats. [Link](https://sw.kovidgoyal.net/kitty/binary/ "Link") to official page, and link for the installation [guide](https://connectwww.com/how-to-install-kitty-on-ubuntu-kitty-terminal-emulator/61186/ "guide").

<p align="center">
<img src="https://sw.kovidgoyal.net/kitty/_static/kitty.svg" alt="drawing" width="250"/>
<img src="https://user-images.githubusercontent.com/6448975/33396524-0dce2240-d549-11e7-9674-be7f006e712f.png" alt="drawing" width="400"/>
</p>

#### Catkin build
Once you install ROS you realize that catkin is a package compiler (kinda). *catkin_make* compiles the entire workspace, there is no harm if you have a couple of light packages, but if you have a lot of packages in one workspace, I recommend you to install *catkin_build*. It will allow compiling the packages separately. Open a terminal (hopefully kitty) and run:

```console
sudo sh -c 'echo "deb http://packages.ros.org/ros/ubuntu `lsb_release -sc` main" > /etc/apt/sources.list.d/ros-latest.list'
wget http://packages.ros.org/ros.key -O - | sudo apt-key add -
sudo apt-get update
sudo apt-get install python3-catkin-tools
```

### Git
If you are reading this, you will probably have some experience with repositories,  in the case you do not have it in your machine, just open a terminal and run:

```console
sudo apt update
sudo apt install git
git --version
```
<p align="center">
<img src="https://techies-world.com/wp-content/uploads/2016/08/1color-lightbg@2x.png" alt="drawing" width="500"/>
</p>

## Python and C++
Fortunately, python3 interpreter and C compiler are preinstalled on Linux, so no worries it is not Windows.

<p align="center">
<img src="https://i.postimg.cc/RCJ4QfRf/Screenshot-from-2022-03-08-21-10-26.png" alt="drawing" width="600"/>
</p>

## CopyQ
Clipboard manager.

![](https://i.postimg.cc/1RK9KRCF/Screenshot-from-2022-03-18-17-24-10.png)

```console
sudo add-apt-repository ppa:hluk/copyq
sudo apt update
sudo apt install copyq
```

## Tree
Shows the hierachy og the linux files in a graphical way.

![](https://i.postimg.cc/zvdYYB6P/Screenshot-from-2022-03-18-17-25-20.png)

```console
sudo apt install tree
```

## Locate
Simplifies terminal searches
```console
sudo apt install locate
```

------------

If I found more tools, I will add them here. If you find something interesting don't hesitate of letting me know.

------------

## Useful commands - Linux terminal

 - **pwd:** Shows the current folder.
```console
pwd
```
 - **clear:** Clenas the terminal.
```console
clear
```
 - **ls:** Lists folder content (some).
```console
ls
```
- **ll:** Lists folder content (all).
```console
ll
```
- **touch:** Creates a file 
```console
touch prueba.txt
```
- **mkdir:** Creates a new folder
```console
makdir carpeta
```
 - **cd + path:** Changes the path to a certain location
```console
cd Downloads
```
- **cd ..:** Jumps to the previous folder
```console
cd ..
```
 - **~:** Home folder.
```console
cd ~
```
You can also go to the Home folder using cd alone
```console
cd 
```
- **cat:** 
```console
cat prueba.txt
```
- **gedit:** open a text file with the text editor gedit.
```console
gedit prueba.txt
```
- **:** 
- **rm:** deletes a file.
```console
rm prueba.txt
```

- **cp:** copy a file or a directory 
```console
cp prueba.txt prueba_backup.txt```
```

- **mv:** it is used to move files to another directory 
```console
mv prueba.txt /tmp
```

and it is also used to rename files.
```console
mv prueba.txt prueba2.txt
```

- **:** 
```console

```

**Useful tricks:**
- Ctl + Atl + t opens a new terminal.
- Ctl + l cleans the terminal
- Ctl + c ends the terminal's process
- Ctl + shift + c copies from the terminal
- Ctl + shift + v pastes to the terminal
- Ctl + r reverse search
- Tab autocompletes
- Up and down arrows allows moving to past commands

------------

## Catkin workspace

1. You must first verify that the catkin tools are installed. In other wise,  Visit [here](https://catkin-tools.readthedocs.io/en/latest/installing.html#installing-on-ubuntu-with-apt-get). 

2. It is an especial place where ROS packages are gonna be located and modified (your owns packages). You can have as many *workspaces* as you want, but for now let's create just one:

```console
cd ~
mkdir catkin_ws
cd catkin_ws
mkdir src
catkin build
```
The previous lines create a folder named *catkin_ws*, it is the actual *workspace*. The last line just compile all the ws. *catkin build* could be replaced by *catkin_make*, but remember it implies to compile the entire ws, not just the package you select.

------------

# Turtlesim

=============

Now the real businesses.

Clone the *hello_turtle* repo from [here](https://github.com/felipeg17/hello_turtle). It's a sort of hello world in the ROS community. Some changes have been added, but don't worry, during the class you will learn most of the concepts.

```console
cd catkin_ws/src
git clone https://github.com/felipeg17/hello_turtle.git
```
Important: I am assuming you already created the catkin_ws.

-----------

### Run ROSCORE and Turtlesim_node

First, open 3 terminals (if you use Kitty press ctrl + shift + enter three times) and run:

**First terminal**
```console
roscore
```
**Second terminal**
```console
rosrun turtlesim turtlesim_node
```
![alt text](https://i.postimg.cc/j2TbKyPc/Screenshot-from-2022-03-04-12-10-27.png)

You will get something like this:
![alt text](https://i.postimg.cc/FsD45dRb/Screenshot-from-2022-03-04-12-10-50.png)
If you are lucky enough, you will get a better turtle icon than me.

### Nodes and Topics
In the third terminal run:

**Third terminal**
```console
rostopic list
rosnode list
```
![alt text](https://i.postimg.cc/bwrjzyD7/Screenshot-from-2022-03-04-12-11-17.png)

You will see all topics and nodes running. Notice that the topics related to the turtle simulation have the */turtle1* namespace.

Now in the same terminal run:

**Third terminal**
```console
rosrun turtlesim turtle_teleop_key
```
It will allow you to move the turtle around using the keys.

Open a new terminal and run:

**Fourth terminal**
```console
rqt_graph
```
![alt text](https://i.postimg.cc/0NJRwVCZ/Screenshot-from-2022-03-04-12-13-44.png)

A graphical visualization of the topics and nodes will appear, It shows the interconnections between them.

### Pose subscription
In the fourth terminal end the *rqt_graph* and run:
```console 
rostopic echo /turtle1/pose
```
![alt text](https://i.postimg.cc/XYkcjCQJ/Screenshot-from-2022-03-18-17-10-58.png)

It will subscribe to the */turtle1/pose* topic that uses the *turtlesim/Pose*, which consists of 5 float32 that describes the turtle pose and velocities. Just in case check the message info.

![](https://i.postimg.cc/xjmmjmd2/Screenshot-from-2022-03-18-17-11-24.png)

### cmd_vel publishing
Now finish the sub process an type:
```console 
rostopic pub -1 /turtle1/cmd_vel geometry_msgs/Twist "linear:
  x: 1.0
  y: 0.0
  z: 0.0
angular:
  x: 0.0
  y: 0.0
  z: 1.0" 
```
![alt text](https://i.postimg.cc/kgmvPcNz/Screenshot-from-2022-03-18-17-14-04.png)

The turtle moves.....so cool.

**Tip:** Check the *cmd_vel geometry_msgs/Twist* using *rosmsg info*.

------------
## hello_turtle package

The hello_turtle package somehow summarizes the previous concepts. It introduces the ROS-package basics.

Firstly look at the files and dirs structure:
![alt text](https://i.postimg.cc/tTNR0k7q/Screenshot-from-2022-03-04-13-47-28.png)

It resembles the ROS recommended structure.

![alt text](https://miro.medium.com/max/1400/0*vfNM1mbkhUpvK-nW.png)

The package consists of: 
- **CMakelist.txt:** A set of special instructions to the compiler (more details in class).
- **package.xml:** An xml file to specify the package dependencies.
- **/config:** A directory to store all configuration files. There is a new standard in ROS called *.yaml* (we will call it *yamile*) which is basically an *xml* with more functionalities.
- **/launch:** This folder stores all the launch files (more details above).
- **/scripts:** This dir stores all the package executables (mainly python one). 
- **/src:** Where all C stuff is stored.

There are a couple of missing folders, for that I **strongly** suggest (*command*) to follow these ROS tutorials:
 - [**ROS packages**:](http://wiki.ros.org/ROS/Tutorials/CreatingPackage) Shows how a package is created.
 - [**ROS packages 2**:](http://wiki.ros.org/ROS/Tutorials/BuildingPackages): Shows how to actually build the package.
 - [**ROS messages and services**:](http://wiki.ros.org/ROS/Tutorials/CreatingMsgAndSrv) Shows how to create new ROS msgs and ROS srv, there you will learn the purpose of the *msg* and *srv* dirs.
 - [**ROS subs and pubs**:](http://wiki.ros.org/ROS/Tutorials/WritingPublisherSubscriber%28python%29) Shows how to write a subscriber and publisher in Python.
 - [**ROS service running**:](http://wiki.ros.org/ROS/Tutorials/WritingServiceClient%28python%29): Shows how to write a pair client and service in Python.

Before continuing, close all terminal and ROS processes. In a new clean terminal run:
```console
cd ~/catkin_ws/src
git clone https://github.com/felipeg17/hello_turtle.git
```
It cloned the *hello_turtle* package in the *catkin_ws*.

```console
cd ~/catkin_ws/
catkin build hello_turtle 
```
If you installed *catkin tools*

Or
```console
cd ~/catkin_ws/
catkin make
```
If you want to compile all packages

You will get something like this: (Ignore the warnings, it's just cmake crying)
![atl text](https://i.postimg.cc/Xqm40zKC/Screenshot-from-2022-03-04-14-22-27.png)

Now we source the changes:
```console
cd ~/catkin_ws/
source devel/setup.bash
```

Moment of true, run this command:
```console
roslaunch hello_turtle turtle.launch
```
![alt text](https://i.postimg.cc/hPXVbQfy/Screenshot-from-2022-03-04-14-29-48.png)
But what just happened?....it run the roscore, the turtlesim, and all that stuff with just one command, that's the power of launch files.

### The launch file
It condense multiple commands in just one executable file. Let's take a look:
```xml
<launch>
  <node
    pkg="turtlesim" 
    name="sim" 
    type="turtlesim_node">
    <rosparam file="$(find hello_turtle)/config/params.yaml" command="load" ns=""/>
  </node>
</launch>
```
It creates a node from the *turtlesim* package with the name *sim*, additionally, it loads some parameters stored in the *config/params.yaml* (spoiler: those params simply change the canvas color). The latter is really important because a lot of packages load info from different configuration files, so remember this syntax. At the same time the launch file *launches* *roscore* if it is needed.

The other parts of the packages will be treated in class, so try to attempt.

------------

`<Lab guide>` : https://drive.google.com/file/d/19UOE_eI-ob2ZymNHWFrYgrxLQfgOon43/view?usp=sharing 

------------

**Acknowledgments:**

 - Jose Manuel Fajardo
 - Sebastian Realpe 
 - Hans Milos Toquica

This repo has taken a lot of effort, so consider to leave a star, [follow me](https://felipeg17.github.io/index.html), and if you feel generous I have [Paypal](https://paypal.me/fegonzalez17?country.x=CO&locale.x=en_US) (just kidding).

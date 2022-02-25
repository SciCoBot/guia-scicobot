# Começo Rápido Raspberry Pi

Neste arquivo estarão o passo a passo utilizado por @OtaviodaCruz para configuração do ambiente Rapsberry Pi.

## Login

- Login padrão ubuntu server após instalação:
  - login: ubuntu 
  - senha: ubuntu

## Imagem Ubuntu Server

- [Raspberry Pi Imager](https://www.raspberrypi.com/software/);
- Baixar ubuntu server 20.04 arm64 (64 bits);

## Acesso Wi-Fi

- Vá em: etc/netplan/50-cloud-init.yaml;
- Use o arquivo [50-cloud-init.yaml](https://github.com/SciCoBot/guia-scicobot/blob/abd63700f053e7ae5ec405d8a58c2857801e833e/50-cloud-init.yaml) como referência;

## PuTTY PC

A partir daqui, é utilizada uma comunicação SSH com o raspberry por um computador, devido a sua facilidade. Para isso, utilizou-se o [PuTTY](https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html).

## Atualização do sistema

- sudo apt-get update
- sudo apt autoremove
- sudo apt upgrade

## Instalação ROS 2

- Há algumas formas de instalar, foi utilizada a [instalação via pacotes debian](https://docs.ros.org/en/foxy/Installation/Ubuntu-Install-Debians.html). Onde em "Install ROS 2 packages" é utilizado o ROS-Base.
- Pode ser que o rosdep não seja instalado utilizando esse tipo de instalação. Para resolver esse poblema pode ser feita a instalação manual, como  é feita [aqui](https://docs.ros.org/en/foxy/Installation/Ubuntu-Development-Setup.html):
```
sudo apt update && sudo apt install -y \
  build-essential \
  cmake \
  git \
  libbullet-dev \
  python3-colcon-common-extensions \
  python3-flake8 \
  python3-pip \
  python3-pytest-cov \
  python3-rosdep \
  python3-setuptools \
  python3-vcstool \
  wget
```
- Para iniciar um ambiente de trabalho ros, execute:
```
source /opt/ros/foxy/setup.bash
```
## Micro-ROS

- [Aqui](https://micro.ros.org/docs/tutorials/core/teensy_with_arduino/) tem um bom tutorial, onde a parte do agente micro-ROS pode ser seguida para o Raspberry.



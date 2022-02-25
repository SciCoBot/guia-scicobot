# 

Neste arquivo estarão o passo a passo utilizado por @OtaviodaCruz para configuração do ambiente Rapsberry Pi.

## Login

- Login padrão ubuntu server após instalação:
  - login:ubuntu 
  - senha: ubuntu

## Imagem

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

## Instalar ROS 2



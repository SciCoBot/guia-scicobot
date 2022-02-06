# Guia Scicobot

# Biblioteca para sensor ultrassônico e Arduino Due
[![platform badge](https://img.shields.io/badge/platform-Arduino-orange.svg)](https://github.com/arduino)
[![GitHub](https://img.shields.io/github/license/mashape/apistatus.svg)](https://github.com/SciCoBot/led_debug/blob/main/LICENSE)

## Conteúdo

- [Sobre](#sobre)
- [Comandos Básicos](#comandos-básicos)
- [Modo de Usar](#modo-de-usar)
- [Como Utilizar](#como-utilizar)
- [Implementaçõs Futuras](#implementaçõs-futuras)

## Sobre

É comum a necessidade de uma plataforma robótica para averiguar hipóteses de uma pesquisa científica na prática. Assim sendo, se faz necessária a aquisição ou montagem de um
robô, contudo, a construção pode ser complexa ou não estar diretamente relacionada ao escopo do estudo (como a implementações de funcionalidades de software), o que acarreta em
perda significativa de tempo, enquanto que a compra pode ser frustrada pelos altos preços.

Assim sendo, Scicobot é um projeto que define uma arquitetura base, tanto física quanto de software (principalmente este), que tem como objetivo servir como ferramenta de pesquisa para temas relacionados a robótica, principalmente para emprego na Universidade Federal de Uberlândia, campus Patos de Minas. A plataforma é idealizada para ser de baixo custo, *open source*, modular e expansivo, sendo baseado em ROS 2, micro-ROS, Arduino Due e Raspberry Pi.

Tem-se como objetivo geral disponibilizar, ao logo do tempo, vários tipos de robôs que utilizem a base estabelecida de hardware e software, mas possuam funcionalidades e/ou componetes distintos

## Hardware Base

Esse seria o hardware base proposta:

<p align="center">
  <img src="https://user-images.githubusercontent.com/30325754/152666972-2c329d15-49e5-4ed6-95e8-38f4ad7dc6f3.png"/ height="300" width="350">
</p>

É claro, no entanto, que uma arquitetura simples como essa nem anda. Então, eu diria que para realmente ser considerado como uma plataforma básica precisaremos adicionar uma ponte H para os motores (e uma bateria), como:

<p align="center">
  <img src="https://user-images.githubusercontent.com/30325754/152667042-5b9511d1-3b15-4178-bb42-40f96cea1448.png"/>
</p>

No entanto, não deseja-se limitar o tipo de ponte H utilizada ou mesmo a bateria, por isso esses tipos de componentes não constam no hardware base proposto, mas são necessários em algum momento.

Além disso, eu diria, ainda, que o cabo TTL é um componente de suma importância a você que deseja/adora debugar, ele vai te ajudar bastante nesse sentido, então se sinta a vontade para comprar algo como o que eu uso:

<p align="center">
  <img src="https://user-images.githubusercontent.com/30325754/152667165-77a39467-b0da-4e57-9f75-6846f6769b11.png"/>
</p>

## Arquitetura Base de Software 

Quero salienta que o principal aqui é a arquitetura proposta, ela pode nãos ser tão ótimizada, mas para aqueles que pretendem implementar uma versão de Scicobot é importante que se atentem a forma de implementação, já que, idealmente, a estrutura dos demais robôs devem se manter. Isso irá facilitar o entendimento de terceirto, a documentação e o reuso.

A lógica da arquitetura de software base se divide em duas vertentes. A fim de ficar mais módular, preferi implementar a lógica dos componentes e do middleware separadas. Onde, geralmente, há uma biblioteca para o componente a nível de leitura, configuração e impressão, como por exemplo uma biblioteca para  aquisição de informação de um sensor ultrassônico. E uma biblioteca para que esse componente interaja no mundo ROS 2.

A seguir tem-se duas imagens da arquitetura de Scicobot 1, como exemplo. A primeira, descreve as bibliotecas dos componentes:

<p align="center">
  <img src="https://github.com/SciCoBot/guia-scicobot/blob/main/images/topologia_bibliotecas_sensores.png?raw=true"/>
</p>

E a segunda, as bibliotecas referentes ao middleware, que nada mais é do que uma impelmentação de micro-R0S-arduino:

<p align="center">
  <img src="https://user-images.githubusercontent.com/30325754/152667228-b227ccd9-c0b9-48ee-ba50-929ed0f9bb27.png"/>
</p>

Nota: aqui ainda há muito o que melhorar, apesar e funcional, acredito, ainda, que haja uma estrutura mais fácil de trabalhar. Por isso ainda quero melhorar muitas coisas nessa parte, então, façam sugestões. 

## Scicobot 1

Este é o Scicobot 1, um prototipo físico inicial, criado para avaliar a estrutura de código desenvolvida, a partir de ferramentas como: ROS 2, micro-ROS-arduino

<p align="center">
  <img src="https://github.com/SciCoBot/guia-scicobot/blob/main/images/scicobot_real.png?raw=true"/>
</p>

Como pode-se perceber das imagens de spoiler nas sessões anteriores, Scicobot 1 possui os seguintes componentes: 

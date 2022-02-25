
## Arduino IDE
- baixar e instalar o [arduino IDE](https://www.arduino.cc/en/software);
- instalar o suporte para a placa arduino DUE;

## micro_ros_arduino
- Siga o tutorial de (https://github.com/micro-ROS/micro_ros_arduino), começando por "How to use the precompiled library";
  - Obs.: Baixe versão micro_ros_arduino conforme ROS instalado (como o foxy): https://github.com/micro-ROS/micro_ros_arduino/releases
- E, depois, "Patch Arduino board for support precompiled libraries", onde utilizei:

```
export ARDUINO_PATH=/home/*username*/.arduino15/packages/arduino
cd $ARDUINO_PATH/hardware/sam/1.6.12/
curl https://raw.githubusercontent.com/micro-ROS/micro_ros_arduino/galactic/extras/patching_boards/platform_arduinocore_sam.txt > platform.txt
```
Sendo *username* o nome do usuário no sistema. Aqui é importante salientar que podem haver diferenças, o caminho ARDUINO_PATH nem sempre vai ser nesse formato, mas deve ser algo parecido.

- 

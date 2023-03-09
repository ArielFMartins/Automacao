#!/bin/bash

sudo su

until [ "$vpn" = "s" ]
do
  echo "Sua VPN esta conectada? Digite: S ou N"
  read vpn
done

echo ##########Instalando o Net-tools##########
sudo apt install net-tools

echo ##########Atualizando o Linux##########
sudo apt update

echo ##########Rodando Upgrade############
sudo apt upgrade

echo ############Excluindo o nosso controle de inventario############
cd /opt/LansweeperAgent/
sudo ./uninstall

echo ############Baixando nosso Controle de Inventário############
sudo wget https://cdn.lansweeper.com/build/lsagent/LsAgent-linux-x64_9.1.0.2.run
sudo chmod +x LsAgent-linux-x64_9.1.0.2.run


echo ############Instalando nosso Controle de Inventário############
sudo ./LsAgent-linux-x64_9.5.0.2.run --server 192.168.10.15 --port 9524 --mode unattended

until [ "$reboot" = "s" ]
do
  echo "Podemos reiniciar sua máquina? Digite: S ou N"
  read reboot
done

reboot

# Práctica: Configuración de Servidor DHCP con Vagrant

Este repositorio contiene una práctica para configurar un servidor DHCP y dos máquinas cliente utilizando Vagrant y Ubuntu 18.04 (bionic64). El objetivo es aprender a instalar y configurar un servidor DHCP, así como gestionar direcciones IP dinámicas y estáticas en un entorno controlado de red privada.

## Contenidos

1. [Descripción General](#descripción-general)
2. [Requisitos](#requisitos)
3. [Configuración del Entorno](#configuración-del-entorno)
4. [Configuración del Servidor DHCP](#configuración-del-servidor-dhcp)
5. [Configuración de los Clientes](#configuración-de-los-clientes)
6. [Asignación de IP Fija Basada en MAC](#asignación-de-ip-fija-basada-en-mac)
7. [Comandos Útiles](#comandos-útiles)
8. [Referencias](#referencias)

## Descripción General

En esta práctica configuraremos un entorno de red en el que un servidor DHCP asignará direcciones IP dinámicas a dos clientes (`c1` y `c2`). Además, se configurará una dirección IP fija basada en la dirección MAC para uno de los clientes. Utilizaremos Vagrant para automatizar la creación de tres máquinas virtuales (`dhcp-server`, `c1`, y `c2`) con configuraciones de red predefinidas en una red interna.

## Requisitos

Antes de comenzar, asegúrate de tener instalado:

- **Vagrant**: [Descargar e instalar Vagrant](https://www.vagrantup.com/downloads)
- **VirtualBox** (o el proveedor de máquinas virtuales compatible con Vagrant): [Descargar VirtualBox](https://www.virtualbox.org/)
- **Git**: [Descargar Git](https://git-scm.com/)

## 1. Levantar el entorno con Vagrant
Levanta las tres máquinas virtuales (dhcp-server, c1 y c2) con el siguiente comando: **vagrant up**

## 2. Configurar el servidor DHCP
Accede a la máquina dhcp-server para comenzar su configuración: **vagrant ssh dhcp-server**
Instalar el servicio DHCP: **sudo apt install isc-dhcp-server**
Edita el archivo /etc/default/isc-dhcp-server para configurar la interfaz de red que utilizará el servidor DHCP **INTERFACESv4="TU-TARGETA-DE-RED"**
Edita el archivo /etc/dhcp/dhcpd.conf para configurar el rango de direcciones IP que se asignarán dinámicamente, y otros parámetros de red (Archivo

# Лабораторная работа. Базовая настройка коммутатора 

## Топология

### Задачи
1. Проверка конфигурации коммутатора по умолчанию
2. Создание сети и настройка основных параметров устройства
    - Настройте базовые параметры коммутатора.
    - Настройте IP-адрес для ПК.
3. Проверка сетевых подключений
    - Отобразите конфигурацию устройства.
    - Протестируйте сквозное соединение, отправив эхо-запрос.
    - Протестируйте возможности удаленного управления с помощью Telnet.


| Устройство | Интерфейс | IP-адрес / префикс | 
|-------|------|---------|
| S1    | VLAN 1 | 192.168.1.2 /24    |
| S1    | VLAN 1 |     |  
| S1    | VLAN 1 |  |
| PC-A    | NIC | 192.168.1.10 /24   |
| PC-A    | NIC |     |
| PC-A    | NIC |     |


1. Создание сети и проверка настроек коммутатора по умолчанию
    - Создайте сеть согласно топологии.  
![](https://github.com/Khalehas/otus-network-engineer/blob/main/labs/lab1/top-new.png)  
![](https://github.com/Khalehas/otus-network-engineer/blob/main/labs/lab1/top-term.png)

Вопрос:  
Почему нужно использовать консольное подключение для первоначальной настройки коммутатора? Почему нельзя подключиться к коммутатору через Telnet или SSH?  
Ответ:  
У нового или сброшенного устройства ещё нет никакой IP-конфигурации и сетевых служб, чтобы настроить его через Telnet или SSH.  

2. Проверьте настройки коммутатора по умолчанию.  

<img width="671" height="542" alt="image" src="https://github.com/user-attachments/assets/9986bb29-b905-4640-95af-b742467df173" />  

```
Switch#show running-config
Building configuration...

Current configuration : 1080 bytes
!
version 15.0
no service timestamps log datetime msec
no service timestamps debug datetime msec
no service password-encryption
!
hostname Switch
!
!
!
!
!
!
spanning-tree mode pvst
spanning-tree extend system-id
!
interface FastEthernet0/1
!
interface FastEthernet0/2
!
interface FastEthernet0/3
!
interface FastEthernet0/4
!
interface FastEthernet0/5
!
interface FastEthernet0/6
!
interface FastEthernet0/7
!
interface FastEthernet0/8
!
interface FastEthernet0/9
!
interface FastEthernet0/10
!
interface FastEthernet0/11
!
interface FastEthernet0/12
!
interface FastEthernet0/13
!
interface FastEthernet0/14
!
interface FastEthernet0/15
!
interface FastEthernet0/16
!
interface FastEthernet0/17
!
interface FastEthernet0/18
!
interface FastEthernet0/19
!
interface FastEthernet0/20
!
interface FastEthernet0/21
!
interface FastEthernet0/22
!
interface FastEthernet0/23
!
interface FastEthernet0/24
!
interface GigabitEthernet0/1
!
interface GigabitEthernet0/2
!
interface Vlan1
 no ip address
 shutdown
!
!
!
!
line con 0
!
line vty 0 4
 login
line vty 5 15
 login
!
!
!
!
end
```
На коммутаторе имеется 24 интерфейса FastEthernet и 2 интерфейса GigabitEthernet. Диапазон значений на vty-линиях 0 4 и 5 15.  





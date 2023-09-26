## Tipos de red

- LAN
- MAN
- WAN

## Modelo OSI

1. Capa Física

    - Protocolos:
        - RS-232
        - TJ45
        - V.34
        - 100BASE-TX
        - SDH
        - DSL
        - 802.11

2. Capa de Enlace

    - Protocolos:
        - Ethernet
        - 802.11
        - MAC/LLC
        - VALN
        - ATM
        - HDP
        - Fibre Channel
        - Frame Relay
        - HDLC
        - PPP
        - Q.921
        - Token Ring

    - Notas:
        - Dirección MAC (dirección física): 
            - Identificador de 48 BITS que identifican a una tarjeta de red (determinada por el fabricante y no uede repetirse).
            - Ejemplo: 00:1e:c2:9e:28:6b
            - Comando window para ver MAC:
                ```cmd
                ipconfig /all
                ```

        - Interfaz de conexión (NIC): Tarjeta de red.

        - Trama Ethernet: Unidad de comunicación en una red LAN y es lo que envían y reciben los equipos para comunicarse en esta red.

        - Switch: Conecta equipos a una red LAN. Utiliza una tabla (conocida como CAM) donde registra la MAC que se encuentra en cada puerto.

        - MAC de difución:
            - FF:FF:FF:FF:FF:FF
            - Mensaje que se envia a todos los puertos.



3. Capa de Red

    - Protocolos:
        - IP
        - ARP
        - IPsec
        - ICMP
        - IGMP
        - OSPF

4. Capa de Transporte

    - Protocolos:
        - TCP
        - UDP
        - SCTP
        - SSL
        - TLS

5. Capa de Sesión

    - Protocolos:
        - Session establishment in TCP
        - SIP
        - RTP
        - RPC
        - RPC-Named pipes

6. Capa de Presentación

    - Reconozind Data:
        - HTML
        - DOC
        - JPEG
        - MP3
        - AVI
        - Sockets


7. Capa de Aplicación

    - Protocolos:
        - DNS
        - WWW/HTTP
        - P2P
        - EMAIL/POP
        - SMTP
        - Telnet
        - FTP

# Ejercicios Tema 1

1. **A partir de la dirección IP 172.18.71.2/21, ¿cuál es la dirección de red y de difusión a la que pertenece dicha interfaz?. ¿Cuántas direcciones IP están disponibles en esta red, y cuáles serían?**

    ```
    Dirección de host:  10101100.00010010.01000111.00000010  (172.18.71.2) Máscara de red (/21): 11111111.11111111.11111000.00000000  (255.255.248.0) 
    
    Dirección de red = (dirección de host) AND (máscara de red), luego será: 
    
    Dirección de red: 10101100.00010010.01000000.00000000 -> 172.18.64.0 
    
    
    Dirección difusión = bits de la dirección de red + resto de bits a 1 Dirección difusión:   10101100.00010010.01000111.1111111 -> 172.18.71.255 
    
    
    Se disponen 32 - 21 = 11 bits para numerar las interfaces de red, pero hay que restar 2 direcciones reservadas: la de red y la difusión. 
    
    Luego tendremos 2n11 - 2 = 2048 - 2 = 2046 interfaces distintas que van desde: 
    
    10101100.00010010.01000000.00000000 (172.18.64.0) Direc. de red (reservada) 10101100.00010010.01000000.00000001 (172.18.64.1) dirección 1ª 10101100.00010010.01000000.00000010 (172.18.64.2) dirección 2ª 10101100.00010010.01000000.00000011 (172.18.64.3) dirección 3ª 10101100.00010010.01000000.00000100 (172.18.64.4) dirección 4ª 
    
    ................................... 
    
    10101100.00010010.01000111.11111110 (172.18.71.254) Última. Dirección 2046ª 10101100.00010010.01000111.11111111 (172.18.71.255) Dir. difusión (reservada)
    ```

2. **A partir de la dirección IP 192.168.108.20/28, ¿cuál es la dirección de red y de difusión a la que pertenece dicha interfaz?. ¿Cuántas direcciones IP están disponibles en esta red, y cuáles serían?**

    ```
    Dirección de host:      11000000.10101000.01101100.00010100 (192.168.108.20)
    Máscara de red:         11111111.11111111.11111111.11110000 (255.255.255.240)
    Dirección de red:       11000000.10101000.01101100.00010000 (192.168.108.16)
    Dirección de difusión:  11000000.10101000.01101100.00011111 (192.168.108.31)

    Se disponen de 32 - 28 = 4bit para nuerar las interfaces de red (2 de ellas reservadas).
    Por lo tanto tenemos 16 - 2 = 14 interfaces distintas que van desde 
    192.168.108.16 --> Dirección de red
    192.168.108.17 --> 1ª
    ...
    ...
    192.168.108.30 --> Última dirección
    192.168.108.31 --> Dirección de difusión
    ```

3. **A partir de la dirección IP 192.168.108.20/255.255.255.128, ¿cuál es la dirección de red y de difusión a la que pertenece dicha interfaz?. ¿Cuántas direcciones IP están disponibles en esta red, y cuáles serían?**

    ```
    Dirección de host:      11000000.10101000.01101100.00010100 (192.168.108.20)
    Máscara de red:         11111111.11111111.11111111.10000000 (255.255.255.128)
    Dirección de red:       11000000.10101000.01101100.00000000 (192.168.108.0)
    Dirección de difusión:  11000000.10101000.01101100.01111111 (192.168.108.127)

    Se disponen de 32 - 25 = 7bits para nuerar las interfaces de red (2 de ellas reservadas).
    Por lo tanto tenemos 128 - 2 = 126 interfaces distintas que van desde 
    192.168.108.0 --> Dirección de red
    192.168.108.1 --> 1ª
    ...
    ...
    192.168.108.126 --> Última dirección
    192.168.108.127 --> Dirección de difusión
    ```

4. **A partir de la dirección IP 192.168.108.148/255.255.255.128, ¿cuál es la dirección de red y de difusión a la que pertenece dicha interfaz?. ¿Cuántas direcciones IP están disponibles en esta red, y cuáles serían?**

    ```
    Dirección de host:      11000000.10101000.01101100.10010100 (192.168.108.148)
    Máscara de red:         11111111.11111111.11111111.10000000 (255.255.255.128)
    Dirección de red:       11000000.10101000.01101100.10000000 (192.168.108.128)
    Dirección de difusión:  11000000.10101000.01101100.11111111 (192.168.108.255)

    Se disponen de 32 - 25 = 7bits para nuerar las interfaces de red (2 de ellas reservadas).
    Por lo tanto tenemos 128 - 2 = 126 interfaces distintas que van desde 
    192.168.108.128 --> Dirección de red
    192.168.108.129 --> 1ª
    ...
    ...
    192.168.108.254 --> Última dirección
    192.168.108.255 --> Dirección de difusión
    ```

5. **Se dispone de una red local cuya dirección de red es 192.168.108.0/24,  lo que nos permite disponer hasta 28 - 2 = 256 - 2 = 254  direcciones para los equipos de la red. Por necesidades de organización, se quiere transformar dicha red en 4 subredes distintas de tal forma que todas las IP de todos los equipos de las 4 subredes sigan comenzando por 192.168.108. ¿Cuáles podrían ser dichas subredes, y qué rango direcciones de hosts estarían disponibles en cada subred?**

    ```
    Dirección de red: 11000000.10101000.01101100.00000000

    1º Tenemos que crear una máscara de subred para poder crear nuestras 4 redes, por lo tanto necesitamos 2bits para crear nuestras 4 redes, así que nuestra máscara de subred será 255.255.255.192
    *Máscara de subred: 255.255.255.192 11111111.11111111.11111111.[11]000000

    Entonces las 4 redes que nos salrían son las resultantes de la combinación de los 2 bits que tenemos reservados en nuestra máscara de subred:
    1ª Subred--> 11000000.10101000.01101100.00000000 (192.168.108.0)
        192.168.108.0 -- 192.168.108.63
    2ª Subred--> 11000000.10101000.01101100.01000000 (192.168.108.64)
        192.168.108.64 -- 192.168.108.127
    3ª Subred--> 11000000.10101000.01101100.10000000 (192.168.108.128)
        192.168.108.128 -- 192.168.108.191
    4ª Subred--> 11000000.10101000.01101100.11000000 (192.168.108.192)
        192.168.108.192 -- 192.168.108.255
    ```

    
# ROOT-ME . CHALLENGE RESEAU

## 1. FTP - AUTHENTIFICATION

En utilisant Wireshark, le logiciel utilisé pour capturer les paquets et lire un fichier PCAP ch1.pcap, on peut obtenir les lignes suivantes avec l'input USER et PASS:

```
#8 4.216600 10.20.144.150 → 10.20.144.151 FTP 81 Request: USER cdts3500
#9 4.217350 10.20.144.151 → 10.20.144.150 FTP 91 Response: 331 Enter password.
#10 4.217630 10.20.144.150 → 10.20.144.151 TCP 66 35974 → 21 [PSH, ACK] Seq=16 Ack=114 Win=32648 Len=0 TSval=1657564500 TSecr=1657394000
#11 7.639420 10.20.144.150 → 10.20.144.151 FTP 81 Request: PASS ********
```

## 2. TELNET - AUTHENTIFICATION

Toujours en utilisant Wireshark et après avoir télécharger ch2.pcap, on peut obtenir les paquets capturés. Observons les lignes suivantes:

```
56	9.464208	192.168.0.1	192.168.0.2	TELNET	75	Telnet Data ...
Data: Password:
```

Puis en suivant les packets suivants, on le mot de pass parmis les packets suivants:

```
58	10.704378	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: *
60	11.144054	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: *
62	11.625626	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: *
64	11.931320	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: *
66	13.285963	192.168.0.2	192.168.0.1	TELNET	68	Telnet Data ...
Data: \r
```

## 3. ETHERNET - FRAME

A l'aide d'un décodeur hexadécimal, on converti la trame en données lisibles et on trouve les données suivantes :

```
Hypertext Transfer Protocol
    GET / HTTP/1.1\r\n
    Authorization: Basic Y29uZmk6ZGVudGlhbA==\r\n
    Credentials: *************
```

# 4. AUTHENTIFICATION TWITTER

A l'aide de Wireshark qui est un décodeur de paquet PCAP, on découvre dans le paquet PCAP la requête faite à Twitter:

```
Hypertext Transfer Protocol
    GET /statuses/replies.xml HTTP/1.1\r\n
    User-Agent: CFNetwork/330\r\n
    Cookie: _twitter_sess=BAh7CDoJdXNlcjA6B2lkIiVmZGQ2ODc5MTMwMWFhOTFiMWExZDViZmQwMGEz%250AOWNkMyIKZmxhc2hJQzonQWN0aW9uQ29udHJvbGxlcjo6Rmxhc2g6OkZsYXNo%250ASGFzaHsABjoKQHVzZWR7AA%253D%253D--ea12e7bc090d05202cd7e3f972c2b4414a97f657\r\n
        Cookie pair: _twitter_sess=BAh7CDoJdXNlcjA6B2lkIiVmZGQ2ODc5MTMwMWFhOTFiMWExZDViZmQwMGEz%250AOWNkMyIKZmxhc2hJQzonQWN0aW9uQ29udHJvbGxlcjo6Rmxhc2g6OkZsYXNo%250ASGFzaHsABjoKQHVzZWR7AA%253D%253D--ea12e7bc090d05202cd7e3f972c2b4414a97f657
    Accept: */*\r\n
    Accept-Language: en-us\r\n
    Accept-Encoding: gzip, deflate\r\n
    Authorization: Basic dXNlcnRlc3Q6cGFzc3dvcmQ=\r\n
        Credentials: usertest:********
    Connection: keep-alive\r\n
    Host: twitter.com\r\n
    \r\n
    [Full request URI: http://twitter.com/statuses/replies.xml]
    [HTTP request 1/1]
```

# 5. BLUETOOTH - UNKNOWN FILE

On ouvre le fichier avec l'extension .bin et on ouvre l'onglet ```Wireless```  et cliquer sur ```bluetooth devices```;
Nous pouvons voir l'adresse MAC et le nom du téléphone et on n'a plus qu'à suivre l'instruction du sujet;
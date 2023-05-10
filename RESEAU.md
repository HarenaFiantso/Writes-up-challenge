# ROOT-ME . CHALLENGE RESEAU

## 1. FTP - AUTHENTIFICATION

En utilisant Wireshark, le logiciel utilisé pour capturer les paquets et lire un fichier PCAP ch1.pcap, on peut obtenir les lignes suivantes avec l'input USER et PASS:

```
#8 4.216600 10.20.144.150 → 10.20.144.151 FTP 81 Request: USER cdts3500
#9 4.217350 10.20.144.151 → 10.20.144.150 FTP 91 Response: 331 Enter password.
#10 4.217630 10.20.144.150 → 10.20.144.151 TCP 66 35974 → 21 [PSH, ACK] Seq=16 Ack=114 Win=32648 Len=0 TSval=1657564500 TSecr=1657394000
#11 7.639420 10.20.144.150 → 10.20.144.151 FTP 81 Request: PASS cdts3500
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
Data: u
60	11.144054	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: s
62	11.625626	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: e
64	11.931320	192.168.0.2	192.168.0.1	TELNET	67	Telnet Data ...
Data: r
66	13.285963	192.168.0.2	192.168.0.1	TELNET	68	Telnet Data ...
Data: \r
```
# ROOT-ME . CHALLENGE RESEAU

## 1. FTP - AUTHENTIFICATION

En utilisant wireshark, le logiciel utilisé pour capturer les paquets et lire un fichier PCAP ch1.pcap, on peut obtenir les lignes suivantes avec l'input USER et PASS:

```
#8 4.216600 10.20.144.150 → 10.20.144.151 FTP 81 Request: USER cdts3500
#9 4.217350 10.20.144.151 → 10.20.144.150 FTP 91 Response: 331 Enter password.
#10 4.217630 10.20.144.150 → 10.20.144.151 TCP 66 35974 → 21 [PSH, ACK] Seq=16 Ack=114 Win=32648 Len=0 TSval=1657564500 TSecr=1657394000
#11 7.639420 10.20.144.150 → 10.20.144.151 FTP 81 Request: PASS cdts3500
```
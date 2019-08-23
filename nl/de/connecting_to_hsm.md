---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-04"

keywords: hardware security modules, HSM, keys, rsa,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Verbindung zu IBM Cloud HSM herstellen
{: #connecting-to-ibm-cloud-hsm}

In den folgenden Schritten wird das Herstellen einer HSM-VPN-Verbindung zum Kundenkonto beschrieben. Es ist ebenfalls möglich, eine Verbindung von einem Server in Ihrem Konto aus herzustellen, der über Konnektivität zu dem privaten VLAN verfügt, in dem das HSM bereitgestellt wurde.
{:shortdesc}

![Architektur eines Netzes im HSM](/images/Connecting_to_HSM-01.png "HSM-Architektur")

1. Melden Sie sich beim HSM mit der Benutzer-ID und dem Kennwort, die unter *Gerätedetails* angegeben sind, über Ihr VPN an oder melden Sie sich bei einem Server an, der sich im selben privaten VLAN befindet.
`#ssh customer_admin@10.1.1.101`

2. Ändern Sie das HSM-Kennwort für `customer_admin`:
`#user password`

3. Aktivieren Sie die PKI-basierte Authentifizierung (PKI = Public Key Infrastructure):
```
#ssh-keygen -b 2048 -t rsa
RSA-Schlüsselpaar aus öffentlichem/privatem Schlüssel generieren.
Datei zum Speichern des Schlüssels angeben (/root/.ssh/id_rsa):
Kennphrase eingeben (leer, falls keine Kennphrase verwendet wird):
Kennphrase wiederholen:
Identifikation wurde in /root/.ssh/id_rsa gespeichert.
Öffentlicher Schlüssel wurde in /root/.ssh/id_rsa.pub gespeichert.
Schlüsselfingerabdruck:
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6 root@host
```
Es werden zwei Dateien erstellt. Bei der ersten Datei handelt es sich um eine Datei mit dem privaten Schlüssel, die auf dem verbindenden Host bleibt, bei der zweiten um eine Datei mit dem öffentlichen Schlüssel, die an die HSM-Appliance gesendet wird.

4. Verwenden Sie SCP (Secure Copy Protocol), um den öffentlichen Schlüssel an die Appliance '# scp /root/.ssh/id_rsa/pub' zu senden.
```
customer_admin@10.1.1.101
customer_admin@appliance password:
id_rsa.pub 100% |****************| 220 00:00
```
5. Verifizieren Sie auf der Appliance die Standardeinstellungen des Service für die Authentifizierung über den öffentlichen Schlüssel.
```
[myLuna] lunash:>sysconf -ssh show
SSH ist nicht eingeschränkt.
Kennwortauthentifizierung ist aktiviert.
Authentifizierung über öffentlichen Schlüssel ist aktiviert.
Befehlsergebnis: 0 (Erfolg)
```

6. Stellen Sie sicher, dass standardmäßig keine Einträge für öffentliche Schlüssel vorhanden sind.
```
[myLuna]
lunash:>sysconf -ssh publickey list
Öffentliche SSH-Schlüssel für Benutzer 'admin':
Name Typ Bit Fingerabdruck
Befehlsergebnis : 0 (Erfolg)
```
7. Fügen Sie den gesendeten öffentlichen Schlüssel zur Appliance hinzu.
```
[myLuna] lunash:>sysconf -ssh publickey add root@host -f id_rsa.pub
Öffentlicher Schlüssel hinzugefügt.
Befehlsergebnis: 0 (Erfolg)
```
8. Überprüfen Sie die Liste der öffentlichen Schlüssel.
```
[myLuna] lunash:>sysconf - ssh publickey list
Öffentliche SSH-Schlüssel für Benutzer 'admin':
Name Typ Bit Fingerabdruck
root@host ssh-rsa 1024
6e:7a:73:e1:2a:54:8f:99:3e:6a:56:f8:38:22:fb:a6
Befehlsergebnis: 0 (Erfolg)
```
9. Stellen Sie sicher, dass der aufgeführte Fingerabdruck mit dem ursprünglich auf dem verbindenden Host generierten Fingerabdruck übereinstimmt.

---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM-Rollen
{: #ibm-cloud-hsm-roles}

In diesem Abschnitt werden die Rollen, die auf das {{site.data.keyword.cloud}} HSM zugreifen, sowie die im Host integrierte Verschlüsselungsengine bzw. die mit dem Host verbundene Verschlüsselungsengine erläutert.  
{:shortdesc}

## Obligatorische Rollen
<li>HSM Security Officer (SO): Der SO ist für die HSM-Initialisierung, das Festlegen und Ändern von HSM-Richtlinien (auf Grundlage der HSM-Funktionalität), die Erstellung und die Löschung von Anwendungspartitionen verantwortlich
<li>Partition Security Officer (PO): Der PO ist für die Initialisierung der Crypto Officer-Rolle in der Partition, das Zurücksetzen von Kennwörtern, das Festlegen und Ändern von Richtlinien auf Partitionsebene (auf Grundlage der HSM- und Partitionsfunktionalität) verantwortlich
<li>Crypto Officer (CO): Der CO ist für die Initialisierung der Crypto User-Rolle sowie für die Erstellung und Modifizierung von Verschlüsselungsobjekten in der HSM-Partition verantwortlich

## Optionale Rollen
{: #optional-roles}

<li>Auditor (Au): Der Au ist für die Verwaltung der HSM-Auditprotokollierung verantwortlich und arbeitet von den anderen Rollen im HSM unabhängig
<li>Crypto User (CU): Der CU ist für die Nutzung von Verschlüsselungsobjekten (Verschlüsseln/Entschlüsseln, Signieren/Prüfen etc.) in der HSM-Partition verantwortlich

## Erweitertes Cryptoki-Modell
{: #enhanced-cryptoki-model}

Die Trennung der Rollen des SafeNet Luna Network HSM folgt einem erweiterten Cryptoki-Modell für die folgenden Rollen:

### HSM Security Officer (SO)
{: #hsm-security-officer-so}

Der HSM SO steuert das HSM innerhalb der SafeNet Luna Network HSM-Appliance. Für den Zugriff auf die HSM SO-Funktionen müssen Sie zunächst als Applianceadministrator angemeldet sein.
Zusätzlich zu den anderen Appliancefunktionen kann ein Benutzer, der sich mit den HSM SO-Berechtigungsnachweisen authentifiziert hat, Folgendes tun:
<li>Partitionen erstellen und löschen
<li>Das HSM sichern und wiederherstellen
<li>HSM-Richtlinien ändern

### Partition Security Officer (PO)
{: #partition-security-officer-po}

Der Partition Security Officer steuert mindestens eine Partition (virtuelle HSMs) innerhalb des SafeNet Luna Network HSM. Für den Zugriff auf Partition SO-Funktionen müssen Sie sich mit dem Dienstprogramm LunaCM auf einem registrierten Client-Computer anmelden.
Der Partition SO kann Folgendes tun, wenn er bei der Partition angemeldet ist:
<li>Partitionsrichtlinien ändern
<li>Den Partitionsinhalt sichern und wiederherstellen
<li>Die Crypto Officer-Rolle initialisieren

### Crypto Officer (CO)
{: #crypto-officer-co}

Der Crypto Officer hat dank des Dienstprogramms LunaCM auf einem registrierten Client-Computer über vollständigen Schreib-/Lesezugriff auf die Partition. Der Berechtigungsnachweis für die Crypto Officer-Partition ermöglicht einer Clientanwendung die Ausführung von beliebigen Verschlüsselungsoperationen; dazu zählen die folgenden:
<li>Erstellung und Löschung von Schlüsseln
<li>Key-Wrapping durchführen und aufheben
<li>Verschlüsseln/Entschlüsseln
<li>Signieren/Prüfen</li>
Der Crypto Officer kann außerdem die optionale Crypto User-Rolle initialisieren.

### Crypto User (CU)
{: #cypto-user-cu}

Beim Crypto User handelt es sich um einen eingeschränkten Clientbenutzer mit ausschließlich Lesezugriff. Sobald die Initialisierung durchgeführt wurde, kann der authentifizierte Crypto User zwar auf Verschlüsselungsmaterial zugreifen, das sich bereits in der Partition befindet (für das Siginieren, Prüfen, Verschlüsseln, Entschlüsseln), diese Objekte jedoch nicht bearbeiten (keine Generierung, kein Löschen oder kein Key-Wrapping/Unwrapping).
Die Crypto User-Rolle ist eine optionale Rolle. Wenn Sie für diese Rolle keine Sicherheitsanforderung haben, kann sie ohne Initialisierung bleiben und alle Clientanwendungen können mithilfe des Berechtigungsnachweises für den Crypto Officer auf die Partition zugreifen.

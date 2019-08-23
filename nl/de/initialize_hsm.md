---

copyright:
  years: 2014, 2019
lastupdated: "2019-04-05"

keywords: hardware security modules, HSM, initializing HSM

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# IBM Cloud HSM initialisieren
{: #initializing-the-ibm-cloud-hsm}

Sobald Sie über Zugriff auf das Hardwaresicherheitsmodul (HSM) verfügen, müssen Sie es initialisieren. Möglicherweise ist zu einem späteren Zeitpunkt eine erneute Initialisierung erforderlich. Führen Sie die folgenden Schritte aus, um das HSM zu initialisieren.
{:shortdesc}

1. HSM `[myLuna] lusash:.hsm init -label Customer1Prod` initialisieren.
```
Kennwort für den HSM-Administrator eingeben:
>**************
Kennwort zur Bestätigung erneut eingeben:
>**************
Klondomäne für die Initialisierung dieses HSM eingeben (Eingabetaste drücken, um die Standarddomäne zu verwenden):
>MyDomain
Vorsicht: Soll dieses HSM tatsächlich reinitialisiert werden?
Alle Partitionen und Daten werden gelöscht.
'proceed' eingeben, um das HSM zu initialisieren; 'quit' eingeben, um den Vorgang abzubrechen.
>proceed
HSM-Initialisierung erfolgreich.
Befehlsergebnis: 0 (Erfolg)
```

Informationen zu allen verfügbaren Befehlen, die in der HSM-CLI unterstützt werden, finden Sie in der Dokumentation [LunaSH Command Reference Guide ![Symbol für externen Link](../../icons/launch-glyph.svg "Symbol für externen Link")](ftp://public.dhe.ibm.com/cloud/bluemix/hsm/LunaSH_Command_Reference_Guide_72.pdf){: new_window}.

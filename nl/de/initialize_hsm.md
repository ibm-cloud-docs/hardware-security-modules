---
copyright:
  years: 1994, 2018
lastupdated: "2018-06-13"
---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# IBM Cloud HSM initialisieren

Sobald Sie über Zugriff auf das Hardwaresicherheitsmodul (HSM) verfügen, müssen Sie es initialisieren. Möglicherweise ist zu einem späteren Zeitpunkt eine erneute Initialisierung erforderlich. Führen Sie die folgenden Schritte aus, um das HSM zu initialisieren.
{:shortdesc}

1. HSM [myLuna] lusash:.hsm init -label Customer1Prod' initialisieren.
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

---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, HSM roles, HSM Security Officer, Partition Security Officer, Crypto Officer, Auditor, Crypto User, Appliance Admin, HSM Security Officer, Partition Security Officer, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:new_window: target="_blank"}

# Ruoli IBM Cloud HSM
{: #ibm-cloud-hsm-roles}

Questo argomento descrive i ruoli per l'accesso a {{site.data.keyword.cloud}} HSM e il motore crittografico all'interno o collegato all'host.  
{:shortdesc}

## Ruoli obbligatori
<li>HSM Security Officer (SO): responsabile dell'inizializzazione dell'HSM, della configurazione e della modifica delle politiche HSM (basate sulle funzionalità dell'HSM) e della creazione ed eliminazione delle partizioni dell'applicazione
<li>Partition Security Officer (PO): responsabile dell'inizializzazione del ruolo Crypto Officer sulla partizione, della reimpostazione delle password, della configurazione e della modifica delle politiche al livello di partizione (basate sulle funzionalità dell'HSM e della partizione)
<li>Crypto Officer (CO): responsabile dell'inizializzazione del ruolo Crypto User e della creazione e modifica degli oggetti crittografici nella partizione HSM

## Ruoli facoltativi
{: #optional-roles}

<li>Auditor (Au): responsabile della gestione della registrazione del controllo HSM, indipendente dagli altri ruoli nell'HSM
<li>Crypto User (CU): responsabile dell'utilizzo degli oggetti crittografici (crittografia/decrittografia, firma/verifica e altro) nella partizione HSM

## Modello Cryptoki avanzato
{: #enhanced-cryptoki-model}

La separazione dei ruoli su SafeNet Luna Network HSM segue un modello Cryptoki avanzato per i seguenti ruoli:

### HSM Security Officer (SO)
{: #hsm-security-officer-so}

L'HSM SO ha il controllo dell'HSM all'interno del dispositivo SafeNet Luna Network HSM. Per accedere alle funzioni HSM SO, devi prima accedere come amministratore del dispositivo.
In aggiunta a tutte le altre funzioni del dispositivo, un utente che si è autenticato con le credenziali HSM SO può:
<li>Creare ed eliminare le partizioni
<li>Eseguire il backup e il ripristino dell'HSM
<li>Modificare le politiche HSM

### Partition Security Officer (PO)
{: #partition-security-officer-po}

Il Partition Security Officer ha il controllo di una o più partizioni (HSM virtuali) all'interno di SafeNet Luna Network HSM. Per accedere alle funzioni Partition SO, devi accedere utilizzando il programma di utilità LunaCM su un computer client registrato.
Il Partition SO, dopo aver eseguito l'accesso alla partizione, può:
<li>Modificare le politiche della partizione
<li>Eseguire il backup e il ripristino dei contenuti della partizione
<li>Inizializzare il ruolo Crypto Officer

### Crypto Officer (CO)
{: #crypto-officer-co}

Il Crypto Officer ha l'accesso di lettura e scrittura completo alla partizione tramite il programma di utilità LunaCM su un computer registrato. Le credenziali della partizione del Crypto Officer permettono a un'applicazione client di eseguire tutte le operazioni crittografiche, incluso:
<li>Generazione/Eliminazione della chiave
<li>Impacchettamento/Spacchettamento
<li>Crittografia/Decrittografia
<li>Firma/Verifica</li>
Il Crypto Officer può inoltre inizializzare il ruolo Crypto User facoltativo.

### Crypto User (CU)
{: #cypto-user-cu}

Il Crypto User è un utente client in sola lettura limitato. Una volta inizializzato, il Crypto User autenticato può accedere al materiale crittografico già esistente (per firma, verifica, crittografia, decrittografia), ma non può modificare questi oggetti (nessuna operazione di generazione, eliminazione o impacchettamento/spacchettamento).
Il ruolo Crypto User è facoltativo. Se non hai alcun requisito di sicurezza per questo ruolo, può rimanere non inizializzato e tutte le applicazioni client possono accedere alla partizione utilizzando le credenziali Crypto Officer.

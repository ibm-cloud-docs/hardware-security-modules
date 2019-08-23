---

copyright:
  years: 2014, 2019
lastupdated: "2019-03-07"

keywords: hardware security modules, HSM, partitions, labels, cryptographic, keys,

subcollection: hardware-security-modules

---

{:shortdesc: .shortdesc}
{:external: target="_blank" .external}

# Creación de particiones de IBM Cloud HSM
{: #creating-ibm-cloud-hsm-partitions}

Dentro de un HSM (Hardware Security Module) de {{site.data.keyword.cloud}}, los espacios de trabajo criptográficos independientes deben estar inicializados y diseñados para los clientes. Un espacio de trabajo, o *partición*, y todo su contenido están protegidos por cifrado derivado de su autenticación. Solo un cliente que presente la autenticación correcta tendrá permiso para ver la partición y trabajar con su contenido.
{:shortdesc}

Al crear las particiones, tenga en cuenta que los nombres de particiones, también conocidos como etiquetas, deben ser exclusivos en el HSM. No puede crear dos particiones con la misma etiqueta en un HSM. El nombre que le ponga a la partición es la etiqueta que ven las aplicaciones de PKCS (Public-Key Cryptographic Standards) #11.

1. Inicie sesión como Administrador de HSM con la contraseña utilizada para inicializar el HSM.
```
[myLuna] lunash:>hsm login
Please enter HSM Administrators' password:
>**************
hsm login successful.
Command Result : 0 (Success)
```
2. Cree la partición.
```
[myLuna] Lunash:>partition create - partition customerPartionProd
Please ensure that you have purchased licenses for at least this number of partitions: 1
If you are sure to continue then type proceed, otherwise type quit.
> proceed
Processing...
Please enter a password for the partition
>**************
Please re-enter password to confirm:
>**************
Please enter the cloning domain to use when creating this partition (press enter to use the default domain):
> MyDomain
partition create successful
Command Result : 0 (Success)
```

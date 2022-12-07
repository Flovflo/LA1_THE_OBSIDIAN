**Includes**
```c
#include <sys/shm.h>
#include <sys/types.h>
#include <sys/ipc.h>
```

**Générer une clé**
```c
key_t ftok(char *pathname, int proj_id);
```
Le fichier décrit par pathname doit exister et être accessible.

**Création d'un segment de mémoire partagée**
```c
int shmget(key_t key, int size, int shmflag);
```
- key : clé déterminée par ftok
- size : taille en octet (utiliser sizeof())
- shmflag : indique les permissions et le mode d'ouverture : 0666 avec IPC_CREAT ou IPC_EXCL (exemple : 0666 | IPC_CREAT | IPC_EXCL)

Retourne un shmid en cas de succès ou -1 en cas d'échec

**Ouverture d'un segment de mémoire partagée**
```c
char *shmat(int shmid, char *shmaddr, int shmflag);
```
- shmid : identifiant de la zone de mémoire
- shmaddr : précise l'addresse du segment attaché (mettre NULL)
- shmflag : conditions d'accès au segment (0 autorise la lecture et l'écriture, SHM_RDONLY impose un accès en lecture seule)

**Détacher un segment de mémoire partagée**
```c
int shmdt(char *shmaddr);
```
- shmaddr : adresse du segment à détacher

**Controle, maj, suppression, vérouillage / dévérrouillage de la mémoire partagée**
```c
int shmctl(int shmid, int cmd, struct shmid_ds *buf);
```
- shmid : identifiant de la mémoire partagée
- cmd : commande, peut valoir les valeurs ci-dessous :
	- IPC_STAT : Permet de récupérer les stats dans la structure shmid_ds
	- IPC_SET : Permet de modifier la structure shmid_ds
	- IPC_RMID : Supprimer le segment de mémoire partagée (buf pourra être positionné à NULL)
- buf : Structure contenant les informations de la mémoire partagée
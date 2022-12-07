## Commande shell
```sh
kill -s SIGUSR1 PID
```
Permet d'envoyer un signal à un processus.

## Fonction C
```c
int kill(pid_t pid, int sig);
```
Permet d'envoyer un signal à un processus

**Includes nécessaires :** 
```c
#include <sys/types.h>
#include <signal.h>
```

**Arguments :**
-  pid : PID du processus à qui on envoit le signal
-  sig : Numéro du signal à envoyer (on peut passer les constantes définies comme SIGUSR1)

**Valeurs de retour :**
- -1 : en cas d'erreur
-  0 : succès
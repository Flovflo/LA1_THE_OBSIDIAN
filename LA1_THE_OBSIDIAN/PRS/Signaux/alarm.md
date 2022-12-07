**Définition de la fonction :**
```c
unsigned int alarm(unsigned int seconds);
```

Envoie un signal SIGALRM après n secondes au processus appelant cette fonction.

**Includes nécessaires :** 
```c
#include <unistd.h>
```

**Arguments :**
- ```c unsigned int seconds``` : tempo

**Valeurs de retour :**
- Nombre de secondes restantes avant l'envoi de la tempo

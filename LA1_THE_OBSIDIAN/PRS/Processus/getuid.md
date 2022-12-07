**Définition de la fonction :**
```c
uid_t getuid(void)
```

Permet d'obtenir son UID

**Includes nécessaires :** 
```c
#include <sys/types.h>
#include <unistd.h>
```

**Valeurs de retour :**
- Le UID du processus courant.

**Exemple d'utilisation :**
```c
uid_t monUid = getuid();
printf("Mon UID : %d\n", monUid);
```


**Définition de la fonction :**
```c
gid_t getegid(void)
```

Permet d'obtenir son EGID

**Includes nécessaires :** 
```c
#include <sys/types.h>
#include <unistd.h>
```

**Valeurs de retour :**
- Le EGID du processus courant.

**Exemple d'utilisation :**
```c
gid_t monEgid = getegid();
printf("Mon EGID : %d\n", monEgid);
```


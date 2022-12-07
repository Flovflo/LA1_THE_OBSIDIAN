**Include pour les sémaphores**
```c
#include <semaphore.h>
```

Link avec -lpthread

**Déclarer un sémaphore**
```c
sem_t semaphore;
```

**Initialiser un sémaphore**
```c
int sem_init(sem_t *sem, int pshared, unsigned int value);
```
- sem : sémaphore
- pshared : Est ce que le sémaphore est partagé avec plusieurs processus (si ce n'est pas le cas 0, si c'est le cas valeur différente de 0)
- value : Valeur de départ du sémaphore

**Attendre un sémaphore**
```c
int sem_wait(sem_t *sem);
```
Reste bloqué si le sémaphore est nul et sinon décrémente le compteur.

**Rendre sémaphore**
```c
int sem_post(sem_t *sem);
```

**Récupèrer valeur d'un sémaphore**
```c
int sem_getvalue(sem_t *sem, int *sval);
```
- sem : semaphore
- sval : pointeur vers un entier ou sera stocké la valeur du sémaphore

Retourne 0 en cas de succès, -1 sinon

**Supprimer sémaphore**
```c
int sem_destroy(sem_t *sem);
```
Retourne 0 en cas de succès, -1 sinon.

**Ouvrir sémaphore nommé**
```c
sem_t *sem_open(const char *name, int oflag, mode_t mode, unsigned int value);
```

Exemple : 
```c
sem = sem_open("mysemp", O_CREAT | O_RDWR, 0644, 1);
```

**Supprimer lien entre processus et sémaphore**
```c
int sem_close(sem_t *sem);
```

ET 

```c
int sem_unlink(const char *name);
```

**Mise en place de sémaphores anonymes**
```c
sem_t semaphore;
sem_init(&semaphore, 0, 1);

sem_destroy(&semaphore);
```

**Mise en place de sémaphores nommés**
```c
sem_t *semaphore = sem_open("/sem", O_CREAT | O_RDWR, 0600, 1);

sem_close(semaphore);
sem_unlink("/sem");
```
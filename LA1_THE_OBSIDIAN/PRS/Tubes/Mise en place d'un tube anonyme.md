**Includes**
```c
#include <unistd.h>
#include <fcntl.h>
```

**Création d'un tube**
```c
int pipe(int descripteur[2]);
```
descripteur[0] désigne la sortie du tube (la ou on lit).
descripteur[1] désigne l'entrée du tube (la ou on écrit)

**Ecriture dans un tube**
```c
ssize_t write(int descripteur1, const void *buf, size_t count);
```

**Lecture dans un tube**
```c
ssize_t read(int descripteur0, void *buf, size_t count);
```

**Fermer un tube**
```c
int close(int descripteur)
```

Il ne faut pas oublier de fermer l'entrée et la sortie du tube.

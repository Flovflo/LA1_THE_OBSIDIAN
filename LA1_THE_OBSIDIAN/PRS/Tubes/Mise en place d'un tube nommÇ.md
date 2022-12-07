   **Includes**
```c
#include <sys/types.h>
#include <sys/stat.h>
```

**Création du tube nommé**
```c
int mkfifo(const char *pathname, mode_t mode);
```

**Ouverture du tube nommé**
```c
fd = open(const char *pathname, O_WRONLY);
```

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
int close(int fd);
```

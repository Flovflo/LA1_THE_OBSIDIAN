**Créer un mutex :**
```c
pthread_mutex_t my_mutex = PTHREAD_MUTEX_INITIALIZER;
```

**Verrouiller un mutex :**
```c
int pthread_mutex_lock(pthread_mutex_t *mutex);
```
Lorsque le mutex est déjà vérouillé, l'exécution est bloquée sur cette ligne jusqu'à ce que le mutex soit débloqué

**Dévérouiller un mutex :**
```c
int pthread_mutex_unlock(pthread_mutex_t *mutex);
```


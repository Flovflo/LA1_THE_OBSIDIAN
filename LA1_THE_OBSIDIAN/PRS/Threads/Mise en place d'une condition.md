**Déclarer une condition**
```c
pthread_cond_t nomCondition = PTHREAD_COND_INITIALIZER;
```

**Attendre une condition**
```c
int pthread_cond_wait(pthread_cond_t *condition, pthread_mutex_t *mutex*);
```

**Valider une condition**
```c
int pthread_cond_signal(pthread_cond_t *condition);
```
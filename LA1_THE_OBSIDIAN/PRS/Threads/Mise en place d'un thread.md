```c
#include <stdio.h>
#include <stdlib.h>
#include <pthread.h>

void * fonction(void * arg)
{
    printf("Fonction de thread : %d\n", *(int *)arg);
    pthread_exit((void *)42);
}

int main()
{
    pthread_t thread;
    int i = 3;
    int retour;
    pthread_create(&thread, NULL, fonction, (void *)&i);
    pthread_join(thread, (void *)&retour);
    printf("%d\n", retour);
    return 0;
}
```
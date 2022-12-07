**Définition de la fonction :**
```c
pid_t waitpid(pid_t pid, int *wstatus, int options)
```

Attend la fin du processus fils. 
Permet également de libérer les ressources de celui-ci.

**Includes nécessaires :** 
```c
#include <sys/types.h>
#include <sys/wait.h>
```

**Arguments :**
- ```c pid_t pid``` : Pid du fils que l'on souhaite attendre (-1 si peu importe le fils)
- ```c int *wstatus``` : Pointeur vers un entier qui contiendra le status de fin du fils
- ```c int options``` : 
	- **WNOHANG** : quitter directement si aucun fils ne s'est terminé
	- **WCONTINUED** : quitte si le fils a repris son exécution grâce à la réception d'un signal SIGCONT
	- **0** : par défaut

**Valeurs de retour :**
- -1 : en cas d'erreur
-  Autre : PID du fils qui vient de mourir

**Exemple d'utilisation :**
```c
pid_t resFork = fork();

if (resFork == -1)
{
    printf("Erreur lors de la création du processus fils !\n");
    return -1;
}

else if (resFork == 0)
{
    printf("Processus fils !\n");
    exit(0);
}
else
{
    printf("Processus père !\n");
	int status;
	waitpid(resFork, &status, 0);
	printf("Status de fin du fils : %d\n", status);
}
```


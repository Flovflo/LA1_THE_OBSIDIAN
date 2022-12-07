**Includes**
```c
#include <sys/types.h>
#include <sys/ipc.h>
#include <sys/msg.h>
```

**Créer la boite aux lettres**
```c
int msgget(key_t key, int msgflg);
```
- key : clé
- msgflg : IPC_CREAT, IPC_EXCL

**Controle de la boite aux lettres**
```c
int msgctl(int msqid, int cmd, struct msqid_ds *buf);
```

Valeurs possibles de cmd :
- IPC_STAT : Récupère les stats de la boite et les met dans buf
- IPC_SET : Modifie les stats de la boite
- IPC_RMID : Supprime la boite

**Lecture dans la boite**
```c
ssize_t msgrcv(int msqid, void *msgp, size_t msgsz, long msgtyp,int msgflg);
```

msgp pointe vers une structure de la forme :
```c
struct msgbuf
{
	long mtype;
	char mtext[1];
}
```

**Ecriture dans la boite aux lettres**
```c
int msgsnd(int msqid, const void *msgp, size_t msgsz, int msgflg);
```


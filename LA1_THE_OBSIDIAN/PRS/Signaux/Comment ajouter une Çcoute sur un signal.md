**Déclaration de la structure sigaction :**
```c
struct sigaction act;
```

**Paramètre à affecter à act :**
```c
act.sa_handler = fonction;
sigemptyset(&act.sa_mask);
act.sa_flags = 0;
```

**Appel à la fonction sigaction :**
```c
if (sigaction(num_signal, &act, NULL) == -1)
{
	printf("Erreur avec sigaction !\n");
	return -1;
}
```

**Exemple de fonction permettant d'ajouter un signal :**
```c
int ajouter_handler_signal(int num_signal, void * fonction)
{
	if (fonction == NULL)
    {
        printf("La fonction est nulle");
        return -1;
    }

    struct sigaction act;
    act.sa_handler = fonction;
    sigemptyset(&act.sa_mask);
    act.sa_flags = 0;
    if (sigaction(num_signal, &act, NULL) == -1)
    {
        printf("Erreur avec sigaction !\n");
        return -1;
    }

	printf("Ajout du signal %d réussi !\n", num_signal);
    return 0;
}
```


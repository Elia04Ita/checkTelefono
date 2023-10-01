# checkTelefono

L'esercizio richiedeva di controllare dei numeri di telefono a gruppi di 3 per vedere quale di questi é un numero di telefono valido secondo dei parametri dati, restituirlo se lo é o restituire "" se non lo é.

I numeri di telefono vengono convertiti da array, i numeri singoli sono stati salvati come vettori di string, a uno string singolo, per facilitare il controllo successivo, usando il metodo Uniscintelefono

```csharp 
static string Uniscintelefono(string input)
{
    string stringunita = "";
    foreach (char c in input)
    {
        //Controlla che inizii con un numero o il simbolo "+"
        if (c >= '0' && c <= '9' || c == '+')
        {
            stringunita += c;
        }
    }
    return stringunita;
}
```

Ora che sono convertiti in string devo controllare che il numero di telefono rispetti i parametri prestabiliti usando .StartsWith, che serve a controllare se l'inizio di una stringa corrisponde alla stringa (nel nostro caso +39, 0039 o 3) e .Length, che serve per controllare se una stringa é della lunghezza specificata.

Qui un esempio del primo caso:
```csharp 
if (ntelefono.StartsWith("+39") && ntelefono.Length == 13)
{
    return s;
}
```

Alla fine, se nessuno dei numeri rispetta i parametri, viene semplicemente fatto ```return "";```.

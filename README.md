# checkTelefono

L'esercizio richiedeva di controllare dei numeri di telefono gruppi di 3 per vedere quale di questi é un numero di telefono valido, restituirlo se lo é o restituire "" se non lo é.

I numeri di telefono vengono convertiti da array a uno string singolo per numero usando il metodo Uniscintelefono

``` 
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


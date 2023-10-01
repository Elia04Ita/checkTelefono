# checkTelefono

```C#
using System;
using System.Text.RegularExpressions;
using System.Collections.Generic;
public static class Telefono
{
    public static string Check(string[] input)
    {
        foreach (string s in input)
        {
            // Converte l'array in string
            string ntelefono = CleanPhoneNumber(s);

            // Verifica se la stringa è vuota o troppo corta
            if (string.IsNullOrEmpty(ntelefono) || ntelefono.Length < 10 || ntelefono.Length > 14)
            {
                continue;
            }

            // Controlla se la stringa inizia con +39, 0039 o 3 e se è della giusta lunghezza
            if (ntelefono.StartsWith("+39") && (ntelefono.Length == 13))
            {
                return s;
            }
            if (ntelefono.StartsWith("0039") && (ntelefono.Length == 14))
            {
                return s;
            }
            if (ntelefono.StartsWith("3") && (ntelefono.Length == 10))
            {
                return s;
            }
        }

        // Se nessun numero segue i parametri restituisce ""
        return "";

        //Unisce i caratteri in uno string
        static string CleanPhoneNumber(string input)
        {
            string stringunita = "";
            foreach (char c in input)
            {
                //Controlla che inizii con un numero o il simbolo "+"
                if ((c >= '0' && c <= '9') || c == '+')
                {
                    stringunita += c;
                }
            }
            return stringunita;
        }
    }
}
```

# Isogramma
Isogramma
Determina se una parola o una frase è un isogramma.

Per come lo intendiamo in questo esercizio, un isogramma è una parola o una frase che non ha lettere ripetute.
Sono ammessi spazi e segni di punteggiatura ripetuti.
## Descrizione del progretto
Realizzazione di un programma che permette di determinare se una parola è un isogramma o meno. <br>
**Esempi di isogrammi:**
- lumberjacks
- background
- downstream
- six-year-old
## Come funziona?
  
<details>
<summary>Caratteri speciali</summary>

```c#
  //rimpiazzo i caratteri speciali per evitare errori
        word = word.Replace(" ", "");
        word = word.Replace("-", "");
        word = word.ToLower();
        int lunghezzaParola;
        bool LettereUguali = true;
        lunghezzaParola = word.Length;
```

Questo pezzo di codice serve a rimuovere eventuali caratteri speciali che andrebbero a compromettere la validità del programma
</details>

<details>
<summary>Controllo contenuto</summary>

```c#
   if (lunghezzaParola <= 0){
            return true;
    }
```
Controlliamo che la parola non sia vuota
</details>
  
  
<details>
<summary>Isogramma?</summary>

```c#
      for (int j = 0; j < lunghezzaParola; j++)
      {
          for (int i = 0; i < lunghezzaParola; i++)
          {
              //faccio questo controllo per evitare che i due contatori dei cicli collidano
              if (i == j)
              {
                  LettereUguali = true;
              }

              if (word[j] == word[i] && LettereUguali == false)
              {
                  return false;
              }
              LettereUguali = false;

          }
      }
      return true;
```

Questo pezzo di codice controlla tramite più cicli e condizioni che la parola sia un isogramma
</details>
  
  
  
  

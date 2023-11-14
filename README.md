# StringsEmCSharp

![Untitled](Strings%20C%23%201827a08cab5040fcb0da4ada1e3e42ae/Untitled.png)

![Untitled](Strings%20C%23%201827a08cab5040fcb0da4ada1e3e42ae/Untitled%201.png)

```csharp
/*                              CRIACAO DE ID/HASH NO C#
        var id = Guid.NewGuid();  indentificado global unico, resumindo, um id feito pelo C#. RESULTADOR => 3d918ae8-0356-4040-b565-4f6a778886b4 , ele gera um hash diferente cada vez que demos um run no programa
        id.ToString(); transformando ele em uma string

            var id1 = new Guid(); aqui ele gera um hash com todos os numeros zeros 
                                    RESULTADO => 00000000-0000-0000-0000-000000000000 
        id = new Guid("3d918ae8-0356-4040-b565-4f6a778886b4"); pegamos o primeiro hash e pedimos para que ele mostrasse somente este hash
        Console.WriteLine(id.ToString().Substring(0,8)); aqui ele transforma em string e com o substring ele pega somente os primeiros 8 caracteres
        
         
         **********************************************************************************************************
         

                                INTERPORLACAO DE STRINGS 

            var texto = "o preço do produto e " + price + " apenas na promocao";  aqui ele ja faz a parte de concatenacao, e converte o price em string(que antes era double)

            var texto = string.Format("o preço do produto e {0} apenas na promocao {1} ",price,true );
            aqui ele interpola as strings e no final temos que declarar elas, no final que declaramos true ele converteu o true em boolean e depois mostrou o resultado na tela 

            var texto = string.Format("o preço do produto e {1} apenas na promocao {0} ", price, true);
            podemos tambem inverter os arrays de strings como nesse exemplo que da certo

            var texto = ($"o preco do produto e {price} apenas na promocao");
            essa e a melhor forma de interpolacao de strings e uma das mais rapidas que tem para aplicacao

            var texto = ($@"o preco do produto e 
                        {price} apenas na promocao");
            quando tem quebra de linha, usar multiplas linhas e colocar caracteres especiais sera necessario colocar o '@' para que o C# entenda. 

        **********************************************************************************************************

                                    COMPARACAO DE STRINGS 

        var texto = "testando";

             Console.WriteLine(texto.CompareTo("testando"));  caso der '0' o resultado e verdadeiro

             Console.WriteLine(texto.CompareTo("Testand"));  caso der '1' ou '-1' o resultado e falso

             Console.WriteLine(texto.Contains("TEstando",StringComparison.OrdinalIgnoreCase)); aqui ele ignora o case sensitive e faz a comparacao de strings normalmente

             Console.WriteLine(texto.Contains("teste"));  aqui ele restorna um boolean e ver se retorna true ou false, o contais tem a funcao de comparar o texto e ver se ele contem essa palavra no texto

        var texto = "testando";

            Console.WriteLine(texto.StartsWith("teste"));  essa funcao pergunta se o texto começa com a palavra teste e retorna um valor boolean 
        Console.WriteLine(texto.StartsWith("testa"));  esse gerou um valor true em boolean

            Console.WriteLine(texto.EndsWith("teste"));  gerou um valor false e ele compara so o final da string

        var texto = "este e um texto";
            
            Console.WriteLine(texto.Equals("este"));  => FALSE 
            Console.WriteLine(texto.Equals("este e um texto")); => TRUE 
            Console.WriteLine(texto.Equals("ESTE E UM TEXTO",StringComparison.OrdinalIgnoreCase)); => TRUE 

        EQUALS compara se um determinado texto e igual ao outro, da pra comparar int, double e outros tipos primitivos

         
            **********************************************************************************************************
            
            
                                METODOS ADICIONAIS DE STRINGS
        var texto = "este texto e um teste";
        Console.WriteLine(texto.Length); aqui ele contabiliza quantos caracteres esta escrito

          Console.WriteLine(texto.Insert(5,"aqui"));  aqui ele inseri a palavra "aqui" na posicao 5 do array RESULTADO => este aquitexto e um teste

            Console.WriteLine(texto.Remove(5,5));  ele tem a funcao de remover e devemos decidir o inicio do array e depois colocar quantos caracteres vai ser removido que acima foi decidido remover 5 caracteres RESULTADO => este  e um teste

             Console.WriteLine(texto.ToLower()); // converte todo o texto para minusculo RESULTADO => este texto e um teste
             
            Console.WriteLine(texto.ToUpper());// converte todo o texto para maiusculo RESULTADO => ESTE TEXTO E UM TESTE

            Console.WriteLine(texto.IndexOf("t"));  indexOf e sempre um extensao do mesmo tipo, ele so vai aceita se for o mesmo tipo, ele vai aponta onde esta localizado o primeiro parametro em forma de array començando pelo numero 0, podemos colocar palavras, frase e outros.RESULTADO => 3

            Console.WriteLine(texto.LastIndexOf("t"));  ele faz a mesma funcao da anterior, mas ele pega o ultimo index

        **********************************************************************************************************
        
        
                                MANIPULANDO STRINGS

        var texto = "este texto e um teste";

            Console.WriteLine(texto.Replace("teste","isto"));ele vai substituir o primeiro caractere para o segundo que o desenvolvedor determinou RESULADOR => este texto e um isto 

        var divisao = texto.Split(" ");funcao de separar as palavras por espaço em branco

        Console.WriteLine(divisao[0]);
            Console.WriteLine(divisao[1]); aqui o desenvolvedor decidi qual palavra ele vai pegar
            Console.WriteLine(divisao[2]);
            Console.WriteLine(divisao[3]);

            var resultado = texto.Substring(5,5); aqui ele vai pega na quinta posicao uma string com 5 caracteres RESULADOR => texto

            var resultado = texto.Substring(5, texto.LastIndexOf("o"));  aqui ele pega a string na quinta posicao e vai percorrer ate a ultima string que tenha a letra 'o'.

        Console.WriteLine(texto.Trim()); funcao de tirar os espacos do começo e do Fim, isso e bom para pessoas que vai digitar senha ou email e nao da erro

        **********************************************************************************************************
                                                    LEITURA DE MULTIPLAS LINHAS
        
        var texto = new StringBuilder();  // aqui ele ele ler multiplas linha, seria a melhor formula

            texto.Append("este texto e um teste");
            texto.Append("este texto e um teste"); // append serve para anexar um item, quase a mesma funcao da concatenacao
            texto.Append("este texto e um teste");
            texto.Append("este texto e um teste");

            texto.ToString(); // como texto acima e um stringbuilder, precisamos converter para string quando for imprimir na tela
            Console.WriteLine(texto);  //  RESULTADOR => este texto e um testeeste texto e um testeeste texto e um testeeste texto e um teste
        

        */
```

## Concatenação de Strings

```csharp
int idade = 32;
double saldo = 10.35784;
String nome = "Maria";

Console.WriteLine("{0} tem {1} anos e tem saldo igual a {2:F2} reais", nome, idade, saldo); // isso se chama place holder, onde depois da frase incluimos as variaveis.

Console.WriteLine($"{nome} tem {idade} anos e tem saldo igual a {saldo:F2} reais"); // esse metodo se chama intercarlacao, onde esta a frase e as variaveis juntas, este e o melhor metodo.

Console.WriteLine(nome + " tem " + idade + " anos e tem saldo igual a "+ 
saldo.ToString("F2", CultureInfo.InvariantCulture) + " reais"); // esse metodo ´´e, a concatenacao tradicional, e o invariant culture so funciona neste metodo.
```

![Untitled](Strings%20C%23%201827a08cab5040fcb0da4ada1e3e42ae/Untitled%202.png)

conseguimos atribuir ate strings

```csharp
string s = "ABC";
        Console.WriteLine(s);
        s += "DEF";
        Console.WriteLine(s);
```

![Untitled](Strings%20C%23%201827a08cab5040fcb0da4ada1e3e42ae/Untitled%203.png)

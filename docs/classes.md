# Oi, bora falar de Classes em C#

Bem, se você já programa, sabe que a programação orientada a objetos é uma das maneiras mais poderosas de criar softwares. A programação orientada a objetos se baseia em construir objetos a partir de classes, que são como moldes que definem as características e os comportamentos dos objetos.

## Entendendo uma Classe em C#

Uma classe em C# é basicamente um molde pra criar objetos. A classe pode ter dentro dela **campos** (que são como variáveis), **propriedades** (que são um jeito fácil de acessar esses campos), **métodos** (que são como funções que fazem algo) e **eventos** (que são como mensagens que o objeto manda pra quem estiver ouvindo). Por enquanto, só serão abordados os três primeiros itens.

Por exemplo, imagine que nós queremos criar uma classe pra representar uma pessoa. A gente pode criar uma classe assim:

```csharp
public class Pessoa
{
    private string nome;

    public int Idade { get; set; }

    public void Falar(string mensagem)
    {
        Console.WriteLine($"{nome} diz: {mensagem}");
    }
}
```

Nessa classe, a gente tem um campo [privado](modificadores_de_acesso.md) `nome`, uma propriedade [pública](modificadores_de_acesso.md) `Idade` pra acessar e modificar a idade da pessoa e um método [público](modificadores_de_acesso.md) `Falar` que faz a pessoa falar alguma coisa.

## Criando Objetos a partir de uma Classe em C#

Depois que a gente cria a classe, aí a gente pode criar objetos a partir dela. Pra criar um objeto, a gente usa a palavra-chave `new`. Por exemplo, a gente pode criar um objeto **Pessoa** assim:

```csharp
Pessoa pessoa = new Pessoa();
pessoa.Nome = "Maria";
pessoa.Idade = 30;
pessoa.Falar("Olá, como vai?");
```

Nesse exemplo, a gente cria um objeto pessoa da classe **Pessoa**, define o nome e a idade dela, e faz ela falar alguma coisa.

## Resumindo!
Enfim, uma classe em C# é importante pra criar objetos e fazer programas orientados a objetos. Com uma classe, podemos definir as características e comportamentos de um objeto e criar vários objetos a partir dela.
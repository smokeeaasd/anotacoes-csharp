# Objetos em C#

Em C#, um objeto é uma instância de uma [classe](classes.md). Pensa na classe como um molde que define as características e comportamentos do objeto, e o objeto como a cópia que foi criada com base nesse molde.

Por exemplo, imagine que temos a classe `Pessoa`, que tem como características o **nome**, **idade** e **profissão**. Quando criamos um objeto do tipo `Pessoa`, estamos criando uma cópia dessa classe com valores específicos para o nome, idade e profissão. Ou seja, cada objeto é **único**, mas tem as _mesmas características e comportamentos_ da classe que o define.

Aqui está um exemplo de código que cria um objeto do tipo `Pessoa`:

```csharp
public class Pessoa
{
    public string Nome { get; set; }
    public int Idade { get; set; }
    public string Profissao { get; set; }

    public Pessoa(string nome, int idade, string profissao)
	{
        Nome = nome;
        Idade = idade;
        Profissao = profissao;
    }

    public void Falar()
	{
        Console.WriteLine("Oi, eu sou " + Nome + " e tenho " + Idade + " anos.");
    }
}

// criando um objeto do tipo Pessoa
Pessoa pessoa1 = new Pessoa("Lucas", 17, "Programador");
pessoa1.Falar(); // saída: "Oi, eu sou Lucas e tenho 17 anos."
```

Neste exemplo, a classe `Pessoa` tem as propriedades `Nome`, `Idade` e `Profissao`, e um método `Falar()`. O objeto **pessoa1** foi criado com valores específicos para cada uma dessas propriedades (nome "Lucas", idade 17 e profissão "Programador"). Quando chamamos o método `Falar()` no objeto **pessoa1**, ele exibe uma mensagem na tela com base nas propriedades definidas para esse objeto.

E é assim que objetos funcionam em C#! Eles permitem que você crie instâncias únicas de uma classe e personalizar cada uma delas com valores específicos.
# Coe meu nobre, vem aprender sobre Abstract, Virtual e Override

As palavras-chave `abstract`, `virtual` e `override` são importantes em conjunto porque permitem a implementação de polimorfismo em C#. Isso significa que é possível criar classes que possuem métodos com o mesmo nome e parâmetros, mas com comportamentos diferentes, dependendo da classe concreta que está sendo usada. Isso facilita a reutilização de código e torna o programa mais flexível e adaptável a mudanças.

----------

## Abstract

Quando você marca uma classe como `abstract` em C#, significa que ela não pode ser instanciada diretamente, ou seja, não pode criar objetos a partir dela. Em vez disso, você precisa criar uma classe derivada (ou seja, uma classe que herda da classe abstrata) e implementar seus membros abstratos. Membros abstratos são métodos ou propriedades que não têm implementação, e precisam ser implementados pelas classes derivadas.

Aqui está um exemplo de uma classe abstrata Animal com um método abstrato `Falar()`:

```csharp
abstract class Animal
{
    public abstract void Falar();
}
```

Observe que a palavra-chave `abstract` é usada para marcar a classe e o método abstrato. Agora, você pode criar classes derivadas como Cachorro e Gato que herdam da classe Animal e implementam o método `Falar()`:

```csharp
class Cachorro : Animal
{
    public override void Falar()
    {
        Console.WriteLine("Au au!");
    }
}

class Gato : Animal
{
    public override void Falar()
    {
        Console.WriteLine("Miau!");
    }
}
```

## Virtual

A palavra-chave `virtual` é usada para marcar um método que pode ser substituído por uma classe derivada, mas que também tem uma implementação padrão. Isso significa que a classe derivada pode substituir o método e fornecer uma nova implementação, mas se não fizer isso, a implementação padrão será usada.

Aqui está um exemplo de uma classe base Pessoa com um método `Apresentar()` marcado como virtual:

```csharp
class Pessoa
{
    public virtual void Apresentar()
    {
        Console.WriteLine("Olá, eu sou uma pessoa!");
    }
}
```

Agora, você pode criar uma classe derivada Estudante que herda da classe Pessoa e substitui o método `Apresentar()`:

```csharp
class Estudante : Pessoa
{
    public override void Apresentar()
    {
        Console.WriteLine("Olá, eu sou um estudante!");
    }
}
```

Observe que a palavra-chave `override` é usada para substituir o método virtual na classe derivada.

## Override

A palavra-chave `override` é usada para substituir um método virtual ou abstrato na classe base por uma implementação na classe derivada.

Aqui está um exemplo de uma classe base Figura com um método abstrato `Area()`:

```csharp
abstract class Figura
{
    public abstract double Area();
}
```

Agora, você pode criar uma classe derivada Retangulo que herda da classe Figura e implementa o método `Area()`:

```csharp
class Retangulo : Figura
{
    private double largura;
    private double altura;

    public Retangulo(double largura, double altura)
    {
        this.largura = largura;
        this.altura = altura;
    }

    public override double Area()
    {
        return largura * altura;
    }
}
```

Observe que a palavra-chave `override` é usada para substituir o método abstrato na classe derivada.